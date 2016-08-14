# Android 学习知识点梳理

Android 学习的知识点笔记

## Java 基础篇

封装、抽象、多态、接口、抽象类、注解、泛型、反射、lamda表达式等等

### 异步

- [Java并发编程：volatile关键字解析](http://www.cnblogs.com/dolphin0520/p/3920373.html)
- [你见过这样的单例模式吗？](http://mp.weixin.qq.com/s?__biz=MzA5MzI3NjE2MA==&mid=2650236548&idx=1&sn=b6c2e406b0b67874cd55a5638ef3c3c0&scene=1&srcid=0802DVnCp2PMe1pSKoFYu4ay#wechat_redirect)

### 注解和反射

- [Android编译期代码生成之apt实践入门](https://segmentfault.com/a/1190000005100468)
- [Android-APT-Framework](https://github.com/lizhaoxuan/Android-APT-Framework)
- [反射、注解与依赖注入总结](http://sunfusheng.com/java/2016/04/12/reflection-annotation-injection.html)

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

### 动画

- [Android 动画基础](http://www.lightskystreet.com/2015/05/23/anim_basic_knowledge/)
- [Android动画系列](http://www.lightskystreet.com/categories/Android/Android%E5%8A%A8%E7%94%BB/)
- [如何高效的学习Android动画](http://www.lightskystreet.com/2015/08/31/android_how_to_lean_anim_efficiently/)

- [如何学习 Android Animation？](https://segmentfault.com/a/1190000004354609)

- [Android属性动画完全解析(上)，初识属性动画的基本用法](http://blog.csdn.net/guolin_blog/article/details/43536355)
- [Android属性动画完全解析(中)，ValueAnimator和ObjectAnimator的高级用法](http://blog.csdn.net/guolin_blog/article/details/43816093)
- [Android属性动画完全解析(下)，Interpolator和ViewPropertyAnimator的用法](http://blog.csdn.net/guolin_blog/article/details/44171115)

- [浅析Android动画（一），View动画高级实例探究](http://www.cnblogs.com/wondertwo/p/5295976.html)
- [浅析Android动画（二），属性动画高级实例探究](http://www.cnblogs.com/wondertwo/p/5312482.html)
- [浅析Android动画（三），自定义Interpolator与TypeEvaluator](http://www.cnblogs.com/wondertwo/p/5327586.html)

- [当数学遇上动画(一)](http://hujiaweibujidao.github.io/blog/2016/05/26/when-math-meets-android-animation/)
- [当数学遇上动画(二)](http://hujiaweibujidao.github.io/blog/2016/05/27/When-Math-meets-Android-Animation-2/)
- [当数学遇上动画(三)](http://hujiaweibujidao.github.io/blog/2016/05/27/When-Math-meets-Android-Animation-3/)

### 自定义View

[自定义View怎么学](http://mp.weixin.qq.com/s?__biz=MzAxNzMxNzk5OQ==&mid=2649484578&idx=1&sn=891d1d65209aa5302b064577799b06c1&scene=1&srcid=0808sWI4HJXfSFvHbfqMbPmL#rd)

自定义View 和 动画的原理、以及自己动手实践（网上那些开源的各种各样的View和动画怎么做的）

Binder 和 Service要怎么做

RecyclerView（ListView、GridView优化已经很久了）

Bitmap加载和优化

Runtime Permission

## 算法数据结构篇

两部分，一个是 Java 自身提供的数据结构，一个是 Android 经过优化后的数据结构

[九大基础排序总结与对比](http://blog.csdn.net/amazing7/article/details/51603682)

会一些基础的算法和数据结构

## 源码框架篇（提升进阶）

[Android开源项目推荐之「图片加载到底哪家强」](http://mp.weixin.qq.com/s?__biz=MzA4NTQwNDcyMA==&mid=2650661949&idx=1&sn=09aececd879bd8b4635e6a63a8249808&scene=1&srcid=0623mjQ2J6NG4S71GI2cpEJU#wechat_redirect)

系统机制的分析

第三方开源框架使用，原理分析，源码分析

butterknife [深入理解 ButterKnife，让你的程序学会写代码](http://mp.weixin.qq.com/s?__biz=MzA3NTYzODYzMg==&mid=2653577446&idx=1&sn=e1c12a2dc3d45babf66f86f4840bed2c&scene=1&srcid=0720PKnScilDs4ZhjwCe3tG8#wechat_redirect)

加载图片框架（Picasso、Glide、Fresco）

网络访问框架（OkHttp、Volley、Retrofit）

数据库ORM框架（GreenDao、LitePal）

缓存框架和机制设计（Lrucache、DiskLruCache、robospice）

总线框架（EventBus）

Apk 动态加载

- [Android apk动态加载机制的研究](http://blog.csdn.net/singwhatiwanna/article/details/22597587)

Android 换肤技术

- [Android换肤技术总结](http://blog.zhaiyifan.cn/2015/09/10/Android%E6%8D%A2%E8%82%A4%E6%8A%80%E6%9C%AF%E6%80%BB%E7%BB%93/)
- [Android主题换肤 无缝切换](http://www.jianshu.com/p/af7c0585dd5b)

插件化（一些原理之类的）

- [包建强：Android插件化技术概述](http://mp.weixin.qq.com/s?__biz=MzA3ODg4MDk0Ng==&mid=2651112486&idx=1&sn=84231b09641646f2e371fcade88c323d&scene=1&srcid=0725r9QJRNpBzMdP2FF7neqM#wechat_redirect)
- [反射技术在android中的应用](http://blog.csdn.net/tiefeng0606/article/details/51700866)

待补充吧

## 性能优化篇

性能优化的原理，相关的指标

ListView做局部刷新

- [Facebook新闻页ListView优化](http://blog.aaapei.com/article/2015/02/facebookxin-wen-ye-listviewyou-hua)

把应用开发中需要注意的性能问题进行罗列，并写出响应的分析和解决方案

保活怎么做

网络访问怎么做？

缓存机制要怎么设计

[缓存更新的套路](http://coolshell.cn/articles/17416.html)

如何使用一些工具帮助我们排查问题做优化方案啊

[腾讯优测：使用Android Studio的Inspact Code做静态代码分析](http://mp.weixin.qq.com/s?__biz=MzAxMzYyNDkyNA==&mid=2651332108&idx=1&sn=0595ccab1516fcff06f15a8f8f50f8ea&scene=0)

## 适配篇

讲讲一些适配的问题和方案，讲讲如何排查得到结果的

- [腾讯优测：Android5.0-6.0双卡适配指南](http://mp.weixin.qq.com/s?__biz=MzAxMzYyNDkyNA==&mid=2651332309&idx=1&sn=f9e7270b1610ebf88488c06615bb6ed6&scene=0#wechat_redirect)
- [腾讯优测：鹅厂专家详解Android N适配要点](http://mp.weixin.qq.com/s?__biz=MzAxMzYyNDkyNA==&mid=2651332192&idx=1&sn=963420cb4ac8b9b86838fc9dc066cb73&scene=0#wechat_redirect)

## 编码篇

### 代码可读性

[【译】如何给变量取个简短且无歧义的名字](http://yemengying.com/2016/06/25/cleanCode4naming/)

### 架构和封装

[从BaseActivity与BaseFragment的封装谈起](http://blog.csdn.net/tyk0910/article/details/51355026)

### 设计模式

[别人再问你设计模式，叫他看这篇文章](http://www.jasongj.com/design_pattern/summary/)
[设计模式合集](http://www.jasongj.com/tags/Design-Pattern/)

几大设计原则分别是！！！！

对封装、抽象的理解（泛型、抽象类、接口这些怎么看？）

编码结构，MVC、MVP、MVVM的真正理解和应用

- [腾讯Bugly：一步一步实现Android的MVP框架](http://mp.weixin.qq.com/s?__biz=MzA3NTYzODYzMg==&mid=2653577546&idx=1&sn=e10be159645a3aa8f6d6f209420fb412&scene=1&srcid=07289Nbf5unjDpiRXxvw1G90#wechat_redirect)
- [DataBinding最佳实践](http://www.jianshu.com/p/1fcda521fcda)

## 网络协议篇

网络协议五花八门，我们不需要每个都去掌握（也没那种精力），但是像那些开发过程中经常使用到的这些，就需要好好深入去了解一番，比如：Socket、Http、Https、DNS等。其他协议，可以根据具体的开发业务需要再进行深入的细化学习。

### 什么是网络协议？

怎么去理解互联网协议？一台计算机要能够上网必须满足什么条件？

[互联网协议入门（一）](http://www.ruanyifeng.com/blog/2012/05/internet_protocol_suite_part_i.html)
[互联网协议入门（二）](http://www.ruanyifeng.com/blog/2012/06/internet_protocol_suite_part_ii.html)

### DNS 协议

[DNS 原理入门](http://www.ruanyifeng.com/blog/2016/06/dns.html)

- 访问一个站点总是要通过域名找到服务器的IP地址，才能进行访问的。如果没有 DNS 协议，基本上想上网就没指望了。
- 考虑到要进行负载均衡，所以一个域名会有对应的多个IP地址。、

### TCP 协议

### UDP 协议

### 其他

HTTP、HTTPS协议等是怎么工作的

Socket怎么玩，推送要怎么设计？

客户端要怎么玩这些协议

## 应用安全篇

[Android安全攻防战，反编译与混淆技术完全解析（上）](http://blog.csdn.net/guolin_blog/article/details/49738023)
[Android安全攻防战，反编译与混淆技术完全解析（下）](http://blog.csdn.net/guolin_blog/article/details/50451259)
[Android 代码保护攻防战，以及一种别样的技巧](http://www.woaitqs.cc/android/2016/07/07/a-method-to-protect-your-android-code.html)

## 新知识篇

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
