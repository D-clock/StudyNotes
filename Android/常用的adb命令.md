# 常用的 adb 命令

随手记一些常用的adb命令

## dumpsys

强大的打印系统信息的命令

```
adb shell dumpsys *** ***
```

## meminfo

打印进程内存的使用信息

```
adb shell dumpsys meminfo processName（or PID）
```

![](http://h.hiphotos.baidu.com/image/pic/item/54fbb2fb43166d22e85daa38412309f79052d270.jpg)

## cpuinfo

打印系统 CPU 的使用信息

```
adb shell dumpsys cpuinfo
```

## intents

获取系统所有 intent 信息 

```
adb shell dumpsys activity intents
```

## intents

获取系统所有 intent 信息 

```
adb shell dumpsys activity intents
```

## broadcasts

获取系统所有 broadcasts 信息 

```
adb shell dumpsys activity broadcasts
```

## providers

获取系统所有 providers 信息 

```
adb shell dumpsys activity providers
```

## activities

获取系统所有 activities 信息 

```
adb shell dumpsys activity activities
```

## processes

获取系统所有 processes 信息 

```
adb shell dumpsys activity processes
```


## services

获取系统(或指定进程)的所有 services 信息 

```
adb shell dumpsys activity services packagename
```

## grep

信息检索过滤

```
grep ***（关键字）
```

例如，过滤出对我们有用的 CPU 信息

![](http://a.hiphotos.baidu.com/image/pic/item/dbb44aed2e738bd40339dd9da68b87d6277ff906.jpg)

## 不错的网站

一个整合一些常用的 adb 命令的网站：http://adbshell.com/