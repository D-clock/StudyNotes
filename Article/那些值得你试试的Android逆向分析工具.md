# 那些值得你试试的 Android 逆向分析工具

介绍自己最近的情况，和写作本文的目的，说说写文的一点点收获。

## 什么是逆向分析

简单介绍逆向分析的概念

## Apk打包简介

简单的介绍Apk打包的原理，还有什么二次打包和混淆防范之类的。

从[ Android 官方文档](https://developer.android.com/studio/build/index.html)

![](http://a.hiphotos.baidu.com/image/pic/item/8b13632762d0f703997dbdcf00fa513d2797c5d1.jpg)

我们知道了apk安装包的由来后，就可以愉快的了解下面将要介绍的一些逆向分析工具了。

## apktool

apktool的作用和使用方式

apktool逆向apk后生成的目录

apktool使用中有哪些需要注意的坑

运行命令，进行反编译操作后，却在控制台窗口中报了下面这些错误。

![](http://g.hiphotos.baidu.com/image/pic/item/267f9e2f0708283801981a00b099a9014c08f109.jpg)

去到反编译结果文件生成目录下，并没有发现任何有价值的东西。额，不得不佩服自己，一些文章就能踩坑，之前反编译都是顺风顺水的。直接把问题丢给 Google ，原来是 apktool 版本的问题，之前在电脑上一直都用着 apktool 反编译东西，写这篇文章的时候又下了最新版本的 apktool 就出现问题了（**貌似只要在同一平台下使用过不同版本的 apktool，都会出现差不多类似报错的问题**），解决方案就是去到下面的路径下：

> C:\Users\Administrator（你本机用户名，不一定是Administrator）\apktool\framework

删除 1.apk 文件

![](http://h.hiphotos.baidu.com/image/pic/item/500fd9f9d72a60596a252d0e2034349b033bbae9.jpg)

然后重新执行反编译命令，一切就就恢复正常了。

![](http://b.hiphotos.baidu.com/image/pic/item/d50735fae6cd7b897f0bf497072442a7d9330ebb.jpg)

和 apktool 的作者提供的示例完全吻合

![](http://h.hiphotos.baidu.com/image/pic/item/aa18972bd40735fa391380ad96510fb30e2408c7.jpg)

去到生成反编译结果的目录下，就可以看到我们成功反编译后所有生成的文件和目录了

![](http://e.hiphotos.baidu.com/image/pic/item/2fdda3cc7cd98d1075dcc725293fb80e7bec909e.jpg)

什么是smali语言

smali语句可以用来调试

apktool原本是具有调试 Smali 代码的功能，但在 2.0.3 版本开始，作者就已经标记打算废弃此功能，到 2.1.0 版本就已经将其完全移除掉。但这并不意味着我们就无法去调试这些 Smali 代码了，Smali 的作者早已为我们准备好了一款用于调试 Smali 代码的插件 [SmaliIdea](https://github.com/JesusFreke/smali/wiki/smalidea) 。目前 SmaliIdea 最新的版本是 0.03，喜欢玩耍的童鞋可以到下面的下载地址中：

> https://bitbucket.org/JesusFreke/smali/downloads

找到最新版的 SmaliIdea 进行安装使用

![](http://g.hiphotos.baidu.com/image/pic/item/50da81cb39dbb6fdb40e3d320124ab18972b3749.jpg)

忘了补充一点，**这个插件是基于 IntelliJ IDEA 和 Android Studio 的**，还在使用 ADT 开发的童鞋就爱莫能助了。关于 apktool 的介绍就大致到这里，更多使用技巧可以自行 Google 或者直奔下面的官方站点

> http://ibotpeaches.github.io/Apktool/

## dex2jar + jd-gui

dex2jar的作用和使用方式

dex2-jar逆向dex后生成的文件信息

作者分别在 SourceForge、Github 或者 Bitbucket 都托管了一份 dex2-jar ，下面三个链接都是相同的东西，喜欢哪个用哪个

> SourceForge：https://sourceforge.net/projects/dex2jar/
> Github：https://github.com/pxb1988/dex2jar
> Bitbucket：https://bitbucket.org/pxb1988/dex2jar

顺便献上 jd-gui 的下载地址

> http://jd.benow.ca/


## enjarify

> 官方地址：https://github.com/google/enjarify

## ClassyShark

> 官方地址：https://github.com/google/android-classyshark

## Procyon

![](http://h.hiphotos.baidu.com/image/pic/item/ac6eddc451da81cb8e96acde5a66d016092431b4.jpg)

> 官方地址：https://bitbucket.org/mstrobel/procyon

## TcpDump


## WireShark

## 总结