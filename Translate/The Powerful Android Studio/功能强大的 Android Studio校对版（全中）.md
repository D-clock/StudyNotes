# 功能强大的 Android Studio

> 
原文链接：http://saulmm.github.io/the-powerful-android-studio
原文作者：[saulmm](https://github.com/saulmm)
译者：[D_clock爱吃葱花](http://www.jianshu.com/users/ec95b5891948/latest_articles)
校对：[汤涛](https://www.zhihu.com/people/tangtao)（就职于海豚浏览器，微信公众号AndroidTrending管理员）、[Yasic](https://github.com/Yasic)（电子科技大学在校大学生，Diycode社区管理员）

Android Studio 作为 Android 开发的官方工具已经有一段时间了。考虑到 [IntelliJ IDEA](https://www.jetbrains.com/idea/) 在开发过程中为编辑、调试、分析、重构等众多功能上提供了更高效的方式，为此，Android Studio 选择在 IntelliJ IDEA 的基础上进行开发。在最新版的 Android Studio 中（写这篇文章时，最新版本是2.2）包含了很多改进， 比如 新的 UI 编辑器、新的 ConstraintLayout 布局交互方式等。本文的关注点不在于涵盖这些新特性。这次，我想介绍一些自己平时经常使用的 Android Studio 小技巧。这篇文章原本是我在[Exfest'16](http://exfest.es) 活动中的一篇演讲稿(没有PPT)，正好有新的借口来写一篇新文章:) 。让我们开始吧！

**声明**

- 文中所有快捷键对应平台： Mac OS X 10.5+

- 文中展示快捷键操作的GIF图底部的那个绿框框，是一个很好用的插件，叫[Presentation Assistant](https://plugins.jetbrains.com/plugin/7345)，对用于演示和结对编程是很棒的:)。

## 杂项

### 避免自动显示Logcat窗口

在运行应用的时候，最好禁止展开 Android Monitor 窗口（因为在运行配置中默认是展开的）。为此，可以在我们当前的 Project 中，选择 Edit Configurations -> Android Application -> Miscellaneous 路径，关掉下面的勾选。

![](http://saulmm.github.io/resources/studio/disable_logcat_on_run.gif)

### 不显示 Tab

正如 [Hadi Hadiri](https://twitter.com/hhariri) 在他的[文章](http://hadihariri.com/2014/06/24/no-tabs-in-intellij-idea/)中明确提到，使用这些 Tab 可能导致以下麻烦：丢失上下文，消耗宝贵的编辑空间，并且这些标签需要使用触控板或鼠标交互。如果这些 Tab 对你来说没有什么用处，可以到 settings -> editor -> tabs 设置中，将 Placement 属性设置为 None。

![](http://saulmm.github.io/resources/studio/no_tabs.png)

[IntelliJ IDEA](https://www.jetbrains.com/help/idea/2016.1/navigating-through-the-source-code.html) 不需要使用标签也能高效地在代码间进行切换。

## 导航

[JetBrains](https://www.jetbrains.com/)团队的目标之一是鼓励用户尽可能减少使用鼠标的频率。有大量高效的操作命令，可以让你的双手在不需要离开键盘的情况下，变得更加高效精准。

### 查找类、文件和操作

[IntelliJ IDEA](https://www.jetbrains.com/idea/) 以及 [Android Studio](http://tools.android.com/recent/androidstudio22preview1available) 都提供了查找文件、类和操作的方案。

**任意搜索 - ⇧ + ⇧**

它会显示一个搜索所有类型元素的对话框：可以用于查找类、文件、操作等。这里建议尽量避免使用这个操作，因为任意查找会使得你宝贵的电脑资源变得更加缓慢。

**搜索类型 - ⌘ + O**

它可以让你快速地搜索到枚举类型，类，接口等。

**搜索文件 - ⌘ + ⇧ + O**

它可以让你搜索各种类型的文件，对像布局这样的xml文件，资源文件等同样有用。

**搜索操作 - ⇧ + ⌘ + o + A**

通过这个功能，你能搜索并打开菜单、设置、工具窗口等，并且会给出一些操作的快捷键。因此，当你忘记这些操作时，你可以通过搜索这些操作从而快速找到它们。

![](http://saulmm.github.io/resources/studio/look_for_stuff.gif)

**优点：**

- 不需要写出我们查找的每一个类的全称。假设我们正在查找CharacterDetailPresenter这个类，那就只需输入CharacterPresenter即可。

- 搜索类（⌘ + O）的时候，我们可以通过在类名后面添加冒号和行数，来跳转到类中指定的某一行里面，例如：CharacterDetailPresenter:50。

- 我们搜索文件时，在文件名的前面加“/”，就可以找到该名称对应的目录。例如：输入“/land”，对话框将会提示与landscape相关的配置目录。

- 我们可以筛选出包含搜索文件的目录，例如，输入 strings 可以看到 values-es/strings.xml 或者 values/strings.xml。 


### 项目窗口 - ⌘ + 1

对于浏览项目文件，有一个不错的方法是通过使用快捷键**⌘ + 1** 来隐藏或者显示我们的项目窗口。

![](http://saulmm.github.com/resources/studio/show_panel_hide.gif)

**优点：**

- 通过快捷键 **⌘ + ⇧ + ⟵ / ⟶**，我们不用鼠标就能改变当前焦点所在窗口的尺寸。

- 在浏览界面中，我们可以通过文件或文件夹的名称来搜索，搜索到的匹配项将高亮显示，并且可以通过方向键跳转到指定的匹配项。

**跳转到导航栏 - ⌘ + ↑**

导航栏是一个有趣的交互元素。使用它，我们可以方便地浏览项目文件，这与在项目窗口中的操作类似。即使导航栏被禁用，也能通过快捷键 **⌘ + ↑** 重新启动，并获取焦点。

![](http://saulmm.github.com/resources/studio/jump_to_navigation_bar.gif)

**优势：**

- 我们可以在导航栏的环境下执行某些文件操作，比如，通过快捷键 **⌘ + N** 创建新文件或者使用 **⌫** 删除它们。

## 显示和隐藏窗口

操纵这些窗口有不同的方式：显示和隐藏单个窗口，跳转到上一个活动窗口并使它获得焦点，当使用某个面板时恢复焦点到编辑器等。

![](http://saulmm.github.io/resources/studio/panels_operations.gif)

**显示或恢复所有窗口 - ⇧ + ⌘ + F12**

顾名思义，它能够让你隐藏和恢复所有的可视窗口。

**跳转到上一个工具窗口 - F12**

恢复显示上次使用过的窗口，并使其获得焦点。

**返回到编辑器**

当我们的焦点在某个窗口上，我们可以在不使用鼠标的情况下通过按键 **⎋** 返回到我们的编辑器中。

## 最近打开过的文件

当我们需要和一堆文件打交道时，这些操作可以帮我们节约不少时间：

**最近打开过的文件 - ⌘ + E**

它可以显示出最近打开过的文件。

**最近编辑过的文件 - ⌘ + ⇧ + E**

它可以显示出最近打开并编辑过的文件。

![](http://saulmm.github.io/resources/studio/recent_files_recent_edited_files.gif)

## 一个文件的结构

快速导航到一个类中不同属性和方法的方式是使用 file structure 操作，你可以使用快捷键 **⌘ + F12** ，或者使用快捷键 **⌘ + A** 并输入 file structure 。这个功能还有一些其他的特点，它能够执行搜索操作，能够快速得到我们查找的东西并替换相应的字符。

![](http://saulmm.github.io/resources/studio/look_for_methods.gif)

与上面类似，window structure(⌘ + 7) 在固定位置展示了相同的信息。

## 显示当前实现和父类方法

有时候，显示当前父类、接口或者一个方法的实现是非常有用的。选中类名或方法名并使用快捷键 **⌘ + B**，可以让我们一目了然的看到当前所有的实现，按ENTER键可以跳转到这些实现里面。 

与上面类似，在一个方法实现里面使用快捷键 **⌘ + U**，也可以跳转到已经被实现的方法或类里面。

![](http://saulmm.github.io/resources/studio/navigate_implementations_superclass.gif)

## 显示下一个错误 - F2

当 Android Studio 高亮提示某些编译错误时，我们通常都是靠滚动鼠标去定位解决这些错误。使用 [IntelliJ IDEA](https://www.jetbrains.com/idea/) 的显示下一个错误（F2）功能，能够迅速的将光标移动到错误前面,从而避免我们把手离开键盘。

![](http://saulmm.github.io/resources/studio/next_error.gif)

首先，按住 F2 会让光标依次移动到每个错误前面。一旦解决某个错误，再按 F2 光标将会移动到当前文件中指定的下一个错误前面。

## 返回之前编辑的位置 - ⌘ + ⇧ + ⌫

当修改某些代码量很庞大的类时，我们经常需要改变类中不同位置的代码。比如：写一些声明，编辑一下方法的实现等。在你添加声明后，不需要使用鼠标就能将光标移回之前编辑的位置是一个非常实用的功能。返回之前的编辑位置 (⌘ + ⇧ + ⌫)，正是使用上面所说的操作。它可以在没有更改代码的情况下就让光标移回之前的编辑位置。

![](http://saulmm.github.io/resources/studio/last_edit_location.gif)

## 编辑代码

### 替换取代添加

在写代码的时候，通常我们会为了得到一些代码提示而使用补全提示对话框。当我们使用 ENTER 键决定采用某个补全提示时，这段新代码会被添加到原有代码前面，导致产生错误。

![](http://saulmm.github.io/resources/studio/editor_replace_instead_append.gif)

如果用 TAB 键取代 ENTER 键，并且我们想要调用的方法与原有方法的参数个数相同，那么这些新代码将会自动替换并使用旧的参数设置。

### 补全当前语句 - ⌘ + ⇧ + ENTER

像使用 Android Studio 这样功能强大的 IDE，就没必要去担心一些基本的语法元素，如逗号或者分号。

![](http://saulmm.github.io/resources/studio/editor_complete_current_statement.gif)

某些情况下，使用补全当前语句的操作，它会根据当前情况自动添加一些必要的语法元素。

### 添加选中内容到下一个位置 - ⌘ + G

有些情况下，为了能够同时编辑多行代码，同时使用多个光标来是非常高效的。通过添加选中内容到下一个位置（⌘ + G）这个功能，我们可以移动光标将选中格式的内容添加到想要的地方。在这个功能上，[Android Studio](https://developer.android.com/studio/index.html) 和 [IntelliJ IDE](https://www.jetbrains.com/idea/) 甚至还给了一些更酷的编辑工具，比如：剪切和粘贴代码片段，选择工具等。

![](http://saulmm.github.io/resources/studio/multiple_cursors.gif)

举一个使用场景，例如，在Activity或Fragment中使用ButterKnife框架的注解去改变我们绑定View的方式。

### 合并成一行 - ⌘ + ⇧ + J

当一个字符串在不同行上多次连接，使用合并成一行的操作会变得非常有用，它可以将其合并成为一行，并且不用担心需要删除大量的连接符号。

![](http://saulmm.github.io/resources/studio/join_lines.gif)

### 查看参数信息 - ⌘ + P

添加一个方法的调用，[Android Studio](https://developer.android.com/studio/index.html) 会展示一个调用方法所需参数的弹窗，这个弹窗会在几秒钟后消失。每当调用方法的时候，我们可以使用 **⌘ + P** 来查看方法所需要的参数信息。

![](http://saulmm.github.io/resources/studio/look_for_parameters.gif)

### 包装代码 - ⌘ + T

某些时候,我们可能需要去包装某些特定的代码，比如：添加一个条件判断,遍历或捕获异常。为此， [IntelliJ IDEA](https://www.jetbrains.com/idea/) 和 [Android Studio](https://developer.android.com/studio/index.html) 提供了一个 Surround with 的功能，使用快捷键 **⌘ + T** 即可调出操作窗口。

![](http://saulmm.github.io/resources/studio/surround_with.gif)

我们可以在对话框中选择不同的操作，比如：条件、循环、异常等，甚至活动模板。

**优点:**

我们在打开XML布局文件的场景下调出对话框，会显示一些提示信息。其中包含少量几个自带的活动模板，比如：通过它可以很简单的做到，把一个 View 或者一个 ViewGroup 放到另一个 ViewGroup 中。这就是使用活动模板的例子，通过 surround with 弹窗可以将 View 放到 ViewGroup 中。

![](http://saulmm.github.io/resources/studio/xml_live_template.png)

## 上下移动代码 - ⌘ + ⇧ + ↑/↓

为了不需要手动复制粘贴的去移动代码。通过快捷键 **⌘ + ⇧ + ↑/↓** 来移动我们选中内容的方式，将是非常高效的。

![](http://saulmm.github.io/resources/studio/move_up_down.gif)

**优点:** 

这个操作对于编辑XML布局文件的时候非常有用。假如我们选中一个 View，我们可以将其移动到当前布局文件中现有的viewgroup里面。

## 扩大/缩小选择区域 - ⌥ + ↑/↓

由于继承了 [IntelliJ IDEA](https://www.jetbrains.com/idea/) 的机制,[Android Studio](https://developer.android.com/studio/index.html) 使得我们在圈选代码的时候变得非常有趣。

![](http://saulmm.github.io/resources/studio/extend_shrink_selection.gif)

在特定部分代码上使用快捷键 **⌥+↑/↓** ，可以扩大或缩小到下一个选中的区域范围。

## 补全

**活动模板- ⌘ + J**

活动模板是一个功能强大的机制，它可以避免我们编写重复的代码。通过 settings -> editor ->live templates 的步骤可以看到有它很多不同的定制选项。

![](http://saulmm.github.io/resources/studio/live_templates.gif)

[Android Studio](https://developer.android.com/studio/index.html) 默认提供了很多 java 和 XML 都可使用的活动模板。

![](http://saulmm.github.io/resources/studio/available_live_templates.png)

通过快捷键 ⌘ + J ，我们可以看到一个显示当前可用活动模板的对话框。

## 调试

### 将调试器依附到Android进程

[Android Studio](https://developer.android.com/studio/index.html) 可以避免每次都以 Debug 的方式启动进程，(⌃ D),因为我们有大量的断点不需要在一开始就进入 Debug 的状态。

![](http://saulmm.github.io/resources/studio/attach_debugger.gif)

为此，[Android Studio](https://developer.android.com/studio/index.html) 提供了一个名字叫 Attach Debugger to Android Process 的操作。

## 条件断点

在被多次调用的代码中，每次都执行到我们设置的断点是非常麻烦的，有可能，我们只想在某种特定情况下才去检查这段代码的运行状态。在断点上点击右键进行设置，只有在条件返回true时，才会运行到我们当前设置的断点。

![](http://saulmm.github.io/resources/studio/conditional_breakpoint.gif)

Android Studio 会根据输入内容弹出补全提示对话框。

## 指定一个状态

当运行到某个断点时，我们经常会去检查它的运行状态。现在不仅可以读取这些状态信息，还可以输入运行特定的某些代码。

![](http://saulmm.github.io/resources/studio/force_state.gif)

我们可以在 evaluate expression (也可以在watches窗口中) 编辑窗口中输入变量，去查看它们的状态信息。

## 不同类型的断点

在右键弹出的断点配置对话框中关闭 suspend 按钮的打勾，并勾选 Log message to console 选项。这样，就能在调试工具中的 console 窗口中输出相应的日志信息（⌘ + 5)。

![](http://saulmm.github.io/resources/studio/breakpoint_types.gif)

此外，我们同样可以在对话框下设置 Log Evaluated Expression 选项来打印指定格式的日志。Android Studio 会再次根据你输入的语句弹出补全提示对话框。

## 总结

为了在gradle构建的时间里有点东西可以看，可以把这份[小抄](https://www.jetbrains.com/idea/docs/IntelliJIDEA_ReferenceCard_Mac.pdf)打印并贴到墙上（当然你也可以一直看着你的代码！:D)。

![](http://saulmm.github.com/resources/studio/wall.jpg)

## References（参考文章）

[No tabs in IntelliJ Idea](http://hadihariri.com/2014/06/24/no-tabs-in-intellij-idea/) - Hadi Hadiri

[IntelliJ IDEA Tips and Tricks](https://vimeo.com/138847553) - Hadi Hadiri

[The experts' guide to Android development tools](https://www.youtube.com/watch?v=hHnTIMjd1Y8) - Google I/O '16

[Android Studio for Experts](https://www.youtube.com/watch?v=Y2GC6P5hPeA)- Android Summit '16

[Android studio tips of the day roundups (all of them)](http://www.developerphil.com/android-studio-tips-of-the-day-roundup-6/)- Philippe Breault

[What's new in Android](http://tools.android.com/recent/androidstudio22preview1available)

[Dev tips](https://medium.com/sebs-top-tips)- Sebastiano Poggi