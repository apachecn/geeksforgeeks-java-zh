# 如何在安卓系统中使用谷歌图书 API 搭建图书库 App？

> 原文:[https://www . geesforgeks . org/how-to-build-a-book-library-app-use-Google-books-API-in-Android/](https://www.geeksforgeeks.org/how-to-build-a-book-library-app-using-google-books-api-in-android/)

如果你正在寻找构建一个**图书库应用程序**，并且你想加载大量的图书数据，那么为了添加这个功能，你必须使用一个简单的由谷歌提供的应用编程接口，当然，这是免费的。在本文中，我们将看看这个应用编程接口在我们的安卓应用程序中的实现。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，在其中我们将搜索不同类型的书籍，我们将在[recycle view](https://www.geeksforgeeks.org/android-recyclerview/)中看到与该主题相关的书籍列表。为了搜索这些书籍，我们将使用谷歌提供的免费应用编程接口，该接口拥有大量书籍。下面给出了一个示例视频，让我们了解一下在本文中要做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-546017-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210116234958/Screenrecorder-2021-01-16-23-46-06-36.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210116234958/Screenrecorder-2021-01-16-23-46-06-36.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210116234958/Screenrecorder-2021-01-16-23-46-06-36.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在你的渐变文件**中添加凌空的依赖

导航到**应用程序>渐变脚本>构建.渐变**文件，并在“依赖项”部分添加下面的依赖项。

> 实现‘com . Android .凌空:凌空:1 . 1 . 1’
> 
> 实现' com.squareup .毕加索:毕加索:2.71828 '

在您的 gradle 文件中添加以下依赖项后，现在同步您的项目，现在我们将转向我们的 **activity_main.xml** 文件。因为我们将使用[截击](https://www.geeksforgeeks.org/volley-library-in-android/)从我们的应用编程接口获取数据，使用[毕加索](https://www.geeksforgeeks.org/image-loading-caching-library-android-set-1/)图像加载库从网址加载图像。

**第三步:添加互联网权限**

导航到**应用程序> AndroidManifest.xml** ，并添加以下权限。

## 可扩展标记语言

```
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```