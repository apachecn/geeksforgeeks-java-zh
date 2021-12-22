# 如何在安卓系统中搭建照片查看应用？

> 原文:[https://www . geesforgeks . org/如何在安卓中构建照片查看应用/](https://www.geeksforgeeks.org/how-to-build-a-photo-viewing-application-in-android/)

**Gallery 应用程序**是最常用的应用程序之一，它预装在许多安卓设备上，在 Google Play 中有几个不同的应用程序可以查看设备中的媒体文件。在这篇文章中，我们将简单地创建一个图库应用程序，在其中我们可以查看我们存储在设备上的所有照片。除此之外，我们还可以在应用程序中查看个人照片。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将简单地显示网格格式的照片列表，点击照片，我们可以查看该照片，并可以放大照片以正确查看。下面是视频 0，在视频 0 中，我们将看到我们将在本文中构建什么。

<video class="wp-video-shortcode" id="video-575535-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210316161357/20210316_161245.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210316161357/20210316_161245.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210316161357/20210316_161245.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在 build.gradle 文件**中添加依赖项

导航到**应用程序>渐变脚本> build.gradle(:应用程序)**并向其中添加以下依赖项。我们正在使用[毕加索](https://www.geeksforgeeks.org/how-to-use-picasso-image-loader-library-in-android/)从我们的[图像视图](https://www.geeksforgeeks.org/imageview-in-android-with-example/)中的路径加载图像。

> //下面是使用毕加索图像加载库的依赖项
> 
> 实现' com.squareup .毕加索:毕加索:2.71828 '

现在同步您的项目，我们将在 **AndroidManifest.xml** 文件中添加权限。

**第三步:在我们的 AndroidManifest.xml 文件**中添加权限

导航至**应用程序> AndroidManifest.xml** 文件，并添加以下权限。

## 可扩展标记语言

```
<!-- permissions for reading external storage -->
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
```