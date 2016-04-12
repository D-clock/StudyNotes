# 基础入门姿势

记录一些基础入门的小姿势。。。。

## 基本工程目录

下面是一个基本的工程目录结构

![基本工程目录](http://c.hiphotos.baidu.com/image/pic/item/810a19d8bc3eb135c1c4371ca11ea8d3fd1f4412.jpg)

- build：项目编译后生成的class文件
- css：存放项目所需要的css文件
- images：存放项目所需要的图片文件
- js：存放项目所需要的js文件及Javascript库等
- pages：一般存放系统公共的jsp页面，例如header.jsp, footer.jsp等
- content：该目录也是存放项目的jsp页面，出于安全性考虑，该目录应该放在WEB-INF目录下，这样客户端便不能直接访问，可以项目中使用struts或者servlet进行转向访问
- lib：用于存放项目的jar包
- classes：这个子目录用于存储所有Java类文件和相关资源文件
- conf：项目配置文件
- web.xml：Web程序最主要的配置文件

## .gitignore

任性的不使用SVN来做版本控制管理，直接用Git。估计是因为Android用习惯了吧。。。gitignore文件编写如下

```
/build/
```

就这么简单粗暴的一行，忽略**build**目录所有编译生成的文件即可。**.settings**文件夹还是要提交的，不然工程就导入不了了！

## .settings

Web工程目录下生成的.settings文件夹到底是干啥用的，请戳这个 [链接](https://yq.aliyun.com/articles/2597)

## Tomcat

Eclipse 自带的 Tomcat 在哪，duang，看下面！

![Eclipse自带的Tomcat路径](http://d.hiphotos.baidu.com/image/pic/item/4610b912c8fcc3cec04b3c949545d688d53f2089.jpg)

