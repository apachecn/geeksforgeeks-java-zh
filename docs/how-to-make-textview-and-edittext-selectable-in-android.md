# 如何在安卓中让 TextView 和 EditText 可选？

> 原文:[https://www . geesforgeks . org/how-make-textview-and-edit text-可选于安卓/](https://www.geeksforgeeks.org/how-to-make-textview-and-edittext-selectable-in-android/)

在本文中，我们将实现一个与 TextView 相关的非常重要的特性。在使用任何社交媒体应用程序或使用脸书时，你可能已经看到有一种特殊类型的文本视图，你不能像人们在帖子上写的标题一样复制它。您可以选择消息，但很少有文本不能选择或复制。所以在这里，我们将学习如何实现这个特性。

## 为文本视图实现此功能

### **方法 1**

**步骤 1:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## XML

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="20dp"
    android:gravity="center"
    android:orientation="vertical"
    tools:context=".SelectText">

    <TextView
        android:id="@+id/select"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Geeks For Geeks "
        android:layout_alignParentTop="true"
        android:layout_centerHorizontal="true"
        android:textSize="30dp" />

</LinearLayout>
```