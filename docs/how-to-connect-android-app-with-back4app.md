# 如何连接安卓 App 和 Back4App？

> 原文:[https://www . geesforgeks . org/how-connect-Android-app-with-back 4 app/](https://www.geeksforgeeks.org/how-to-connect-android-app-with-back4app/)

[Back4App](https://www.back4app.com/) 是另一个著名的后端平台，为不同类型的应用提供后端服务，无论是 web、安卓还是 IOS 设备。Back4App 也为我们提供了类似于 [Firebase](https://www.geeksforgeeks.org/firebase-introduction/) 的服务。我们已经看到在安卓应用中使用[Firebase](https://www.geeksforgeeks.org/adding-firebase-to-android-app/)。在本文中，我们将在[安卓工作室](https://www.geeksforgeeks.org/android-studio-main-window/)中查看在您的安卓应用中添加 Back4App。我们将构建一个简单的应用程序，其中我们将连接我们的安卓应用程序和 Back4App。

### **Back4App**

Back4App 是开发人员的社区中最优秀、最受欢迎的 Parse 替代品之一。使用开源解析服务器构建、托管、和管理应用程序是一种简单的方法。基于高效的开源后端框架 Parse Server，Back4App 有几个丰富的功能:

*   **Featured Parse Server** : Back4app uses Parse Server as its core product, because it is the best framework for back-end development, which can help developers save valuable time in building applications.
*   **Enhanced server performance** : It supports intelligent database indexing, query optimizer, automatic expansion, automatic backup and redundant storage capacity.
*   **Easy deployment** : Back4app is a ready-made platform. You can set up your application in less than 5 minutes.
*   **Real-time database and analysis** : Provide real-time data storage and synchronization. Real-time analysis is a key function.
*   **Within your budget** : Predictable pricing, transparent and easy to budget.
*   **Strong technical support team** : Back4app's engineering support can help users at any time.

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:添加依赖和 JitPack 存储库**

导航到**渐变脚本>build . grade le(模块:应用)**，并在依赖项部分添加以下依赖项。

> 实现“com.github.parse-community。解析-SDK-Android:解析:1 . 26 . 0”

将 JitPack 存储库添加到构建文件中。将其添加到 allprojects{ }部分内存储库末尾的根 [build.gradle](https://www.geeksforgeeks.org/android-build-gradle/) 中。

> *all projects {*
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

现在同步您的项目，我们准备将 Back4App 添加到我们的应用程序中。

**第三步:在 AndroidManifest.xml 文件**中添加互联网权限

导航到**应用程序> AndroidManifest.xml** ，并在其中添加以下代码。

## XML

```
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
<uses-permission android:name="android.permission.INTERNET"/>
```