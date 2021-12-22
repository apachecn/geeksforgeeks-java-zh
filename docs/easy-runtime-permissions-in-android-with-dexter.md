# 用 Dexter 轻松实现安卓运行时权限

> 原文:[https://www . geesforgeks . org/easy-runtime-permissions-in-Android-with-dexter/](https://www.geeksforgeeks.org/easy-runtime-permissions-in-android-with-dexter/)

在[棉花糖](https://www.geeksforgeeks.org/difference-between-android-1-0-and-android-6-0-1/)中引入的安卓中的**运行时权限，由于这些运行时权限，用户可以在运行时授予应用程序权限，同时编写运行时权限的代码。有时处理请求权限的任务变得非常困难，开发人员不得不编写大量的代码。因此，我们将使用**德克斯特**在安卓系统中实现运行时权限。**

### 安卓系统中的 Dexter 是什么？

**Dexter** 是帮助我们在 Android 中轻松处理运行时权限的库。现在我们将在我们的安卓应用程序中看到这一点的实现。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，向用户显示一个按钮。点击该按钮后，我们将向用户显示运行时权限。因此，如果用户拒绝该权限，那么我们将显示打开设置屏幕并授予权限的选项。下面是一个短视频，在这个视频中，我们将看到我们将在这篇文章中构建什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-543675-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210112235708/Screenrecorder-2021-01-12-23-55-36-154.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210112235708/Screenrecorder-2021-01-12-23-55-36-154.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210112235708/Screenrecorder-2021-01-12-23-55-36-154.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在 build.gradle 文件**中添加 Dexter 运行时权限的依赖关系

导航到梯度脚本，然后导航到构建.梯度(模块)级别。在 dependencies 部分的 build.gradle 文件中添加以下行。

> 实现' com.karumi:dexter:6.2.2 '

添加此依赖项后，现在同步您的项目。让我们转向 XML 部分。

**步骤 3:使用 activity_main.xml 文件**

转到 **activity_main.xml** 文件，参考以下代码。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <!--Button to request permissions-->
    <Button
        android:id="@+id/idBtnRequestPermission"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:text="Request Permission"
        android:textAllCaps="false" />

</RelativeLayout>
```