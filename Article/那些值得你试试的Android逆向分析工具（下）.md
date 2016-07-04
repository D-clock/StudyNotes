# 那些值得你试试的 Android 逆向分析工具

承接上文，接着往下写。

## enjarify

Google 开源的一个逆向分析工具

Enjarify使用说明 http://wiki.wooyun.org/android:tools:enjarify

要把bat文件里面的python3改成python

注意要使用相对路径，不要使用全路径

为什么不用 dex2jar ，详见README.md

![](http://e.hiphotos.baidu.com/image/pic/item/8644ebf81a4c510fa5371e0d6859252dd42aa532.jpg)

从官方的说明上看，enjarify 相较于 dex2jar 做了更多的优化处理，去避免在逆向得到jar包的过程中出错。虽然我在使用 dex2jar 的过程中还没遇到过出错的情况，但是在使用 enjarify 时，确实感受到相对更加方便的地方。例如：可以直接对apk进行逆向操作，而不需要先解压提取classes.dex，特别是针对那些本来就不止一个dex包的大型应用；

以反编译微信这种多dex包的apk为例子

而 enjarfy 也并非万能的，官方文档也提到了它目前存在的一些限制，如暂时还无法逆向获得源文件的属性、行数和注释等。（需要验证一下是不是无法获得注释）

![](http://d.hiphotos.baidu.com/image/pic/item/8c1001e93901213f23b2a1cb5ce736d12f2e9520.jpg)

当然，相信 Google 的工程师也会尽力去优化改善 enjarfy 的功能，还是很值得期待的。

> 官方地址：https://github.com/google/enjarify

## ClassyShark

ClassyShark 的两个比较主要的作用：1、分析一个apk的实现用了什么技术；2、检查apk中的方法数，可以查看到什么地方导致了65K方法；

命令怎么用，可以参考官方文档，最主要的还是第一个分析apk的命令

参考文章：

http://www.jianshu.com/p/8e8b88ea2197

http://w4lle.github.io/2016/02/15/ClassyShark%E2%80%94%E2%80%94%E5%88%86%E6%9E%90apk%E5%88%A9%E5%99%A8/#rd

源码地址：https://github.com/google/android-classyshark

官方使用指南：https://github.com/borisf/classyshark-user-guide

jar包下载地址：https://github.com/google/android-classyshark/releases

官方命令行使用PDF手册：https://github.com/google/android-classyshark/blob/master/CommandLine.pdf

官网地址：http://classyshark.com/

## Procyon

![](http://h.hiphotos.baidu.com/image/pic/item/ac6eddc451da81cb8e96acde5a66d016092431b4.jpg)

介绍常用命令，它能够更强的还原代码的逻辑结构

介绍它相对于其他逆向工具的好处

http://blog.csdn.net/zhaokaiqiang1992/article/details/45038125

> 官方地址：https://bitbucket.org/mstrobel/procyon

## TcpDump

需要root吗？支持http和https吗？

http://blog.csdn.net/zhaokaiqiang1992/article/details/45038125

http://mrpeak.cn/blog/tutorial-tcpdump/

tcpdump命令：http://liuzhigong.blog.163.com/blog/static/1782723752012851043396/

用命令行装载 tcpdum，拉取打印文件。

## Fiddler

需要root吗？支持http和https吗？

http://www.trinea.cn/android/android-network-sniffer/

据说 Mac 下的童鞋使用 [Charles](https://www.charlesproxy.com/) 会更爽，额，我是 Windows 用户，Mac 下的童鞋就自行折腾吧。

## WireShark

一些基本的操作和命令

https://www.wireshark.org/

http://blog.csdn.net/zhaokaiqiang1992/article/details/45038125

http://www.trinea.cn/android/tcpdump_wireshark/

## 总结

[如何从技术上全面分析一款Android竞品？](http://mp.weixin.qq.com/s?__biz=MzA4MjU5NTY0NA==&mid=402218810&idx=1&sn=1005ca3c2c1e391f7ce4a9851d2722eb&scene=0#wechat_redirect)