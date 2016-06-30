# 那些值得你试试的 Android 逆向分析工具

介绍自己最近的情况，和写作本文的目的，说说写文的一点点收获。

## 逆向分析是何物

简单介绍逆向分析的概念

## Apk的生成和内部结构

简单的介绍Apk打包的原理，还有什么二次打包和混淆防范之类的。

从[ Android 官方文档 ](https://developer.android.com/studio/build/index.html)中看到下面的打包流程

![](http://a.hiphotos.baidu.com/image/pic/item/8b13632762d0f703997dbdcf00fa513d2797c5d1.jpg)

介绍 Apk 的生成流程和内部结构。

下面就是我们apk的一个最基础的目录结构

![](http://d.hiphotos.baidu.com/image/pic/item/08f790529822720edf87b3ec73cb0a46f21fab5f.jpg)

介绍上面各大文件和目录是干嘛用的。

META-INF： 什么文件目录暂时未知
res： apk的资源文件目录
AndroidManifest.xml： Android项目中的配置文件
classes.dex： class字节码文件打包生成的dex文件
resources.arsc： 资源文件压缩包

需要告诉大家文中的xml文件之类的都是加密的。

经过前面的介绍，我们大致已经明白了一个Apk是怎么生成的，以及Apk的内部构造是怎样的。接下来就可以愉快的介绍一些逆向分析的工具，让大家闲暇之余可以自己好好的爽一把。

## apktool

![](http://ibotpeaches.github.io/Apktool/images/logo.png)

apktool 是第一个要介绍的逆向分析工具，它大致具有以下几个功能：

- 还原 apk 中所包含的 resources.arsc, classes.dex, 9.png 和 xml 等文件；
- 对 apk 进行重新（二次）打包；
- 反编译依赖于 Framework 的 apk 文件；
- 调试 Smali 文件；

如果此时你看不懂上面这四点，别着急，请继续往下阅读本文。而对于想要更加详细了解 apktool 的童鞋，可以直接前往它的官方站点：

> http://ibotpeaches.github.io/Apktool/

### 常用命令

那些常用的命令，很所谓的反编译依赖于 Framework 的 apk 文件。

http://www.codefrom.com/paper/ApkTool%20%E5%9F%BA%E7%A1%80%E7%94%A8%E6%B3%95

http://bbs.gfan.com/android-2657915-1-1.html

### 反编译操作

使用不同版本的 Apktool 是会报错的 

### smali 

什么是smali语言....

smali语句可以用来调试....

apktool原本是具有调试 Smali 代码的功能，但在 2.0.3 版本开始，作者就已经标记打算废弃此功能，到 2.1.0 版本就已经将其完全移除掉。但这并不意味着我们就无法去调试这些 Smali 代码了，Smali 的作者早已为我们准备好了一款用于调试 Smali 代码的插件 [SmaliIdea](https://github.com/JesusFreke/smali/wiki/smalidea) 。目前 SmaliIdea 最新的版本是 0.03，喜欢玩耍的童鞋可以到下面的下载地址中：

> https://bitbucket.org/JesusFreke/smali/downloads

找到最新版的 SmaliIdea 进行安装使用

![](http://g.hiphotos.baidu.com/image/pic/item/50da81cb39dbb6fdb40e3d320124ab18972b3749.jpg)

忘了补充一点，**这个插件是基于 IntelliJ IDEA 和 Android Studio 的**，还在使用 ADT 开发的童鞋就爱莫能助了。

强调下 apktool 的作者：http://www.ourunix.org/post/101.html 提供这个工具不是让我们去干盗版违法活动的。

## dex2jar + jd-gui

### dex2jar 常用命令

dex2jar 带的命令如何使用....

### 反编译操作

dex2-jar 逆向 dex 后生成的目录结构信息...

### jd-gui

接着上面生成的 jar 包，那要如何查看他们的源代码呢，操作也是非常简单的。直接去到 http://jd.benow.ca/ 下载名为 jd-gui 的工具，然后将生成的 jar 包拖曳进去即可查看到对应的源代码。

对比混淆和没混淆过的目录结构的区别。

作者分别在 SourceForge、Github 或者 Bitbucket 都托管了一份 dex2-jar ，下面三个链接都是相同的东西，喜欢哪个用哪个

> SourceForge：https://sourceforge.net/projects/dex2jar/
> Github：https://github.com/pxb1988/dex2jar
> Bitbucket：https://bitbucket.org/pxb1988/dex2jar

## enjarify

为什么不用 dex2jar ，想看README.md

> 官方地址：https://github.com/google/enjarify

## ClassyShark

http://mp.weixin.qq.com/s?__biz=MzA4NTQwNDcyMA==&mid=402526638&idx=1&sn=bdd13a3cb722e72f67d4dcc1af0f620d#rd

> 官方地址：https://github.com/google/android-classyshark

## Procyon

![](http://h.hiphotos.baidu.com/image/pic/item/ac6eddc451da81cb8e96acde5a66d016092431b4.jpg)

http://blog.csdn.net/zhaokaiqiang1992/article/details/45038125#代码框架解析

> 官方地址：https://bitbucket.org/mstrobel/procyon

## TcpDump

http://blog.csdn.net/zhaokaiqiang1992/article/details/45038125#代码框架解析

http://mrpeak.cn/blog/tutorial-tcpdump/

## WireShark

http://blog.csdn.net/zhaokaiqiang1992/article/details/45038125#代码框架解析

## 总结

[如何从技术上全面分析一款Android竞品？](http://mp.weixin.qq.com/s?__biz=MzA4MjU5NTY0NA==&mid=402218810&idx=1&sn=1005ca3c2c1e391f7ce4a9851d2722eb&scene=0#wechat_redirect)