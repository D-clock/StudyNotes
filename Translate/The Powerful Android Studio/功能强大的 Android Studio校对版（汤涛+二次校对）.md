# 功能强大的 Android Studio

> 
原文链接：http://saulmm.github.io/the-powerful-android-studio
原文作者：[saulmm](https://github.com/saulmm)
译者：[D_clock爱吃葱花](http://www.jianshu.com/users/ec95b5891948/latest_articles)
校对：[汤涛](https://www.zhihu.com/people/tangtao)（微信公众号AndroidTrending管理员）、[Yasic](https://github.com/Yasic)（电子科技大学在校大学生，Diycode社区管理员）

Android Studio is the official tool for Android development these days. Being developed at the top of project IntelliJ IDEA, takes into advantage (almost in its entirety) features of edition, debugging, analysis, refactor among many other categories for developing in an effective way.

(Android Studio 作为 Android 开发的官方工具已经有一段时间了。考虑到 [IntelliJ IDEA](https://www.jetbrains.com/idea/) 在开发过程中为编辑、调试、分析、重构等众多功能上提供了更高效的方式，为此，Android Studio 选择在 IntelliJ IDEA 的基础上进行开发。)

In the latest version (2.2 at the time of the writing), Android Studio includes a lot of improvements like the new UI editor, interaction with the new ConstraintLayout viewgroup and much more.

(在最新版的 Android Studio 中（写这篇文章时，最新版本是2.2）包含了很多改进， 比如 新的 UI 编辑器、新的 ConstraintLayout 布局交互方式等。)

This article doesn't put the focus on covering these new features. In this one, I would like to give importance to the role that plays IntelliJ IDEA over Android Studio besides a few more tips that I use every day.

（本文的关注点不在于涵盖这些新特性。这次，我想介绍一些自己平时经常使用的 Android Studio 小技巧。）

Because of my last talk given at the amazing event Exfest'16, the intention of this article is to serve as media support (there weren't slides) of the talk, and of course, a new excuse to write a new article. Let's get started!

（这篇文章原本是我在[Exfest'16](http://exfest.es) 活动中的一篇演讲稿(没有PPT)，正好有新的借口来写一篇新文章:) 。让我们开始吧！）

**Disclaimer（声明）**

- All shorcuts shown in this article corresponds to the Mac OS X 10.5+

（文中所有快捷键对应平台： Mac OS X 10.5+）

- The green box which suggests the shotcut used at the bottom of the gifs is a nice plugin called Presentation Assistant, perfect for presentations and pair programming :).

（文中展示快捷键操作的GIF图底部的那个绿框框，是一个很好用的插件，叫[Presentation Assistant](https://plugins.jetbrains.com/plugin/7345)，对用于演示和结对编程是很棒的:)。）

## Miscellaneous（杂项）

### Avoid show the logcat automatically （避免自动显示Logcat窗口）

It could be interesting to disable the expansion of the window Android Monitor during every time when run our app (since the default behavior on a run configuration is to show it).

（在运行应用的时候，最好禁止展开 Android Monitor 窗口（因为在运行配置中默认是展开的））

To achieve this, in the Run Configuration that we are using in our project just disable that tick at `Edit Configurations/Android Application/Miscellaneous.

（为此，可以在我们当前的 Project 中，选择 Edit Configurations -> Android Application -> Miscellaneous 路径，关掉下面的勾选。）

![](http://saulmm.github.io/resources/studio/disable_logcat_on_run.gif)

### No tabs （不显示 Tab）

As Hadi Hadiri rightly says in his article, using tabs could result in the following hassles: loss of context, a valuable space in the editor consumed and the fact that also the interaction with tabs is used to require using the trackpad or the mouse.

（正如 [Hadi Hadiri](https://twitter.com/hhariri) 在他的[文章](http://hadihariri.com/2014/06/24/no-tabs-in-intellij-idea/)中明确提到，使用这些 Tab 可能导致以下麻烦：丢失上下文，消耗宝贵的编辑空间，并且这些标签需要使用触控板或鼠标交互。）

If you believe that tabs don't offer any benefit to you, disable them under settings/editor/tabs setting the Placement preference to None.

（如果这些 Tab 对你来说没有什么用处，可以到 settings -> editor -> tabs 设置中，将 Placement 属性设置为 None。）

![](http://saulmm.github.io/resources/studio/no_tabs.png)

[IntelliJ IDEA](https://www.jetbrains.com/help/idea/2016.1/navigating-through-the-source-code.html) offers many ways to move effectively through the code without need tabs.

（[IntelliJ IDEA](https://www.jetbrains.com/help/idea/2016.1/navigating-through-the-source-code.html) 不需要使用标签也能高效地在代码间进行切换。）

## Navigation（导航）

One of the goals which the JetBrains team encourages to the users is that we have to use the mouse as less as possible. There are tons of actions and commands which allow working in a very effective way without leaving the hands from the keyboard gaining speed and accuracy.

（[JetBrains](https://www.jetbrains.com/)团队的目标之一是鼓励用户尽可能减少使用鼠标的频率。有大量高效的操作命令，可以让你的双手在不需要离开键盘的情况下，变得更加高效精准。）

### Find classes, files, and actions （查找类、文件和操作）

IntelliJ IDEA and, as the result, Android Studio offers solutions finding files, classes, actions.

（[IntelliJ IDEA](https://www.jetbrains.com/idea/) 以及 [Android Studio](http://tools.android.com/recent/androidstudio22preview1available) 都提供了查找文件、类和操作的方案。）

**Search Everywhere - ⇧ + ⇧**（任意搜索 - ⇧ + ⇧）

It shows a dialog for search all types of elements: classes, files, actions, etc. It's recommended to avoid this action and use the specific ones since search everywhere could be slower and expensive in term of your machine resources.

（它会显示一个搜索所有类型元素的对话框：可以用于查找类、文件、操作等。这里建议尽量避免使用这个操作，因为任意查找会使得你宝贵的电脑资源变得更加缓慢。）

**Search types - ⌘ + O**（搜索类型 - ⌘ + O）

It allows finding enumerations, classes, interfaces, etc fastly.

（它可以让你快速地搜索到枚举类型，类，接口等。）

**Search files - ⌘ + ⇧ + O**（搜索文件 - ⌘ + ⇧ + O）

It allows finding every type of files, useful for XML files like layouts, resources, etc.

（它可以让你搜索各种类型的文件，对像布局这样的xml文件，资源文件等同样有用。）

**Search actions - ⇧ + ⌘ + o + A**（搜索操作 - ⇧ + ⌘ + o + A）

It's possible to search and run actions from this feature, actions that live under menus, preferences, tool windows, etc, also suggests the shortcut of some actions, so, if you forget it you can fastly remind it searching for the action.

（通过这个功能，你能搜索并打开菜单、设置、工具窗口等，并且会给出一些操作的快捷键。因此，当你忘记这些操作时，你可以通过搜索这些操作从而快速找到它们。）

![](http://saulmm.github.io/resources/studio/look_for_stuff.gif)

**Bonus:（优点：）**

- It's not necessary to write the full name of whatever we are looking for. If we are searching for a class called CharacterDetailPresenter, we'll find it just typing CharacterPresenter.

（不需要写出我们查找的每一个类的全称。假设我们正在查找CharacterDetailPresenter这个类，那就只需输入CharacterPresenter即可。）

- We can go to a specific line looking for classes (⌘ + O) writing a colon and the number of the line after the searched class name, for example: CharacterDetailPresenter:50.

（搜索类（⌘ + O）的时候，我们可以通过在类名后面添加冒号和行数，来跳转到类中指定的某一行里面，例如：CharacterDetailPresenter:50。）

- If we type / on the beginning of the text of the file that we are looking for, we'll find folders. For example, with /land, the dialog will suggest the folders related to landscape configurations.

（我们搜索文件时，在文件名的前面加“/”，就可以找到该名称对应的目录。例如：输入“/land”，对话框将会提示与landscape相关的配置目录。）

- We can filter the folder which contains the searched file, for example, values-es/strings.xml or values/strings.

（我们可以筛选出包含搜索文件的目录，例如，输入 strings 可以看到 values-es/strings.xml 或者 values/strings.xml。 ）


### Project window - ⌘ + 1（项目窗口 - ⌘ + 1）

For browsing through the project files, a nice solution is to use the project window which can be shown or hidden with the shortcut **⌘ + 1**.

（对于浏览项目文件，有一个不错的方法是通过使用快捷键**⌘ + 1** 来隐藏或者显示我们的项目窗口。）

![](http://saulmm.github.com/resources/studio/show_panel_hide.gif)

**Bonus:（优点：）**

- With ⌘ + ⇧ + ⟵ / ⟶, we can modify the size of the focused panel without using the mouse.

（通过快捷键 **⌘ + ⇧ + ⟵ / ⟶**，我们不用鼠标就能改变当前焦点所在窗口的尺寸。）

- We can perform searches writing the name of the file or folder that we are looking for right in the browser, it will highlight the matches and will restrict the positions selected with the arrows for these matches.

（在浏览界面中，我们可以通过文件或文件夹的名称来搜索，搜索到的匹配项将高亮显示，并且可以通过方向键跳转到指定的匹配项。）

**Jump to navigation bar - ⌘ + ↑ (跳转到导航栏 - ⌘ + ↑)**

The navigation bar is an interesting element to interact with. Using it, we can navigate through the project files as we usually do with the project window. The shortcut **⌘ + ↑** displays the bar and puts the focus into it even if it's disabled.

（导航栏是一个有趣的交互元素。使用它，我们可以方便地浏览项目文件，这与在项目窗口中的操作类似。即使导航栏被禁用，也能通过快捷键 **⌘ + ↑** 重新启动，并获取焦点。）

![](http://saulmm.github.com/resources/studio/jump_to_navigation_bar.gif)

**Bonus:（优势：）**

- We can perform some file operations inside the navigation bar context, like create new files **⌘ + N** or delete them **⌫**.

（我们可以在导航栏的环境下执行某些文件操作，比如，通过快捷键 **⌘ + N** 创建新文件或者使用 **⌫** 删除它们。）

## Show and hide windows（显示和隐藏窗口）

There are different ways to manipulate windows: show and hide a single one, jump to the last active window giving it focus, restore the focus back to the editor when we are using a panel, etc.

（操纵这些窗口有不同的方式：显示和隐藏单个窗口，跳转到上一个活动窗口并使它获得焦点，当使用某个面板时恢复焦点到编辑器等。）

![](http://saulmm.github.io/resources/studio/panels_operations.gif)

**Hide / Restore all windows - ⇧ + ⌘ + F12 （显示或恢复所有窗口 - ⇧ + ⌘ + F12）**

As its name indicates, it allows to hide and restore all visible windows.

（顾名思义，它能够让你隐藏和恢复所有的可视窗口。）

**Jump to Last Tool Window - F12（跳转到上一个工具窗口 - F12）**

Restores the visibility of the last window used, also puts the focus into that tool.

（恢复显示上次使用过的窗口，并使其获得焦点。）

**Back to the editor（返回到编辑器）**

When we have the focus in a window, we can back to the editor without using the mouse with the key ⎋.

（当我们的焦点在某个窗口上，我们可以在不使用鼠标的情况下通过按键 **⎋** 返回到我们的编辑器中。）

## Recently files（最近打开过的文件）

These three actions can help us to save time when we are working with a group of files:

（当我们需要和一堆文件打交道时，这些操作（原文的three actions但实际上只有2个，估计是笔误）可以帮我们节约不少时间：）

**Recently Files - ⌘ + E（最近打开过的文件 - ⌘ + E）**

It shows files that have been opened recently.

（它可以显示出最近打开过的文件。）

**Recently Changed Files - ⌘ + ⇧ + E（最近编辑过的文件 - ⌘ + ⇧ + E）**

It shows files that have been opened and changed recently.

（它可以显示出最近打开并编辑过的文件。）

![](http://saulmm.github.io/resources/studio/recent_files_recent_edited_files.gif)

## Structure of a file（一个文件的结构）

A quick method to navigate through the different attributes and methods in a class is using the action file structure, can be used with shortcut **⌘ + F12**, or finding the action with **⌘ + A** and typing file structure.

(快速导航到一个类中不同属性和方法的方式是使用 file structure 操作，你可以使用快捷键 **⌘ + F12** ，或者使用快捷键 **⌘ + A** 并输入 file structure 。)

This feature, as many other, allows searching on it, allowing find quickly what we are looking for and place the caret accordingly.

（这个功能还有一些其他的特点，它能够执行搜索操作，能够快速得到我们查找的东西并替换相应的字符。）

![](http://saulmm.github.io/resources/studio/look_for_methods.gif)

Similarly, the window structure (⌘ + 7), shows the same information but in a permanent way.

（与上面类似，window structure(⌘ + 7) 在固定位置展示了相同的信息。）

## Show implementations and Super Method（显示当前实现和父类方法）

It's useful, sometimes, to show the current implementations of a superclass, interface or a method. Using **⌘ + B** in the name of the class or method selected, allows, in a glance, check the current implementations navigate to them pressing the ENTER key.

（有时候，显示当前父类、接口或者一个方法的实现是非常有用的。选中类名或方法名并使用快捷键 **⌘ + B**，可以让我们一目了然的看到当前所有的实现，按ENTER键可以跳转到这些实现里面。 ）

Similarly, with the shortcut **⌘ + U** in an implementation, we can navigate to the method or class which is being implemented.

（与上面类似，在一个方法实现里面使用快捷键 **⌘ + U**，也可以跳转到已经被实现的方法或类里面。）

![](http://saulmm.github.io/resources/studio/navigate_implementations_superclass.gif)

## Next Highlighted Error - F2（显示下一个错误 - F2）

When Android Studio highlights some compilation errors, usually we use the mouse to scroll until their location and fix them.

（当 Android Studio 高亮提示某些编译错误时，我们通常都是靠滚动鼠标去定位解决这些错误。）

With IntelliJ IDEA, we can place the care right on the left of the errors using the feature Next Highlighted Error (F2), avoiding leave your hands from your amazing keyboard.

（使用 [IntelliJ IDEA](https://www.jetbrains.com/idea/) 的显示下一个错误（F2）功能，能够迅速的将光标移动到错误前面,从而避免我们把手离开键盘。 ）

![](http://saulmm.github.io/resources/studio/next_error.gif)

First, F2 will iterate the caret over all the errors. Once they are solved, the cursor will be placed left of the warnings according to the current inspection profile.

（首先，按住 F2 会让光标依次移动到每个错误前面。一旦解决某个错误，再按 F2 光标将会移动到当前文件中指定的下一个错误前面。）

## Last Edit Location - ⌘ + ⇧ + ⌫ (返回之前编辑的位置 - ⌘ + ⇧ + ⌫)

When we are changing the code in classes with a huge number of lines, we tend to edit different sections of the class. Put some declarations, edit the body of a method, etc.

（当修改某些代码量很庞大的类时，我们经常需要改变类中不同位置的代码。比如：写一些声明，编辑一下方法的实现等。）

It could be useful after add some declarations place the caret back to the previous edition without using your mouse.

（在你添加声明后，不需要使用鼠标就能将光标移回之前编辑的位置是一个非常实用的功能。）

The action Last Edit Location (⌘ + ⇧ + ⌫), does exactly that. Moves the caret to the previous edition location without changing the code.

（返回之前的编辑位置 (⌘ + ⇧ + ⌫)，正是使用上面所说的操作。它可以在没有更改代码的情况下就让光标移回之前的编辑位置。）

![](http://saulmm.github.io/resources/studio/last_edit_location.gif)


## Edition （编辑代码）

### Replace instead append（替换取代添加）

When we are writing code, usually we use the completion dialog in order to add suggestions.

（在写代码的时候，通常我们为了得到一些代码提示都会使用补全提示对话框。）

When we decide to add a suggestion pressing the ENTER key, the new sentence is added left of the old one, causing an error.

（当我们使用 ENTER 键决定采用某个补全提示时，这段新代码会被添加到原有代码前面，导致产生错误。 ）

![](http://saulmm.github.io/resources/studio/editor_replace_instead_append.gif)

If instead ENTER we press TAB, and if desired method call has the same number of parameters, the new code will be automatically set with the old parameters.

（如果用 TAB 键取代 ENTER 键，并且我们想要调用的方法与原有方法的参数个数相同，那么这些新代码将会自动替换并使用旧的参数设置。）

### Complete Current Statement - ⌘ + ⇧ + ENTER （补全当前语句 - ⌘ + ⇧ + ENTER）

Using a powerful IDE like Android Studio, there is no need to worry about some syntactic elements like braces or semicolons.

（像使用 Android Studio 这样功能强大的 IDE，就没必要去担心一些基本的语法元素，如逗号或者分号。）

![](http://saulmm.github.io/resources/studio/editor_complete_current_statement.gif)

There is an action called Complete Current Statement which automatically add the necessary elements in some contexts.

（某些情况下，使用补全当前语句的操作，它会根据当前情况自动添加一些必要的语法元素。）

### Add Selection To The Next Occurrence - ⌘ + G（添加选项到下一个位置 - ⌘ + G）

In some situations, it could be very effective use multiple carets in order to change multiple sentences at the same time.

（有些情况下，为了能够同时编辑多行代码，同时使用多个光标来是非常高效的。）

We can achieve it, with the feature Add Selection To The Next Occurrence (⌘ + G), selecting the pattern where we want to add carets.

（通过添加选项到下一个位置（⌘ + G）这个功能，我们可以移动光标将选中格式的内容添加到想要的地方。）

Android Studio and IntelliJ IDEA give us even some cool editing tools in this feature, like cut and paste fragments of code, selection tools, etc.

（在这个功能上，[Android Studio](https://developer.android.com/studio/index.html) 和 [IntelliJ IDE](https://www.jetbrains.com/idea/) 甚至还给了一些更酷的编辑工具，比如：剪切和粘贴代码片段，选择工具等。）

![](http://saulmm.github.io/resources/studio/multiple_cursors.gif)

A practical use could be, for instance, changes the binding of our views in an activity or fragment to replace them by ButterKnife annotations.

（举一个使用场景，例如，在Activity或Fragment中使用ButterKnife框架的注解去改变我们绑定View的方式。）

### Join Lines - ⌘ + ⇧ + J（合并成一行 - ⌘ + ⇧ + J）

When there is a string concatenated multiple times in different lines, it could be useful to join those lines into a single one, with the action join lines we'll achieve a single sentence without having to worry about delete the concat operators.

（当一个字符串在不同行上多次连接，使用合并成一行的操作会变得非常有用，它可以将其合并成为一行，并且不用担心需要删除大量的连接符号。）

![](http://saulmm.github.io/resources/studio/join_lines.gif)

### Check the parameters info - ⌘ + P（查看参数信息 - ⌘ + P）

Using the completion for add a call to a method, Android Studio shows a popup with the required parameters, this popup hides after a few seconds.

（添加一个方法的调用，[Android Studio](https://developer.android.com/studio/index.html) 会展示一个调用方法所需参数的弹窗，这个弹窗会在几秒钟后消失。）

Using the action Parameter Info with **⌘ + P**, we can check what parameters are needed for the desired method call every time we want.

（每当调用方法的时候，我们可以使用 **⌘ + P** 来查看方法所需要的参数信息。）

![](http://saulmm.github.io/resources/studio/look_for_parameters.gif)

### Surround With - ⌘ + T（包装代码 - ⌘ + T）

Sometimes, it could be interesting to wrap certain code for evaluating it with a condition, iterate through it or capture an exception.

（某些时候,我们可能需要去包装某些特定的代码，比如：添加一个条件判断,遍历或捕获异常。）

For that purpose, IntelliJ IDEA and in consequence, Android Studio, offers a tasty feature called surround with, operable with a dialog fired by the shortcut **⌘ + T**.

（为此， [IntelliJ IDEA](https://www.jetbrains.com/idea/) 和 [Android Studio](https://developer.android.com/studio/index.html) 提供了一个 Surround with 的功能，使用快捷键 **⌘ + T** 即可调出操作窗口。）

![](http://saulmm.github.io/resources/studio/surround_with.gif)

With that dialog we can choose among different actions: conditions, loops, exceptions, etc, even live templates.

（我们可以在对话框中选择不同的操作，比如：条件、循环、异常等，甚至活动模板。）

**Bonus:（优点:）**

If we fire that dialog in a XML context like a layout file, a few suggestions will be shown. With a bit of ingenuity and a live template we could, for example, wrap a view or viewgroup into another viewgroup, in a very easy way.

（我们在打开XML布局文件的场景下调出对话框，会显示一些提示信息。其中包含少量几个自带的活动模板，比如：通过它可以很简单的做到，把一个 View 或者一个 ViewGroup 放到另一个 ViewGroup 中。）

This is an example of a live template used with the surround with dialog to wrap views insider viewgroups.

（这就是使用活动模板的例子，通过 surround with 弹窗可以将 View 放到 ViewGroup 中。）

![](http://saulmm.github.io/resources/studio/xml_live_template.png)

## Move sentence up/down - ⌘ + ⇧ + ↑/↓ （上下移动代码 - ⌘ + ⇧ + ↑/↓）

In order to move code is not needed to cut and paste sentences manually. The action Move Sentence Up/Down under the selection of a sentence or a group of ones, will be useful to move code in an effective way.

（为了不需要手动复制粘贴的去移动代码。通过快捷键 **⌘ + ⇧ + ↑/↓** 来移动我们选中内容的方式，将是非常高效的。）

![](http://saulmm.github.io/resources/studio/move_up_down.gif)

**Bonus:（优点:）** 

This action could result useful editing layout files in XML. If we select a view, we could move it into an existing viewgroup in the same file.

（这个操作对于编辑XML布局文件的时候非常有用。假如我们选中一个 View，我们可以将其移动到当前布局文件中现有的viewgroup里面。）




## Extend/Shrink selection - ⌥ + ↑/↓（扩展/收缩选择 - ⌥ + ↑/↓）

Android Studio, thanks to IntelliJ IDEA inherits a mechanism really interesting when we select code.

（当我们选中代码时，非常感谢 Android Studio 沿用了 IntelliJ IDEA 这项非常有趣的机制。）

![](http://saulmm.github.io/resources/studio/extend_shrink_selection.gif)

Using the shorcut ⌥ + ↑/↓ in a specific section of the code, will extend or collapse the selection until the next point regarding the nearest scope.

（在代码中的特定部分使用快捷 **⌥+↑/↓** ，被选择的内容将被扩展或折叠，直到最近的范围下一个点。）




## Completition （补全）

**Live templates - ⌘ + J**（活动模板- ⌘ + J）

The live templates are a powerful mechanism to avoid to write boilerplate code. They can be customized with a lot of different options in settings/editor/live templates.

（活动模板是一个功能强大的机制，它可以避免我们编写重复的代码。通过 settings -> editor ->live templates 的步骤可以看到有它很多不同的定制选项。）

![](http://saulmm.github.io/resources/studio/live_templates.gif)

Android Studio, by default, has a lot of live templates ready to use, both for contexts like java and XML.

（[Android Studio](https://developer.android.com/studio/index.html) 默认提供了很多 java 和 XML 都可用的活动模板。）

![](http://saulmm.github.io/resources/studio/available_live_templates.png)

With the shortcut ⌘ + J we can show a dialog with the available live templates for the context where we are.

（通过快捷键 ⌘ + J ，我们可以显示当前情况下可用的活动模板的对话框。）




## Debugging（调试）

### Attach debugger to Android process（调试Android进程）

It could be interesting avoid to run a debug session from Android Studio, (⌃ D), because we have tons of breakpoints configured, we want to force a state before init the debug session, etc.

（避免在 Android Studio 上运行调试会话是非常有意思的，而是使用快捷键⌃ D，因为我们有很多断点配置，在初始化调试会话之前，我们想要状态重置。）

![](http://saulmm.github.io/resources/studio/attach_debugger.gif)

For that, Android Studio includes an action called Attach Debugger to Android Process.

（因此，Android Studio 提供了一个叫 Attach Debugger to Android Process 的操作。）

## Conditional breakpoints（条件断点）

In code which is called multiple times, it could be annoying if our breakpoint is called every time which is fire, and maybe, our purpose is to check that code in a specific situation.
（在被多次调用的代码中，假如我们的断点每次都被启动调用，那将是很烦人的，可能，我们只想去检查特定情况下的代码。）

We can configure the breakpoint for being fired only if a condition returns true, pressing the right click at the breakpoint.

（在断点上点击右键，我们可以配置只有在条件返回true时，才会运行到当前指定的断点。）

![](http://saulmm.github.io/resources/studio/conditional_breakpoint.gif)

The input will open the completion dialog with the context of the breakpoint while typing.

（输入操作会激活弹出条件对话框，在断点场景中输入）

## Force an state（强制指定状态）

When a breakpoint is fired, we usually check the state of the execution. Instead just read we can also write and force the state to enable a certain condition of our code.

（当一个断点被触发时，我们经常会去检查它的执行状态。我们不仅可以读还可以在代码中强制指定一个条件状态。）

![](http://saulmm.github.io/resources/studio/force_state.gif)

With the action evaluate expression (also from the watches window) in edition to check the states of certain variables we can also write the desired value on them.

（在编辑器的 evaluate expression (也包括watches窗口)操作中可以检查到某个特定变量的状态，我们也可以写入一个想要得到的值。）

## Different types of breakpoints（不同类型的断点）

Unsetting the button suspend tick in the breakpoint configuration dialog with a right click on a breakpoint, we could enable the option Log message to console.

（在右键弹出的断点配置对话框中去掉suspend按钮的打勾，我们可以启动 Log message to console 的选项。）

Messages will be print under the tab console at the debug tool window (⌘ + 5).

（消息将在调试工具窗口的控制台选项卡下打印（⌘ + 5)）。）

![](http://saulmm.github.io/resources/studio/breakpoint_types.gif)

Besides, we could print logs with an specific expression, which can be set at the same dialog under the Log Evaluated Expression option. Once again it will suggest sentences of your context with the completion dialog while you are typing the expression.

（此外，我们也可以打印打印指定格式的日志，同样可以在对话框下设置Log Evaluated Expression选项。将再次建议你跟根据上文的句子在对话框中完成输入表达式。）

## Conclusion（总结）

Print the [cheatsheet](https://www.jetbrains.com/idea/docs/IntelliJIDEA_ReferenceCard_Mac.pdf) and hang it to your wall in order to have something to look during your gradle build times (You always could read your code btw! :D).

（为了在gradle构建的时间里有点东西可以看，可以打印这份[小抄](https://www.jetbrains.com/idea/docs/IntelliJIDEA_ReferenceCard_Mac.pdf)并贴到墙上（当然你也可以一直看你的代码！:D)。）

![](http://saulmm.github.com/resources/studio/wall.jpg)

## References（参考文章）

[No tabs in IntelliJ Idea](http://hadihariri.com/2014/06/24/no-tabs-in-intellij-idea/) - Hadi Hadiri

[IntelliJ IDEA Tips and Tricks](https://vimeo.com/138847553) - Hadi Hadiri

[The experts' guide to Android development tools](https://www.youtube.com/watch?v=hHnTIMjd1Y8) - Google I/O '16

[Android Studio for Experts](https://www.youtube.com/watch?v=Y2GC6P5hPeA)- Android Summit '16

[Android studio tips of the day roundups (all of them)](http://www.developerphil.com/android-studio-tips-of-the-day-roundup-6/)- Philippe Breault

[What's new in Android](http://tools.android.com/recent/androidstudio22preview1available)

[Dev tips](https://medium.com/sebs-top-tips)- Sebastiano Poggi