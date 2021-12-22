# 在社交媒体安卓应用中实现首页搜索特定博客和注销功能

> 原文:[https://www . geesforgeks . org/implementing-search-for-a-specific-blog-on-home-page-and-登出-功能-in-social-media-Android-app/](https://www.geeksforgeeks.org/implementing-search-for-a-specific-blog-on-home-page-and-logout-functionality-in-social-media-android-app/)

这是**“在安卓工作室构建社交媒体 App”**教程的**第 7 部分**，我们将在本文中介绍以下功能:

*   We will search blogs on the homepage.
*   If there are few blogs in our application, it is easy to manually search blogs. But when we have 1000 blogs, searching a specific blog becomes a very complicated and time-consuming task.
*   That's why we want to implement this function, and use the provided title or description to search blog **.**
*   Similarly, we have implemented the **logout function** in this paper.

### **分步实施**

**第一步:在菜单文件夹**中创建一个注销和搜索按钮

转到 **app > res >菜单>右键单击>新建>菜单资源文件**，并将文件命名为**主 _ 菜单**。下面是**主菜单. xml** 文件的代码。

## XML

```java
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto">

    <item
        android:id="@+id/logout"
        android:title="Logout">
    </item>

    <item
        android:id="@+id/search"
        android:icon="@drawable/ic_search"
        android:title="Search"
        app:actionViewClass="android.widget.SearchView"
        app:showAsAction="always">
    </item>

</menu>
```