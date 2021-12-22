# 如何在社交媒体安卓 App 中添加博客？

> 原文:[https://www . geesforgeks . org/how-add-blogs-in-social-media-Android-app/](https://www.geeksforgeeks.org/how-to-add-blogs-in-social-media-android-app/)

这是 **【在 Android Studio 上构建社交媒体 App】**教程的 **第 5 部分** ，我们将在本文中介绍以下功能:

*   We will add any user's blog. Here we will work in **Add Blog Segment** , and the user will add a blog with a title, description and images related to the blog.
*   If the user does not write any title or description, then we will display an error.

### 逐步实施

**第一步:使用 fragment_add_blogs.xml 文件**

在此页面上将有两个编辑文本来输入标题和描述，以及一个图像视图，用户将在其中选择一个图像。导航到 **app > res >布局>fragment _ add _ blogs . XML**并将下面的代码添加到该文件中。下面是 **片段 _add_blogs.xml** 文件的代码。

## XML

```java
<?xml version="1.0" encoding="utf-8"?>
<ScrollView 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".AddBlogsFragment">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="2dp"
        android:orientation="vertical">

        <EditText
            android:id="@+id/ptitle"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:background="@drawable/edit"
            android:hint="Enter Title"
            android:minHeight="80dp"
            android:padding="10dp"
            android:singleLine="true" />

        <ImageView
            android:id="@+id/imagep"
            android:layout_width="match_parent"
            android:layout_height="200dp"
            android:layout_marginTop="15dp"
            android:background="@drawable/edit"
            android:src="@drawable/ic_images" />

        <EditText
            android:id="@+id/pdes"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginTop="15dp"
            android:background="@drawable/edit"
            android:gravity="start"
            android:hint="Enter Description"
            android:inputType="textCapSentences|textMultiLine"
            android:minHeight="120dp"
            android:padding="10dp"
            android:singleLine="true" />

        <Button
            android:id="@+id/pupload"
            style="@style/Widget.AppCompat.Button.Colored"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_gravity="end"
            android:layout_marginTop="20sp"
            android:text="Upload"
            android:textAlignment="center" />
    </LinearLayout>

</ScrollView>
```