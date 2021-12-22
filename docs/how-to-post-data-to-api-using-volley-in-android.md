# 如何在安卓中使用凌空将数据发布到 API？

> 原文:[https://www . geeksforgeeks . org/如何使用安卓截击将数据发布到 API/](https://www.geeksforgeeks.org/how-to-post-data-to-api-using-volley-in-android/)

我们已经看到在安卓中借助 **GET** 请求使用凌空请求从 API 读取数据。借助 GET Request，我们可以以 [JSON](https://www.geeksforgeeks.org/javascript-json/) 格式显示来自 API 的数据，并在我们的应用程序中使用这些数据。在本文中，我们将看看如何使用安卓系统中的[截击](https://www.geeksforgeeks.org/volley-library-in-android/)库，使用**发布**请求将数据发布到应用编程接口。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将显示两个[编辑文本](https://www.geeksforgeeks.org/edittext-widget-in-android-using-java-with-examples/)字段和一个名称和一个作业，我们将从用户那里获取数据，并将这些数据发布到我们的应用编程接口。为此，我们使用了一个需要免费测试的应用编程接口的示例。下面给出一个视频样本来了解一下我们在本文中要做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-561108-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210214165550/Screenrecorder-2021-02-14-16-54-33-857.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210214165550/Screenrecorder-2021-02-14-16-54-33-857.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210214165550/Screenrecorder-2021-02-14-16-54-33-857.mp4)</video>

数据可以以不同的格式添加到应用编程接口中，如 [XML](https://www.geeksforgeeks.org/xml-basics/) 、表单和 JSON。大多数应用编程接口都以 JSON 格式发布数据。因此，我们也将以 JSON 对象的形式将数据发布到我们的应用编程接口。

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在你的 build.gradle 文件**中添加下面的依赖项

下面是凌空的依赖，我们将使用它从应用编程接口获取数据。要添加此依赖项，请导航至**应用程序>渐变脚本> build.gradle(应用程序)**，并在依赖项部分添加以下依赖项。

> 实现‘com . Android .凌空:凌空:1 . 1 . 1’

添加这个依赖项后，同步你的项目，现在进入 **AndroidManifest.xml** 部分。

**第三步:在 AndroidManifest.xml 文件**中添加互联网权限

导航到**应用程序> AndroidManifest.xml** ，并添加以下代码。

## 可扩展标记语言

```java
<!--permissions for INTERNET-->
<uses-permission android:name="android.permission.INTERNET"/>
```