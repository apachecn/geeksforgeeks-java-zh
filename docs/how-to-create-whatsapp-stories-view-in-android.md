# 如何在安卓中创建 WhatsApp 故事视图？

> 原文:[https://www . geesforgeks . org/how-create-whatsapp-stories-view-in-Android/](https://www.geeksforgeeks.org/how-to-create-whatsapp-stories-view-in-android/)

故事现在正成为许多不同应用程序中最常见的功能之一，如 WhatsApp、LinkedIn、Instagram 等。在本文中，我们将看看如何在我们的安卓应用程序中创建类似类型的视图。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将创建一个故事视图，我们可以在 WhatsApp 上看到。我们将添加一些固定的图像。下面给出一个视频样本，了解一下在本文中我们要做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-591563-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210409221543/Screenrecorder-2021-04-09-22-13-45-251.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210409221543/Screenrecorder-2021-04-09-22-13-45-251.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210409221543/Screenrecorder-2021-04-09-22-13-45-251.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:添加依赖和 JitPack 存储库**

导航到**渐变脚本>构建.渐变(模块:应用)**，并在依赖项部分添加以下依赖项。

> 实现' com . github . shts:storieprogressview:3 . 0 . 0 '

将 JitPack 存储库添加到构建文件中。将其添加到 allprojects{ }部分内存储库末尾的 root build.gradle 中。

> *所有项目{*
> 
> *存储库{*
> 
> *……*
> 
> *maven { URL " https://jitpack . io " }*
> 
> *}*
> 
> *}*

添加这个依赖项后，同步您的项目，现在我们将开始实现它。

**第三步:将主题更新到 themes.xml 文件**中的 NoActionBar

导航到**应用程序> res >值> themes.xml** 并在其中将基本应用程序主题更改为**无功能栏**。您可以在下面看到 **themes.xml** 文件的代码。

## 可扩展标记语言

```java
<resources xmlns:tools="http://schemas.android.com/tools">
    <!-- Base application theme. -->
    <style name="Theme.GFGParse" parent="Theme.MaterialComponents.DayNight.NoActionBar">
        <!-- Primary brand color. -->
        <item name="colorPrimary">@color/purple_500</item>
        <item name="colorPrimaryVariant">@color/purple_700</item>
        <item name="colorOnPrimary">@color/white</item>
        <!-- Secondary brand color. -->
        <item name="colorSecondary">@color/teal_200</item>
        <item name="colorSecondaryVariant">@color/teal_700</item>
        <item name="colorOnSecondary">@color/black</item>
        <!--below is the text color-->
        <item name="android:textColor">@color/black</item>
        <!-- Status bar color. -->
        <item name="android:statusBarColor" tools:targetApi="l">?attr/colorPrimaryVariant</item>
        <!-- Customize your theme here. -->
    </style>
</resources>
```