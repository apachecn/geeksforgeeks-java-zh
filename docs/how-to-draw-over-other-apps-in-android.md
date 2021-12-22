# 如何在安卓中画出其他应用？

> 原文:[https://www . geeksforgeeks . org/如何在安卓中绘制其他应用程序/](https://www.geeksforgeeks.org/how-to-draw-over-other-apps-in-android/)

有时我们要求我们的应用程序在主屏幕上显示一些内容，而不考虑前台运行的应用程序，这个过程被称为绘制其他应用程序。有许多应用程序使用这一功能，以最小的屏幕覆盖范围提供最大的功能。这也使用户能够进行多任务处理。**比如**、Facebook Messenger 的聊天泡泡、YourHour App 的手机过度使用通知、Google 的语音命令等等。我们可以使用安卓软件开发工具包提供的窗口管理器界面创建类似的功能。

### Android WindowManager

安卓窗口管理器是一个系统服务，控制哪些窗口显示以及它们在屏幕上的排列方式。当您启动或关闭应用程序或旋转屏幕时，它会自动执行窗口过渡和动画等操作。

每个活动都有自己的窗口，在屏幕上显示其内容。当您对一个活动执行 setContentView 时，它会将视图添加到该活动的默认窗口中。因为默认窗口会填充屏幕并隐藏任何其他活动，所以窗口管理器会显示顶部的任何窗口。所以，在大多数情况下，你不需要为窗户而烦恼；只需构建活动，安卓将负责其余部分。为了操作窗口，我们需要与窗口管理器交互。现在，为了在其他应用上显示，我们需要创建某种服务，因为当其他应用出现在前台时，活动将会关闭。

### **本文我们要构建什么？**

下面给出一个视频样本，了解一下在本文中我们要做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-615623-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210523135847/outputgfg.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210523135847/outputgfg.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210523135847/outputgfg.mp4)</video>

### 逐步实施

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 AndroidManifest.xml 文件**

为了吸引我们需要的其他应用程序，**android . permission . system _ ALERT _ WINDOW**权限，对于具有 **API 版本> 23** 的 Android，我们需要在运行时请求此权限。Android . permission . system _ ALERT _ WINDOW 允许应用程序使用 WindowManager 类型创建窗口。显示在所有其他应用程序的顶部。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.raghav.gfgwindowmanager">

    <!-- add required permission -->
    <uses-permission android:name="android.permission.FOREGROUND_SERVICE"/>
    <uses-permission android:name="android.permission.SYSTEM_ALERT_WINDOW"/>

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.GFGWindowManager">

        <!-- register the service -->
        <service
            android:name=".ForegroundService"
            android:enabled="true"
            android:exported="true"/>

        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>
```

**步骤 3:使用 activity_main.xml 文件**

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

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Hello World!"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```