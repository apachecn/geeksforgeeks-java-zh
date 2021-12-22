# 如何使用 Firebase 在安卓系统中更改用户密码？

> 原文:[https://www . geeksforgeeks . org/如何更改使用 firebase 的安卓用户密码/](https://www.geeksforgeeks.org/how-to-change-password-of-user-in-android-using-firebase/)

在许多应用程序中，我们有一个使用电子邮件和密码登录的功能。有时我们会忘记密码，大多数时候会重置密码。在这里，我们将使用 **Firebase 身份验证**实现相同的功能来重置我们的密码。你可以参考下面的文章 [**安卓**](https://www.geeksforgeeks.org/user-authentication-using-firebase-in-android/) **使用 Firebase 进行用户认证。** 下面给出一个视频样本，来了解一下我们在这篇文章中要做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-572127-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210308000833/forget.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210308000833/forget.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210308000833/forget.mp4)</video>

### **分步实施**

**第一步:使用 UI 部分**

转到 **activity_login.xml** 文件，参考以下代码。下面是 **activity_login.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".LoginActivity">

    <include
        android:id="@+id/login_toolbar"
        layout="@layout/app_bar_layout" />

    <TextView
        android:id="@+id/textView2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentStart="true"
        android:layout_alignParentTop="true"
        android:layout_marginStart="19dp"
        android:layout_marginTop="96dp"
        android:textSize="25dp"
        android:text="Login to Your Account" />

    <EditText
        android:id="@+id/logemail"
        android:layout_width="267dp"
        android:layout_height="wrap_content"
        android:layout_alignParentStart="true"
        android:layout_alignParentTop="true"
        android:layout_marginStart="36dp"
        android:layout_marginTop="198dp"
        android:ems="10"
        android:hint="Email"
        android:inputType="textEmailAddress" />

    <EditText
        android:id="@+id/logpass"
        android:layout_width="259dp"
        android:layout_height="58dp"
        android:layout_alignParentStart="true"
        android:layout_alignParentTop="true"
        android:layout_marginStart="32dp"
        android:layout_marginTop="261dp"
        android:ems="10"
        android:hint="Password"
        android:inputType="textPassword" />

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:id="@+id/forgetpass"
        android:layout_alignParentStart="true"
        android:layout_alignParentTop="true"
        android:layout_marginStart="132dp"
        android:layout_marginTop="351dp"
        android:text="Forget Password"/>
    <Button
        android:id="@+id/logbut"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentStart="true"
        android:layout_alignParentTop="true"
        android:layout_marginStart="222dp"
        android:layout_marginTop="387dp"
        android:background="@color/colorPrimary"
        android:text="Login"
        android:textSize="15dp" />

</RelativeLayout>
```