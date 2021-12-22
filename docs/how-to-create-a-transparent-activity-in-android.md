# 如何在安卓中创建透明活动？

> 原文:[https://www . geesforgeks . org/如何创建透明的安卓活动/](https://www.geeksforgeeks.org/how-to-create-a-transparent-activity-in-android/)

很多时候，我们不得不在我们的应用程序中显示一个功能，我们必须在我们的安卓应用程序中使用透明的活动。在本文中，我们将了解如何在安卓系统中创建透明活动。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将在一个透明的活动中显示一个简单的[文本视图](https://www.geeksforgeeks.org/textview-widget-in-android-using-java-with-examples/)。为了创建一个透明的活动，我们将为我们的活动添加不同的风格。下面给出了一个示例视频，以了解我们将在本文中做什么。请注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-595577-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210420095613/20210420_095525.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210420095613/20210420_095525.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210420095613/20210420_095525.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--text view for displaying textview-->
    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_margin="4dp"
        android:padding="10dp"
        android:text="Welcome to Geeks for Geeks"
        android:textAlignment="center"
        android:textColor="@color/purple_200"
        android:textSize="25sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

**第三步:为本次活动添加自定义风格**

导航至**应用程序>RES>values>themes . XML**并添加以下代码。

## 可扩展标记语言

```
<resources xmlns:tools="http://schemas.android.com/tools">
    <!-- Base application theme. -->
    <style name="Theme.TransparentActivity" parent="Theme.MaterialComponents.DayNight.DarkActionBar">
        <!-- Primary brand color. -->
        <item name="colorPrimary">@color/purple_500</item>
        <item name="colorPrimaryVariant">@color/purple_700</item>
        <item name="colorOnPrimary">@color/white</item>
        <!-- Secondary brand color. -->
        <item name="colorSecondary">@color/teal_200</item>
        <item name="colorSecondaryVariant">@color/teal_700</item>
        <item name="colorOnSecondary">@color/black</item>
        <!-- Status bar color. -->
        <item name="android:statusBarColor" tools:targetApi="l">?attr/colorPrimaryVariant</item>
        <!-- Customize your theme here. -->
    </style>

    <!--add below code in themes.xml file-->
    <!--below is the style for transparent activity and here we are using no action bar.-->
    <style name="Theme.AppCompat.Translucent" parent="Theme.AppCompat.NoActionBar">
        <!--on below line we are setting background as transparent color-->
        <item name="android:background">@android:color/transparent</item>
        <!--on below line we are displaying the windowNotitle as true as we are not displaying our status bar-->
        <item name="android:windowNoTitle">true</item>
        <!--on below line we are setting our window background as transparent color-->
        <item name="android:windowBackground">@android:color/transparent</item>
        <!--on below line we are setting color background cache hint as null-->
        <item name="android:colorBackgroundCacheHint">@null</item>
        <!--on below line we are adding a window translucent as true-->
        <item name="android:windowIsTranslucent">true</item>
        <!--on below line we are adding a window animationstyle-->
        <item name="android:windowAnimationStyle">@android:style/Animation</item>
    </style>

</resources>
```

**第四步:更改 AndroidManifest.xml 文件中的主题**

导航到主题标签中应用程序标签内的**应用程序> AndroidManifest.xml** 在其中添加此样式。

## 可扩展标记语言

```
android:theme="@style/Theme.AppCompat.Translucent"
```

现在运行您的应用程序，并查看应用程序的输出。

**输出:**

<video class="wp-video-shortcode" id="video-595577-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210420095613/20210420_095525.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210420095613/20210420_095525.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210420095613/20210420_095525.mp4)</video>