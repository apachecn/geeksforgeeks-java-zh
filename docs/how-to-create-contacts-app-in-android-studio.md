# 如何在安卓工作室创建联系人 App？

> 原文:[https://www . geesforgeks . org/如何创建联系人-app-in-android-studio/](https://www.geeksforgeeks.org/how-to-create-contacts-app-in-android-studio/)

android 设备中的联系人应用程序是安装在你的 android 设备上的系统应用程序。不同的设备有不同的联系人应用程序界面。在本文中，我们将了解如何在[安卓工作室](https://www.geeksforgeeks.org/android-studio-main-window/)中构建自己的联系人应用程序。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，在其中显示存储在用户设备中的联系人列表。除此之外，我们还将添加一个功能来保存新的联系人，使用搜索栏从列表中过滤联系人，等等。下面是视频，我们将在其中看到我们将在本文中构建的内容。

<video class="wp-video-shortcode" id="video-581205-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210325143710/20210325_143459.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210325143710/20210325_143459.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210325143710/20210325_143459.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:添加依赖和 JitPack 存储库**

由于我们必须请求用户的权限才能在应用程序中显示设备上的联系人，因此我们必须请求用户的权限。所以为了获得用户的权限，我们将在运行时使用 Dexter 来获得用户的权限。为了使用 Dexter，我们还将使用文本可绘制依赖项来显示可绘制内部的文本，现在我们已经在 [build.gradle](https://www.geeksforgeeks.org/android-build-gradle/) 文件中添加了以下依赖项。导航至**梯度脚本>构建.梯度(模块:应用)**并在依赖项部分添加以下依赖项。

> *实现‘com . github . mukeshlanki:photo filter:1 . 0 . 2’*
> 
> 实现' com.karumi:dexter:6.2.2 '

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

现在同步您的项目，我们将进一步处理 AndroidManifest.xml 文件。

**第三步:在 AndroidManifest.xml** 中添加权限

导航至**应用程序> AndroidManifest.xml** 文件，并添加以下权限。代码中添加了注释，以便更详细地了解。

## 可扩展标记语言

```java
<!--permissions to read contacts-->
<uses-permission android:name="android.permission.READ_CONTACTS" />
<!--permissions to write contacts-->
<uses-permission android:name="android.permission.WRITE_CONTACTS" />
<!--permissions to make a call-->
<uses-permission android:name="android.permission.CALL_PHONE"/>
<!--permissions to send sms-->
<uses-permission android:name="android.permission.SEND_SMS" />
<!--permissions to write sms-->
<uses-permission android:name="android.permission.WRITE_SMS"/>
```