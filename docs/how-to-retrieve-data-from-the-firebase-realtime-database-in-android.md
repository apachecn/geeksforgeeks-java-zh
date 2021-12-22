# 如何在安卓中从 Firebase 实时数据库中检索数据？

> 原文:[https://www . geeksforgeeks . org/如何从 firebase-实时数据库中检索数据安卓/](https://www.geeksforgeeks.org/how-to-retrieve-data-from-the-firebase-realtime-database-in-android/)

[**Firebase 实时数据库**](https://www.geeksforgeeks.org/firebase-realtime-database-with-operations-in-android-with-examples/) 是谷歌提供的后端服务，用于为你的安卓应用、IOS 应用以及你的网站处理后端任务。它提供了许多服务，如存储、数据库等等。 [Firebase](https://www.geeksforgeeks.org/firebase-introduction/) 的特色是其 Firebase 实时数据库。通过在应用程序中使用 Firebase 实时数据库，您可以向用户提供实时数据更新，而无需实际刷新应用程序。因此，在本文中，我们将创建一个简单的应用程序，其中我们将使用 Firebase 实时数据库，并从 Firebase 实时数据库中检索数据，并将在我们的应用程序中看到实时数据的变化。

### 我们将在本文中构建什么？

我们将构建一个简单的安卓应用程序，其中我们将显示一个简单的文本视图。在[文本视图](https://www.geeksforgeeks.org/textview-widget-in-android-using-java-with-examples/)中，我们将显示来自 Firebase 的数据。我们将通过在服务器端实际更改数据来了解实时数据更改如何在我们的应用程序中发生。请注意，我们将使用 **Java** 语言来实现这个项目。

> **注意:**你也可以参考[如何在安卓中保存数据到 Firebase 实时数据库？](https://www.geeksforgeeks.org/how-to-save-data-to-the-firebase-realtime-database-in-android/)

**分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:将你的应用连接到 Firebase**

创建新项目后，导航到顶部栏上的“工具”选项。点击火焰基地。点击 Firebase 后，你可以看到截图中下面提到的右栏。

![](img/8cef8a02ae49cbbf1ea2a1dffd166e59.png)

在该列中，导航到 Firebase 实时数据库。点击那个选项，你会看到两个选项:连接应用程序到 Firebase 和添加 Firebase 实时数据库到你的应用程序。单击立即连接，您的应用程序将连接到 Firebase。之后点击第二个选项，现在你的应用程序连接到 Firebase。

![](img/36dfe5f64980ac9bec1621a98e633b69.png)

完成此过程后，您将看到下面的屏幕。

![](img/4bbbe5e8d7654fe9df363866823da315.png)

现在验证您的应用程序是否连接到 Firebase。转到您的 [build.gradle](https://www.geeksforgeeks.org/android-build-gradle/) 文件。导航到应用程序>渐变脚本> build.gradle 文件，并确保下面的依赖项已添加到您的依赖项部分。

> 实现' com . Google . firebase:firebase-数据库:19.6.0 '

如果上述依赖项没有添加到您的依赖项部分。添加此依赖项并同步您的项目。现在，我们将转向应用程序的 XML 部分。

**步骤 3:使用 activity_main.xml 文件**

转到 **activity_main.xml** 文件，参考以下代码。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/idTVRetrieveData"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:text="Retrieve Data"
        android:textAlignment="center"
        android:textColor="@color/purple_500"
        android:textSize="18sp" />

</RelativeLayout>
```

**第四步:在你的 AndroidManifest.xml 文件中添加互联网权限**

在 AndroidManifest.xml 文件中添加互联网权限。

## 可扩展标记语言

```
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```