# 使用凌空库

解析安卓系统中的 JSON

> 原文:[https://www . geesforgeks . org/JSON-Android 中解析-使用-凌空-库/](https://www.geeksforgeeks.org/json-parsing-in-android-using-volley-library/)

[JSON](https://www.geeksforgeeks.org/json-full-form/) 也称为(JavaScript Object notification)是一种从服务器交换数据的格式。以 JSON 格式存储的数据是轻量级的，易于处理。在 JSON 的帮助下，我们可以以 JsonArray、JsonObject 和 JsonStringer 的形式访问数据。在本文中，我们将具体看一下在安卓系统中使用[凌空](https://www.geeksforgeeks.org/volley-library-in-android/)实现 JsonObject。

> **JSON Object:** 用“{”大括号开头，用“}”大括号结尾，很容易识别出 JSON Object。我们可以从带有键值的 JSON 对象中获取数据。从那个键，我们可以访问那个键的值。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，在其中我们将显示一个简单的[卡片视图](https://www.geeksforgeeks.org/cardview-in-android-with-example/)，在其中我们将显示一个在极客上为极客提供的单一课程。下面给出了一个示例视频，让我们了解一下在本文中要做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-548244-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210121214223/Screenrecorder-2021-01-21-21-39-44-445.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210121214223/Screenrecorder-2021-01-21-21-39-44-445.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210121214223/Screenrecorder-2021-01-21-21-39-44-445.mp4)</video>

下面是 JSON 对象，我们将从该对象在我们的安卓应用程序中显示数据。

> {
> 
> "库尔塞纳姆":" Fork CPP "，
> 
> “course img”:“https://media . geeksforgeeks . org/img-practice/banner/fork-CPP-thumbnail . png”，
> 
> “课程模式”:“在线批处理”，
> 
> “课程曲目”:“6 首曲目”
> 
> }

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在你的 build.gradle 文件**中添加下面的依赖项

下面是凌空的依赖，我们将使用它从应用编程接口获取数据。要添加此依赖项，请导航至**应用程序>渐变脚本>** [**构建.渐变(应用程序)**](https://www.geeksforgeeks.org/android-build-gradle/) ，并在依赖项部分添加以下依赖项。我们使用了[毕加索](https://www.geeksforgeeks.org/how-to-use-picasso-image-loader-library-in-android/)依赖从网址加载图像。

> //下方线用于截击库
> 
> 实现‘com . Android .凌空:凌空:1 . 1 . 1’
> 
> //下面一行用于图像加载库
> 
> 实现' com.squareup .毕加索:毕加索:2.71828 '

添加这个依赖项后，同步你的项目，现在进入 **AndroidManifest.xml** 部分。

**第三步:在 AndroidManifest.xml 文件**中添加互联网权限

导航到**应用程序> AndroidManifest.xml** ，并添加以下代码。

## 可扩展标记语言

```
<!--permissions for INTERNET-->
<uses-permission android:name="android.permission.INTERNET"/>
```