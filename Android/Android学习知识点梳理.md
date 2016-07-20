# Android 学习知识点梳理

Android 学习的知识点

## Java 基础篇

封装、抽象、多态、接口、抽象类、泛型、反射、lamda表达式等等

## Android 基础篇

四大组件（Activity、Service、ContentProvider、BroadcastReceiver、Fragment）

[Fragment 和 Activity 详细的生命周期](https://github.com/xxv/android-lifecycle)

Material Design 控件的使用

布局

Intent 

[Android Intent最全面的解析](http://mp.weixin.qq.com/s?__biz=MzA5MzI3NjE2MA==&mid=2650235926&idx=1&sn=58d03be2956944647df6a9719c90d13b&scene=1&srcid=0518V43oqfWKA0zduywv5FRe#wechat_redirect)

Notification

[Android通知栏的微技巧](http://mp.weixin.qq.com/s?__biz=MzA5MzI3NjE2MA==&mid=2650235923&idx=1&sn=af1fc1a6b60282732d94b0e7a354488f&scene=1&srcid=0517c0t12GnMgc5tWAkEMHNs#wechat_redirect)

[Android N 带来的新通知栏](https://www.rogerblog.cn/2016/04/15/Android-N-Introducing-upgraded-Notifications/)

多线程、同步

持久化：文件IO、SharePreferences、SQLite

View、ViewGroup等相关知识点，包括事件分发啊，什么的等等

动画

Binder 和 Service要怎么做

RecyclerView（ListView、GridView优化已经很久了）

Bitmap加载和优化

Runtime Permission

## 算法数据结构篇

两部分，一个是 Java 自身提供的数据结构，一个是 Android 经过优化后的数据结构

会一些基础的算法和数据结构

## 源码框架篇（提升进阶）

[Android开源项目推荐之「图片加载到底哪家强」](http://mp.weixin.qq.com/s?__biz=MzA4NTQwNDcyMA==&mid=2650661949&idx=1&sn=09aececd879bd8b4635e6a63a8249808&scene=1&srcid=0623mjQ2J6NG4S71GI2cpEJU#wechat_redirect)

系统机制的分析

自定义View 和 动画的原理、以及自己动手实践（网上那些开源的各种各样的View和动画怎么做的）

第三方开源框架使用，原理分析，源码分析

butterknife [深入理解 ButterKnife，让你的程序学会写代码](http://mp.weixin.qq.com/s?__biz=MzA3NTYzODYzMg==&mid=2653577446&idx=1&sn=e1c12a2dc3d45babf66f86f4840bed2c&scene=1&srcid=0720PKnScilDs4ZhjwCe3tG8#wechat_redirect)

加载图片框架（Picasso、Glide、Fresco）

网络访问框架（OkHttp、Volley、Retrofit）

数据库ORM框架（GreenDao、LitePal）

缓存框架和机制设计（Lrucache、DiskLruCache、robospice）

总线框架（EventBus）

插件化（一些原理之类的）

待补充吧

## 性能优化篇

性能优化的原理

ListView之类的做局部刷新

把应用开发中需要注意的性能问题进行罗列，并写出响应的分析和解决方案

保活怎么做

网络访问怎么做？

缓存机制要怎么设计

如何使用一些工具帮助我们排查问题做优化方案啊

[腾讯优测：使用Android Studio的Inspact Code做静态代码分析](http://mp.weixin.qq.com/s?__biz=MzAxMzYyNDkyNA==&mid=2651332108&idx=1&sn=0595ccab1516fcff06f15a8f8f50f8ea&scene=0)

## 适配篇

讲讲一些适配的问题和方案，讲讲如何排查得到结果的

## 编码篇

### 代码可读性

[【译】如何给变量取个简短且无歧义的名字](http://yemengying.com/2016/06/25/cleanCode4naming/)

### 架构和封装

[从BaseActivity与BaseFragment的封装谈起](http://blog.csdn.net/tyk0910/article/details/51355026)

对封装、抽象的理解（泛型、抽象类、接口这些怎么看？）

编码结构，MVC、MVP、MVVM的真正理解和应用

## 网络协议篇

网络协议五花八门，我们不需要每个都去掌握（也没那种精力），但是像那些开发过程中经常使用到的这些，就需要好好深入去了解一番，比如：Socket、Http、Https、DNS等。其他协议，可以根据具体的开发业务需要再进行深入的细化学习。

### 什么是网络协议？

怎么去理解互联网协议？一台计算机要能够上网必须满足什么条件？

[互联网协议入门（一）](http://www.ruanyifeng.com/blog/2012/05/internet_protocol_suite_part_i.html)
[互联网协议入门（二）](http://www.ruanyifeng.com/blog/2012/06/internet_protocol_suite_part_ii.html)

### DNS 协议

[DNS 原理入门](http://www.ruanyifeng.com/blog/2016/06/dns.html)

- 访问一个站点总是要通过域名找到服务器的IP地址，才能进行访问的。如果没有 DNS 协议，基本上想上网就没指望了。
- 考虑到要进行负载均衡，所以一个域名会有对应的多个IP地址。

### 其他

HTTP、HTTPS协议等是怎么工作的

Socket怎么玩，推送要怎么设计？

客户端要怎么玩这些协议

## 应用安全篇

[Android安全攻防战，反编译与混淆技术完全解析（上）](http://blog.csdn.net/guolin_blog/article/details/49738023)
[Android安全攻防战，反编译与混淆技术完全解析（下）](http://blog.csdn.net/guolin_blog/article/details/50451259)
[Android 代码保护攻防战，以及一种别样的技巧](http://www.woaitqs.cc/android/2016/07/07/a-method-to-protect-your-android-code.html)

## 新知识篇

了解一些主要的并不需要都去深入

新出来的UI控件啊，例如ConstraitLayout之类的

Android的新特性，例如JobScheduler、Doze Mode之类的

Rxjava

React Native

Hybird

Hotfix

Hook

增量更新

## 工具技巧篇

### IDE

高效实用 Android Studio ，提高开发效率。

[倍数提高工作效率的Android Studio奇技](http://zlv.me/posts/2015/07/13/14_android-studio-tips/)


## 服务器篇

只涉及一些基本常用的，能够配合客户端来用即可。

## 英语篇

加强学习英语啊！！！！

## 面试注意事项篇

没做过就说没做过，不懂就说不懂

产品分析，你去面试人家的职位，肯定要对他们家的产品有所了解才行。
