# 在安卓系统中给吐司添加图像的不同方式

> 原文:[https://www . geesforgeks . org/不同方式添加图像到安卓吐司/](https://www.geeksforgeeks.org/different-ways-to-add-image-to-toast-in-android/)

一条 [**吐司**](https://www.geeksforgeeks.org/toasts-android-studio/) 是一条反馈信息。当整体活动是交互式的并且对用户可见时，它占用很少的显示空间。几秒钟后就消失了。它会自动消失。如果用户想要一条永久的可见消息，可以使用一条 [**通知**](https://www.geeksforgeeks.org/notifications-in-android-oreo-8/) 。另一种吐司是 **定制吐司** ，可以用图像代替简单的信息。所以在这篇文章中，我们要讨论 **三种** 不同的方式来在安卓上给 Toast 添加图片。注意，我们要用 **Java** 语言实现这个项目。

### 方法 1

**步骤 1:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。我们将在****活动 _main.xml** 文件中创建一个简单的[文本视图](https://www.geeksforgeeks.org/textview-widget-in-android-using-java-with-examples/)。**

## ****XML****

```
**<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/show"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="10dp"
        android:text="Show image in Toast"
        android:textSize="22sp"
        android:textStyle="bold" />

</LinearLayout>**
```