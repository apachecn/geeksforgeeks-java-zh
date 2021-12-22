# 如何在社交媒体安卓 App 中实现聊天功能？

> 原文:[https://www . geeksforgeeks . org/如何实现-聊天-功能-社交媒体-安卓-app/](https://www.geeksforgeeks.org/how-to-implement-chat-functionality-in-social-media-android-app/)

这是 **【在 Android Studio 上构建社交媒体 App】**教程的 **第 14 部分** ，我们将在本文中介绍以下功能:

*   We will create a layout for the chat & send messages in the chat.
*   Users can send messages or images.
*   Users can send images using a camera or gallery.
*   First, asking for permission will require you to use the gallery or send the image after clicking the image with the camera.
*   If permission is obtained, the user can send the image or ask for permission again.

### **分步实施**

**第一步:新建两个布局资源文件，命名为 row_chat_left 和 row_chat_right**

使用 **row_chat_left.xml** 文件。收到的信息将在左侧。类似地，使用 **row_chat_right** 。 **xml** 文件。发送给用户的消息将在右侧。下面是**row _ chat _ left . XML**文件和 **row_chat_right** 的代码。 **xml** 文件。

## XML

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/msglayout"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:orientation="vertical"
    android:padding="10dp">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal">

        <de.hdodenhof.circleimageview.CircleImageView
            android:id="@+id/profilec"
            android:layout_width="50dp"
            android:layout_height="50dp"
            android:src="@drawable/profile_image"
            app:civ_border_color="@null" />

        <TextView
            android:id="@+id/msgc"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:background="@drawable/bg_receiver"
            android:padding="15dp"
            android:text="His Message"
            android:textColor="@color/colorBlack"
            android:textSize="16sp"
            android:visibility="gone" />

        <ImageView
            android:id="@+id/images"
            android:layout_width="200dp"
            android:layout_height="200dp"
            android:adjustViewBounds="true"
            android:background="@drawable/bg_receiver"
            android:padding="15dp"
            android:scaleType="fitCenter"
            android:src="@drawable/ic_images" />

        <TextView
            android:id="@+id/timetv"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="02/01/1990 06:19PM"
            android:textColor="@color/colorBlack"
            android:textSize="12sp" />
    </LinearLayout>

    <TextView
        android:id="@+id/isSeen"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:gravity="end"
        android:text="Delivered"
        android:textAlignment="textEnd"
        android:visibility="gone" />

</LinearLayout>
```