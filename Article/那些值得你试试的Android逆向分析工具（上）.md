# 那些值得你试试的 Android 逆向分析工具（上）

最近一段时间因为琐事（有公有私）太多，加上搬家后，家里断网了一周，虽然有很多东西想写，但却迟迟没有动手。好在目前基本事情都搞完，又可以愉快的写东西了，所以，接下来博客更新的频率将会有所提高。写博客的好处是很多的哈，一方面总结可以分享也方便自己回顾，另一方面是当作者对知识点理解可能存在局限（或者错误）时，读者也会帮你指出。起初写作本文时，是打算把内容写成一篇文章的。但在整理完内容脉络结构后，发现写成一篇文章的话，内容过长，我自己都有点看不下去了。所以，还是分为上下篇来写会更好一些。好了，啰嗦了一小会儿，接下来开始进入文章的正题。

## 前言

本文主要是总结自己在开发过程中经常会用到的一些逆向开发工具，学会使用这些工具，可以帮助我们分析一些应用程序的 Apk 安装包。通过分析这些 Apk 我们可以获得相应的一些技术信息，例如：代码质量、某种业务的实现方式、用了什么第三方库等竞品分析行为。除此之外，也有一些高端玩家会去HOOK程序，更有甚者是通过修改代码然后进行二次打包。当然这些损害开发者利益的事情，是不值得提倡的。但如果只是出于学习的目的，我是十分建议多折腾的。

下面提到的所有工具，本文只是做一些功能介绍和一些基本的使用示例。要求面面俱到的讲解每个工具的用途，本人表示能力实在有限啊，所以感兴趣的童鞋还是自行深入挖掘。要是哪位童鞋对某些工具已经用得出神入化，也欢迎写成文章，顺便丢个链接给我学习一下。

## 逆向分析是何物

逆向工程是一种技术过程，即对一项目标产品进行逆向分析及研究，从而演绎并得出该产品的处理流程、组织结构、功能性能规格等设计要素，以制作出功能相近，但又不完全一样的产品。起源于商业及军事领域中的硬件分析，**其主要目的是，在不能轻易获得必要的生产信息下，直接从成品的分析，推导出产品的设计原理。**（摘自维基百科）

有做过竞品分析的童鞋，想必对逆向分析不会陌生。竞品分析过程大体都是通过反编译Apk安装包获取竞品源码，再通过一些网络抓包方式互相配合来获得竞品的设计实现思路。当然，要想完全获得竞品实现思路还是有一些阻碍的，一方面是 Google 的混淆机制使得反编译后的源码可读性变得很差，另一方面是应用加固手段可以隐藏dex包存在使得反编译无从下手（不过在我折腾过的那些知名app里面，基本没有用过加固的）。运气好的话，你可能真的直接反编译后就可以得到一份没有经过任何混淆的干净源码。例如，某款千万用户级别的电台应用就曾经木有混淆代码，唾手可得，真心暗爽！

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

http://mp.weixin.qq.com/s?__biz=MzA3NTYzODYzMg==&mid=2653576954&idx=1&sn=6826647df10da83c645b2c49cf1326a6&scene=1&srcid=05123rKobhXex7zkEKrSel5t#wechat_redirect

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

## dex2jar

### 常用命令

dex2jar 带的命令如何使用....

### 反编译操作

dex2-jar 逆向 dex 后生成的目录结构信息...

作者分别在 SourceForge、Github 或者 Bitbucket 都托管了一份 dex2-jar ，下面三个链接都是相同的东西，喜欢哪个用哪个

> SourceForge：https://sourceforge.net/projects/dex2jar/
> Github：https://github.com/pxb1988/dex2jar
> Bitbucket：https://bitbucket.org/pxb1988/dex2jar

## jd-gui

http://jd.benow.ca/

https://github.com/java-decompiler/jd-gui

接着上面生成的 jar 包，那要如何查看他们的源代码呢，操作也是非常简单的。直接去到  下载名为 jd-gui 的工具，然后将生成的 jar 包拖曳进去即可查看到对应的源代码。

对比混淆和没混淆过的目录结构的区别。

可以将class文件转换成为Java文件

## jadx

一直还在维护的，好像可以反编译的同时又查看源码。

https://github.com/skylot/jadx

http://blog.csdn.net/coder_pig/article/details/51384286


## 总结

[如何从技术上全面分析一款Android竞品？](http://mp.weixin.qq.com/s?__biz=MzA4MjU5NTY0NA==&mid=402218810&idx=1&sn=1005ca3c2c1e391f7ce4a9851d2722eb&scene=0#wechat_redirect)