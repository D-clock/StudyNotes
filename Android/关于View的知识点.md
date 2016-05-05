# 关于 View 的知识点

记录关于 View 的那些杂七杂八的知识点。

## 触摸事件分发机制

参考文章：

- [公共技术点之 View 事件传递](http://a.codekk.com/detail/Android/Trinea/%E5%85%AC%E5%85%B1%E6%8A%80%E6%9C%AF%E7%82%B9%E4%B9%8B%20View%20%E4%BA%8B%E4%BB%B6%E4%BC%A0%E9%80%92)

分发逻辑如下方伪代码所示，参考自《Android开发艺术探索》的P141：

```java

	public boolean dispatchTouchEvent(MotionEvent ev){
		boolean consume = false;
		if(onInterceptTouchEvent(ev)){
			consume = onTouchEvent(ev);
		} else {
			consume = child.dispatchTouchEvent(ev);
		}
		return consume;
	}

```

## View绘制流程和一些关键函数

确定View的位置：1、左上角坐标；2、宽高尺寸

## MeasureSpec

- MeasureSpec.EXACTLY：明确指定宽高，或者match_parent
- MeasureSpec.AT_MOST：wrap_content


## Scroller

实现滑动效果处理的一大杀器

两篇介绍Scroller不错的文章

- [Android Scroller完全解析，关于Scroller你所需知道的一切](http://blog.csdn.net/guolin_blog/article/details/48719871)
- [Android 带你从源码的角度解析Scroller的滚动实现原理](http://blog.csdn.net/xiaanming/article/details/17483273)

## ViewConfiguration


## VelocityTracker