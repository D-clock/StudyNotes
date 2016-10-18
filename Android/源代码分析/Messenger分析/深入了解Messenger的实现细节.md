# 深入了解 Messenger 的实现细节

近一个半月因为工作变动的缘故，忙着交接工作和复习面试。没有多少时间来写博客，连一周三次的健身都有几个星期没练了，好多同事问我是胖了还是壮了（我迅速就岔开话题了，机智boy）。上周离职，这周主要在处理一些私事、做些入职准备工作、看点书之类的，下周入职YY（上周才知道原来大神罗升阳也在YY）。好啦，说了这么多，要开始进入 Messenger 的正题了。

## 前言

看这篇文章前，需要对 Android 的进程间通讯方式有所了解，不然可能会云里雾里。

## 从使用 Messenger 说起

Android 上实现 IPC （进程间通讯）的方式有好几种，其中有一种就是使用 AIDL 方式实现，对使用 AIDL 不了解的童鞋可以看下方的官方文档（需要梯子）。

> https://developer.android.com/guide/components/aidl.html

对于使用 AIDL 方式通讯，其关键就在于创建 aidl 文件，系统会自动为 aidl 文件生成相应的 Java 类，其关键实现在于生成的 Java 类中。

![](http://diycode.b0.upaiyun.com/photo/2016/1febfc2cfb863d4e9cee154ea856507c.png)

系统提供了一个更方便我们进行 IPC 的类 —— Messenger，先来看看如何使用 Messenger（熟悉的童鞋完全可以跳过这一部分）。

- 第一步：客户端进程创建两个 Messenger，一个 Sender ，一个 Receiver；

```java

	//客户端进程发消息给服务进程
	private Messenger mSender;
	//客户端进程接收服务进程回调
    private Messenger mReceiver = new Messenger(new Handler() {
        @Override
        public void handleMessage(Message msg) {
            super.handleMessage(msg);
            Bundle data = msg.getData();
            if (data != null) {
                String response = data.getString("body");
                Toast.makeText(MainActivity.this, response, Toast.LENGTH_SHORT).show();
            }
        }
    });

```

- 第二步：编写Service类，并需要在 AndroidManifest.xml 配置多进程；

```java

public class IPCService extends Service {

    private Messenger messenger = new Messenger(new Handler() {
        @Override
        public void handleMessage(Message msg) {
            super.handleMessage(msg);
            try {
                Thread.sleep(2 * 1000);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
            Message response = Message.obtain();
            Bundle data = new Bundle();
            data.putString("body", "response");
            response.setData(data);
            try {
                msg.replyTo.send(response);//回调客户端
            } catch (RemoteException e) {
                e.printStackTrace();
            }
        }
    });

    @Override
    public IBinder onBind(Intent intent) {
        return messenger.getBinder();//将Binder返回给请求绑定的进程
    }

}

```

- 第三步：绑定Service进程，并在 ServiceConnection 中初始化 Sender；

```java

	Intent intent = new Intent(this, IPCService.class);
    startService(intent);
    bindService(intent, conn, Context.BIND_AUTO_CREATE);//启动绑定Service进程

	private ServiceConnection conn = new ServiceConnection() {
        @Override
        public void onServiceConnected(ComponentName name, IBinder service) {
            mSender = new Messenger(service); //用Binder初始化Sender
        }

        @Override
        public void onServiceDisconnected(ComponentName name) {

        }
    };

```

- 第四步：用 Sender 和 Receiver 完成客户端进程和服务进程的交互。

```java

	if (mSender != null) {
        Message message = Message.obtain();
        message.replyTo = mReceiver;//将 Receiver 一并发送给服务进程
        try {
             mSender.send(message);
        } catch (RemoteException e) {
             e.printStackTrace();
        }
     }

```

至此，在绑定服务进程初始化 Sender 后，即可以做多进程间的交互工作了。使用 Messenger 来实现多进程的交互相比我们用 aidl 来要方便得多，但是 Messenger 的内部也是采用 aidl 实现的，只不过为了方便开发者调用而进行一些封装，使得开发者们可以忽略 aidl 的实现细节。简单的了解了 Messenger 的基本使用后，下面我们就来看看 Messenger 的源代码，了解一些内部的实现细节。

## Messenger 源代码通读

Messenger 类位于 android.os 包下，代码量不是很多，所以看起来难度不大，只有如下这么几个方法。

![](http://diycode.b0.upaiyun.com/photo/2016/4b9f10adf3a955efd6ccbfd229058498.png)

在上面的示例代码中可以看到，客户端进程有 Sender 和 Receiver 两个 Messenger，如果不需要实现服务进程回调客户端进程，那么 Receiver 完全可以不要。当需要服务进程回调客户端进程时，则需要传入 Receiver 了。由于需要在进程间传递 Messenger 对象，那么 Messenger 类就必须要继承 Serializable 或者 Parcelable 接口。按照 Android 系统一向的风格，都是偏向于推荐继承 Parcelable 来实现。

![](http://diycode.b0.upaiyun.com/photo/2016/59e099375589f2c9ecd30214ba60fd75.png)

所以，上面看到的 describeContents、writeToParcel 方法和 CREATOR 对象实际上继承 Parcelable 的实现。不明白的童鞋可以参照 Parcelable 的官方文档（需要梯子）

> https://developer.android.com/reference/android/os/Parcelable.html

而 equals 和 hashCode 方法自然不用多说啦，大家熟悉得很。而 writeMessengerOrNullToParcel 和 readMessengerOrNullFromParcel 这对静态方法主要是实现 Messenger 在 Parcel 中的读写操作的，实现比较简单，大家参见下面代码就可以理解了。

![](http://diycode.b0.upaiyun.com/photo/2016/081313d3be066c9f090fca264560f2e4.png)

当然，Messenger 除了继承 Parcelable 外，还需要声明一个同名的 Messenger.aidl 文件，可以在 framework 层源码下 android.os 包中找到 Messenger.aidl 文件，对于写过 aidl 的童鞋，肯定不陌生了。

![](http://diycode.b0.upaiyun.com/photo/2016/c26a66640c5d45fa1cce02d78a34e2ca.png)

排除掉上面提到的方法，剩下的主要是 Messenger 的两个构造方法以及 getBinder 和 send 方法。客户端调用服务进程方法时，是通过 Messenger 中的 send 方法，所以我们先直接看 send 方法中的内部实现

![](http://diycode.b0.upaiyun.com/photo/2016/10b6829f799a800cf17425cef7368e42.png)

其内部是调用了 mTarget 的 send 方法，那么 mTarget 又是何物呢？

![](http://diycode.b0.upaiyun.com/photo/2016/2d3d61b7f16cdd2e0dae17fdb89472fc.png)

从上面可以看到 mTarget 是一个 IMessenger 实例，作为 Messenger 唯一的成员变量。 初始化 mTarget 是在 public Messenger(Handler target) 构造函数中，利用 Handler 的 getIMessenger 方法来获取一个 IMessenger 的实例。

![](http://diycode.b0.upaiyun.com/photo/2016/ff8f02982923cb6616ced561a3d327ee.png)

从上图可以看到 getIMessenger 前面是没有修饰符的，这样控制了该方法的作用域仅限于 android.os 包内给其他类使用，我们日常开发是无法使用该方法的，所以在 API 文档中也没有提供相应接口文档。在倒数第二行中可以看到 new MessengerImpl() 并在最后 return 给调用者。所以实际上， mTarget 具体实现是在 MessengerImpl 中。

![](http://diycode.b0.upaiyun.com/photo/2016/8767996b7fe81f7fa1f07b86c8002416.png)

MessengerImpl 实际上是 Handler 的一个私有内部类，它继承了 IMessenger.Stub 并实现 send 方法。用过 aidl 的童鞋 IMessenger.Stub 的身影想必就明白了，实际上 IMessenger 就是系统提供的 IMessenger.aidl 文件，而 IMessenger.Stub 就是由 IMessenger.aidl 生成的类。 IMessenger.aidl 在 framework 层代码的 android.os 包中可以找到，而关于 IMessenger 的 Java 实现，则可以看下面的链接。

> http://grepcode.com/file/repository.grepcode.com/java/ext/com.google.android/android/5.1.1_r1/android/os/IMessenger.java/

MessengerImpl 的 send 实现相对也比较简单，只有两行代码

```java

	public void send(Message msg) {
        msg.sendingUid = Binder.getCallingUid();
        Handler.this.sendMessage(msg);
    }

```

首先是将发起调用的客户端进程的 Linux Uid 存储在我们传入的 Message 对象中，服务进程收到 Message 可以通过 msg.sendingUid 得知发起调用的进程的 Linux Uid。接着通过 Handler 的 sendMessage 方法发送给服务进程，这意味着 Messenger 与服务进程间的操作是串行的，因此，在有并行需求的场景下 Messenger 就不适用了。

了解完了 send 方法后，最后就只剩下 getBinder 了，其内部实现也简单。

![](http://diycode.b0.upaiyun.com/photo/2016/9328b1e17bd9b1526c8058759d8e1037.png)

参照前面的示例代码，这里主要还是在 Service 的 onBind 方法中返回 Binder 对象给客户端调用，实现同样是 IMessenger 的 Java 实现中。

至此，基本上看完了整个 Messenger 的内部代码，从上面的分析上看，内部实现确实非常简单，基于 aidl 的基础上做的封装实现，又对开发者屏蔽了底层 aidl 的实现细节。当然个人认为有两点不足之处：

- 一个前面提到的 send 操作串行，并行场景则无法用 Messenger；
- Messenger 内部没有做 Binder 键断裂重连的处理（个人认为内部处理了会更好，更加屏蔽底层的实现细节）；

## 远程调用的阻塞与非阻塞

Android 系统跨进程通讯的底层实现都是通过 Binder 实现，正常情况下客户端进程发起一个远程方法调用的流程大致如下：

1. 客户端线程发起调用；
2. 客户端线程将远程调用操作交给 Binder 线程池，并阻塞等待返回远程方法执行完毕返回；

![](http://diycode.b0.upaiyun.com/photo/2016/4cb8d854d7419b005a701a2188a83d2f.png)

这也就意味着，我们不能在客户端进程的 UI 线程中发起远程方法调用，不然如果远程方法执行了耗时操作，客户端的 UI 线程将会被阻塞，从而造成 ANR 的问题存在。读者可以自行尝试自定义 aidl 并发起一个耗时的远程方法调用进行验证。但是，如果你使用系统提供的 Messenger ，则不会出现这样的问题，无论你的远程方法执行多么耗时，客户端 Messenger 发起调用后会继续执行接下来的代码，并不会进行阻塞等待。这里让我百思不得其解，为什么呢？前面我们可以看到 Messenger 的 send 方法实现是在 MessengerImpl 中

![](http://diycode.b0.upaiyun.com/photo/2016/8767996b7fe81f7fa1f07b86c8002416.png)

并且，发送 Messeage 的操作是利用主线程的 Handler ，并没有其他的异步操作，为何执行的过程中不阻塞？这点我也完全没有想明白，最后折腾半天无果向任玉刚老师求助才得到答案。原来，默认情况下发起的远程方法调用都是阻塞式的，但也可以是非阻塞式的。 Messenger 就是采用非阻塞的方式通讯，其关键就在于 IMessenger.aidl 的实现

![](http://diycode.b0.upaiyun.com/photo/2016/c910c43934ed01acaa0f7f46ba4c6444.png)

相比平常自定义的 aidl，多了 oneway 的关键字，声明和不声明 oneway 关键字的在于生成 Java 类中一个参数

![](http://diycode.b0.upaiyun.com/photo/2016/8da2301cb121267dc8693c1f13d98044.png)

![](http://diycode.b0.upaiyun.com/photo/2016/c9bf78bd8feed4955a744a96cf60e494.png)

不声明 oneway 时，mRemote.transact 传入的最后一个参数是 0；声明 oneway 时，mRemote.transact 传入的最后一个参数是 android.os.IBinder.FLAG_ONEWAY 。

![](http://diycode.b0.upaiyun.com/photo/2016/cc38584579c2f73a0a4c09f6d5ae7c58.png)

![](http://diycode.b0.upaiyun.com/photo/2016/fa9f37187ef5ee7af596d70f3caa6f52.png)

查看 API 文档即可以看到 FLAG_ONEWAY 的作用就是让客户端能够非阻塞的调用远程方法，至此真相大白，如果我们自定义的 aidl 也想实现非阻塞的调用，只需声明 oneway 关键字即可。

## 总结

因为平时并不常用到 oneway，加上文档提及的很少，唯一有描述的就是下面这段。这次看了 Messenger 的代码才知道有这么回事，也是涨姿势了。

![](http://diycode.b0.upaiyun.com/photo/2016/46cdaf6e8fada5e087b852613e220220.png)

对我的博文感兴趣，可以关注我的简书哟：

> http://www.jianshu.com/users/ec95b5891948/latest_articles
