# 在社交媒体安卓应用中实现对特定博客功能的评论

> 原文:[https://www . geesforgeks . org/implement-comment-on-a-special-blog-functional-in-social-media-Android-app/](https://www.geeksforgeeks.org/implement-comment-on-a-particular-blog-functionality-in-social-media-android-app/)

这是 **【在 Android Studio 上构建社交媒体 App】**教程的 **第 11 部分** ，我们将在这篇文章中涵盖以下功能:

*   We will make comments on the blog.
*   We will write a comment here, and then we will display the comment and update the number of comments.
*   Comment is the best function of all blog applications. It helps to interact with bloggers, and so on.

### **分步实施**

**第一步:新建布局资源文件**

转到 **app > res >布局>右键>新建>布局资源文件**并将文件命名为 row_comments。下面是 **row_comments.xml** 文件的代码。

## XML

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.cardview.widget.CardView 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="1dp"
    android:orientation="vertical"
    app:cardBackgroundColor="@color/colorWhite"
    app:contentPadding="2dp">

    <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

        <de.hdodenhof.circleimageview.CircleImageView
            android:id="@+id/loadcomment"
            android:layout_width="40dp"
            android:layout_height="40dp"
            android:layout_marginEnd="5dp"
            android:layout_marginRight="5dp"
            android:src="@drawable/profile_image" />

        <TextView
            android:id="@+id/commentname"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_toRightOf="@id/loadcomment"
            android:text="Anni"
            android:textColor="@color/colorBlack"
            android:textSize="16sp"
            android:textStyle="bold" />

        <TextView
            android:id="@+id/commenttext"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_below="@id/commentname"
            android:layout_toEndOf="@id/loadcomment"
            android:layout_toRightOf="@id/loadcomment"
            android:text="Actual Comment"
            android:textColor="@color/colorBlack" />

        <TextView
            android:id="@+id/commenttime"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_below="@id/commenttext"
            android:layout_toEndOf="@id/loadcomment"
            android:layout_toRightOf="@id/loadcomment"
            android:text="12/06/19" />
    </RelativeLayout>

</androidx.cardview.widget.CardView>
```