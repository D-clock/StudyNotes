# 功能强大的 Android Studio

> 
原文链接：http://saulmm.github.io/the-powerful-android-studio
原文作者：[saulmm](https://github.com/saulmm)
译者：[D_clock爱吃葱花](http://www.jianshu.com/users/ec95b5891948/latest_articles)
校对：[]()

Android Studio is the official tool for Android development these days. Being developed at the top of project IntelliJ IDEA, takes into advantage (almost in its entirety) features of edition, debugging, analysis, refactor among many other categories for developing in an effective way.（Android Studio 作为 Android 开发的官方工具已经有一段时间了。它是在 [IntelliJ IDEA](https://www.jetbrains.com/idea/) 项目的基础上进行开发的，考虑到它在开发过程中为编辑、调试、分析、重构等众多功能上提供了更高效的方式。）

In the latest version (2.2 at the time of the writing), Android Studio includes a lot of improvements like the new UI editor, interaction with the new ConstraintLayout viewgroup and much more.（在最新版的 Android Studio 中（写这篇文章时，最新版本是2.2）包含了很多像新的 UI 编辑器、新的 ConstraintLayout 布局等更多交互方式上的改进。）

This article doesn't put the focus on covering these new features. In this one, I would like to give importance to the role that plays IntelliJ IDEA over Android Studio besides a few more tips that I use every day.（本文的关注点不在于涵盖这些新特性。这次，我想介绍一些自己平时经常使用的 Android Studio 小技巧。）

Because of my last talk given at the amazing event Exfest'16, the intention of this article is to serve as media support (there weren't slides) of the talk, and of course, a new excuse to write a new article. Let's get started!（
因为我在惊人的事件Exfest'16给出最后一次谈话中，这篇文章的用意是作为媒体支持（有没有幻灯片）的谈话，当然，一个新的借口来写一个新的文章:) 。让我们开始吧！）

**Disclaimer（声明）**

- All shorcuts shown in this article corresponds to the Mac OS X 10.5+（本文展示的所有快捷键对应的 Mac OS X 10.5+ 操作系统）
- The green box which suggests the shotcut used at the bottom of the gifs is a nice plugin called Presentation Assistant, perfect for presentations and pair programming :).（绿盒子这表明在GIF文件的底部使用的快捷键是一个很好的插件，叫做演示助手，完美的演示文稿和结对编程:)。）


## Miscellaneous（杂项）

### Avoid show the logcat automatically （避免自动显示Logcat窗口）

It could be interesting to disable the expansion of the window Android Monitor during every time when run our app (since the default behavior on a run configuration is to show it).（每当我们运行应用程序的时候，禁用 Android Monitor 窗口的展开是一件很有意思的事情（因为在运行配置中默认是显示的）

To achieve this, in the Run Configuration that we are using in our project just disable that tick at `Edit Configurations/Android Application/Miscellaneous.（为了避免自动显示Logcat窗口，在我们当前正在使用的 Project 中，去到 Edit Configurations -> Android Application -> Miscellaneous 路径下关掉下面的打勾。）

![](http://saulmm.github.io/resources/studio/disable_logcat_on_run.gif)

### No tabs （不显示标签）

As Hadi Hadiri rightly says in his article, using tabs could result in the following hassles: loss of context, a valuable space in the editor consumed and the fact that also the interaction with tabs is used to require using the trackpad or the mouse.（正如 [Hadi Hadiri](https://twitter.com/hhariri) 在他的[文章](http://hadihariri.com/2014/06/24/no-tabs-in-intellij-idea/)中明确提到，使用标签可能导致以下麻烦：丢失上下文，消耗宝贵的编辑空间，并且这些标签是需要使用触控板或鼠标才能起到相互作用。）

If you believe that tabs don't offer any benefit to you, disable them under settings/editor/tabs setting the Placement preference to None.（如果这些标签对你来说没有什么用处，你可以通过去到 settings -> editor -> tabs 设置中，将 Placement 属性设置为 None。）

![](http://saulmm.github.io/resources/studio/no_tabs.png)

IntelliJ IDEA offers many ways to move effectively through the code without need tabs.（IntelliJ IDEA 提供了很多不需要使用到标签而又行之有效的方式。）

## Navigation（导航）

One of the goals which the JetBrains team encourages to the users is that we have to use the mouse as less as possible. There are tons of actions and commands which allow working in a very effective way without leaving the hands from the keyboard gaining speed and accuracy.（[JetBrains](https://www.jetbrains.com/)团队的目标之一是鼓励用户尽可能减少使用鼠标的频率。有大量高效的操作命令，可以让你的双手在不需要离开键盘的情况下，变得更加高效精准。）

### Find classes, files, and actions

IntelliJ IDEA and, as the result, Android Studio offers solutions finding files, classes, actions.

**Search Everywhere - ⇧ + ⇧**

It shows a dialog for search all types of elements: classes, files, actions, etc. It's recommended to avoid this action and use the specific ones since search everywhere could be slower and expensive in term of your machine resources.

**Search types - ⌘ + O**

It allows finding enumerations, classes, interfaces, etc fastly.

**Search files - ⌘ + ⇧ + O**

It allows finding every type of files, useful for XML files like layouts, resources, etc.

**Search actions - ⇧ + ⌘ + o + A**

It's possible to search and run actions from this feature, actions that live under menus, preferences, tool windows, etc, also suggests the shortcut of some actions, so, if you forget it you can fastly remind it searching for the action.

![](http://saulmm.github.io/resources/studio/look_for_stuff.gif)

**Bonus:**

- It's not necessary to write the full name of whatever we are looking for. If we are searching for a class called CharacterDetailPresenter, we'll find it just typing CharacterPresenter.

- We can go to a specific line looking for classes (⌘ + O) writing a colon and the number of the line after the searched class name, for example: CharacterDetailPresenter:50.

- If we type / on the beginning of the text of the file that we are looking for, we'll find folders. For example, with /land, the dialog will suggest the folders related to landscape configurations.

- We can filter the folder which contains the searched file, for example, values-es/strings.xml or values/strings.


**Project window - ⌘ + 1**

For browsing through the project files, a nice solution is to use the project window which can be shown or hidden with the shortcut ⌘ + 1.

![](http://saulmm.github.com/resources/studio/show_panel_hide.gif)

**Bonus:**

- With ⌘ + ⇧ + ⟵ / ⟶, we can modify the size of the focused panel without using the mouse.

- We can perform searches writing the name of the file or folder that we are looking for right in the browser, it will highlight the matches and will restrict the positions selected with the arrows for these matches.

**Jump to navigation bar - ⌘ + ↑**

The navigation bar is an interesting element to interact with. Using it, we can navigate through the project files as we usually do with the project window. The shortcut ⌘ + ↑ displays the bar and puts the focus into it even if it's disabled.

![](http://saulmm.github.com/resources/studio/jump_to_navigation_bar.gif)

**Bonus:**

- We can perform some file operations inside the navigation bar context, like create new files ⌘ + N or delete them ⌫.

## Show and hide windows

There are different ways to manipulate windows: show and hide a single one, jump to the last active window giving it focus, restore the focus back to the editor when we are using a panel, etc.

![](http://saulmm.github.io/resources/studio/panels_operations.gif)

**Hide / Restore all windows - ⇧ + ⌘ + F12**

As its name indicates, it allows to hide and restore all visible windows.

**Jump to Last Tool Window - F12**

Restores the visibility of the last window used, also puts the focus into that tool.

**Back to the editor**

When we have the focus in a window, we can back to the editor without using the mouse with the key ⎋.

## Recently files

These three actions can help us to save time when we are working with a group of files:

**Recently Files - ⌘ + E**

It shows files that have been opened recently.

**Recently Changed Files - ⌘ + ⇧ + E**

It shows files that have been opened and changed recently.

![](http://saulmm.github.io/resources/studio/recent_files_recent_edited_files.gif)

## Structure of a file

A quick method to navigate through the different attributes and methods in a class is using the action file scructure, can be used with shortcut ⌘ + F12, or finding the action with ⌘ + A and typing file structure.

This feature, as many other, allows searching on it, allowing find quickly what we are looking for and place the caret accordingly.

![](http://saulmm.github.io/resources/studio/look_for_methods.gif)

Similarly, the window structure (⌘ + 7), shows the same information but in a permanent way.

## Show implementations and Super Method

It's useful, sometimes, to show the current implementations of a superclass, interface or a method. Using ⌘ + B in the name of the class or method selected, allows, in a glance, check the current implementations navigate to them pressing the ENTER key.

Similarly, with the shortcut ⌘ + U in an implementation, we can navigate to the method or class which is being implemented.

![](http://saulmm.github.io/resources/studio/navigate_implementations_superclass.gif)

## Next Highlighted Error - F2

When Android Studio highlights some compilation errors, usually we use the mouse to scroll until their location and fix them.

With IntelliJ IDEA, we can place the care right on the left of the erros using the feature Next Highlighted Error (F2), avoiding leave your hands from your amazing keyboard.

![](http://saulmm.github.io/resources/studio/next_error.gif)

First, F2 will iterate the caret over all the errors. Once they are solved, the cursor will be placed left of the warnings according to the current inspection profile.

## Las Edit Location - ⌘ + ⇧ + ⌫ - Last Edit Location

When we are changing the code in classes with a huge number of lines, we tend to edit different sections of the class. Put some declarations, edit the body of a method, etc.

It could be useful after add some declarations place the caret back to the previous edition without using your mouse.

The action Last Edit Location (⌘ + ⇧ + ⌫), does exactly that. Moves the caret to the previous edition location without changing the code.

！[](http://saulmm.github.io/resources/studio/last_edit_location.gif)


## Edition

### Replace instead append

When we are writing code, usually we use the completion dialog in order to add suggestions.

When we decide to add a suggestion pressing the ENTER key, the new sentence is added left of the old one, causing an error.

![](http://saulmm.github.io/resources/studio/editor_replace_instead_append.gif)

If instead ENTER we press TAB, and if desired method call has the same number of parameters, the new code will be automatically set with the old parameters.

### Complete Current Statement - ⌘ + ⇧ + ENTER - Complete Current Statement

Using a powerful IDE like Android Studio, there is no need to worry about some syntactic elements like braces or semicolons.

![](http://saulmm.github.io/resources/studio/editor_complete_current_statement.gif)

There is an action called Complete Current Statement which automatically add the necessary elements in some contexts.

### Add Selection To The Next Ocurrence - ⌘ + G

In some situations, it could be very effective use multiple carets in order to change multiple sentences at the same time.

We can achieve it, with the feature Add Selection To The Next Ocurrence (⌘ + G), selecting the pattern where we want to add carets.

Android Studio and IntelliJ IDEA give us even some cool editing tools in this feature, like cut and paste fragments of code, selection tools, etc.

![](http://saulmm.github.io/resources/studio/multiple_cursors.gif)

A practical use could be, for instance, changes the binding of our views in an activity or fragment to replace them by ButterKnife annotations.

### Join Lines - ⌘ + ⇧ + J

When there is a string concatenated multiple times in different lines, it could be useful to join those lines into a single one, with the action join lines we'll achieve a single sentence without having to worry about delete the concat operators.

![](http://saulmm.github.io/resources/studio/join_lines.gif)

### Check the parameters info - ⌘ + P

Using the completion for add a call to a method, Android Studio shows a popup with the required parameters, this popup hides after a few seconds.

Using the action Parameter Info with ⌘ + P, we can check what parameters are needed for the desired method call every time we want.

![](http://saulmm.github.io/resources/studio/look_for_parameters.gif)

### Surround With - ⌘ + T

Sometimes, it could be interesting to wrap certain code for evaluating it with a condition, iterate through it or capture an exception.

For that purpose, IntelliJ IDEA and in consequence, Android Studio, offers a tasty feature called surround with, operable with a dialog fired by the shortcut ⌘ + T.

![](http://saulmm.github.io/resources/studio/surround_with.gif)

With that dialog we can choose among different actions: conditions, loops, exceptions, etc, even live templates.

**Bonus:**

If we fire that dialog in a XML context like a layout file, a few suggestions will be shown. With a bit of ingenuity and a live template we could, for example, wrap a view or viewgroup into another viewgroup, in a very easy way.

This is an example of a live template used with the surround with dialog to wrap views insider viewgroups.

![](http://saulmm.github.io/resources/studio/xml_live_template.png)

## Move sentence up/down - ⌘ + ⇧ + ↑/↓

In order to move code is not needed to cut and paste sentences manually. The action Move Sentence Up/Down under the selection of a sentence of a group of ones, will be useful to move code in an effective way.

![](http://saulmm.github.io/resources/studio/move_up_down.gif)

**Bonus**

This action could result useful editing layout files in XML. If we select a view, we could move it into an existing viewgroup in the same file.

## Extend/Shrink selection - ⌥ + ↑/↓

Android Studio, thanks to IntelliJ IDEA inherits a mechanism really interesting whe we select code.

![](http://saulmm.github.io/resources/studio/extend_shrink_selection.gif)

Using the shorcut ⌥ + ↑/↓ in a specific section of the code, will extend or collapse the selection until the next point regarding the nearest scope.

## Completition

**Live templates - ⌘ + J**

The live templates are a powerful mechanism to avoid to write boilerplate code. They can be customized with a lot of different options in settings/editor/live templates.

![](http://saulmm.github.io/resources/studio/live_templates.gif)

Android Studio, by default, has a lot of live templates ready to use, both for contexts like java and XML.

![](http://saulmm.github.io/resources/studio/available_live_templates.png)

With the shortcut ⌘ + J we can show a dialog with the available live templates for the context where we are.

## Debugging

### Attach debugger to Android process

It could be interesting avoid to run a debug session from Android Studio, (⌃ D), because we have tons of breakpoints configured, we want to force a state before init the debug session, etc.

![](http://saulmm.github.io/resources/studio/attach_debugger.gif)

For that, Android Studio includes an action called Attach Debugger to Android Process.

## Conditional breakpoints

In code which is called multiple times, it could be annoying if our breakpoint is called every time which is fire, and maybe, our purpose is to check that code in a specific situation.

We can configure the breakpoint for being fired only if a condition returns true, pressing the right click at the breakpoint.

![](http://saulmm.github.io/resources/studio/conditional_breakpoint.gif)

The input will open the completion dialog with the context of the breakpoint while typing.

## Force an state

When a breakpoint is fired, we usually check the state of the execution. Instead just read we can also write and force the state to enable a certain condition of our code.

![](http://saulmm.github.io/resources/studio/force_state.gif)

With the action evaulate expression (also from the watches window) in adition to check the states of certain variables we can also write the desired value on them.

## Different types of breakpoints

Unsetting the button suspend tick in the breakpoint configuration dialog with a right click on a breakpoint, we could enable the option Log message to console.

Messages will be print under the tab console at the debug tool window (⌘ + 5).

![](http://saulmm.github.io/resources/studio/breakpoint_types.gif)

Besides, we could print logs with an specific expression, which can be set at the same dialog under the Log Evaluated Expression option. Once again it will suggest sentences of your context with the completion dialog while you are typing the expression.

## Conclusion

Print the cheatsheet and hang it to your wall in order to have something to look during your gradle build times (You always could read your code btw! :D).

![](http://saulmm.github.com/resources/studio/wall.jpg)

## References（参考文章）

[No tabs in IntelliJ Idea](http://hadihariri.com/2014/06/24/no-tabs-in-intellij-idea/) - Hadi Hadiri

[IntelliJ IDEA Tips and Tricks](https://vimeo.com/138847553) - Hadi Hadiri

[The experts' guide to Android development tools](https://www.youtube.com/watch?v=hHnTIMjd1Y8) - Google I/O '16

[Android Studio for Experts](https://www.youtube.com/watch?v=Y2GC6P5hPeA)- Android Summit '16

[Android studio tips of the day roundups (all of them)](http://www.developerphil.com/android-studio-tips-of-the-day-roundup-6/)- Philippe Breault

[What's new in Android](http://tools.android.com/recent/androidstudio22preview1available)

[Dev tips](https://medium.com/sebs-top-tips)- Sebastiano Poggi