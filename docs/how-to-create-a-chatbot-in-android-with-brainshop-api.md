# 如何用 BrainShop API 在安卓系统中创建聊天机器人？

> 原文:[https://www . geesforgeks . org/how-to-create-a-chatbot-in-Android-with-brain shop-API/](https://www.geeksforgeeks.org/how-to-create-a-chatbot-in-android-with-brainshop-api/)

我们已经看到了许多应用程序和网站，在这些应用程序和网站中，我们将看到一个聊天机器人，在这里我们可以与聊天机器人一起聊天，并且可以轻松地从聊天机器人那里获得我们的问题的解决方案。在本文中，我们将看一下**在安卓**中构建聊天机器人。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将构建一个简单的聊天机器人，我们可以向我们的机器人提问，机器人将回答我们的问题。下面是视频，我们将在其中看到我们将在本文中构建的内容。下面给出一个视频样本，了解一下在本文中我们要做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-560931-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210213154250/Screenrecorder-2021-02-13-15-39-22-202.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210213154250/Screenrecorder-2021-02-13-15-39-22-202.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210213154250/Screenrecorder-2021-02-13-15-39-22-202.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在你的 build.gradle 文件**中添加下面的依赖项

导航到**应用程序>渐变脚本> build.gradle** 文件，并在依赖项部分向其添加下面的依赖项。

> 实现‘com . Android .凌空:凌空:1 . 1 . 1’

添加这个依赖项后，同步你的项目，现在进入 **AndroidManifest.xml** 部分。

**第三步:在 AndroidManifest.xml 文件**中添加互联网权限

导航到**应用程序> AndroidManifest.xml** ，并添加以下代码。

## 可扩展标记语言

```
<!--permissions for internet-->
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

**第 4 步:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--recycler view to display our chats-->
    <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/idRVChats"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:layout_above="@id/idLLMessage" />

    <LinearLayout
        android:id="@+id/idLLMessage"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_alignParentBottom="true"
        android:orientation="horizontal"
        android:weightSum="5">

        <!--edit text to enter message-->
        <EditText
            android:id="@+id/idEdtMessage"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="4"
            android:hint="Enter Message" />

        <!--button to send message-->
        <ImageButton
            android:id="@+id/idIBSend"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_gravity="center_vertical"
            android:layout_weight="1"
            android:background="@color/purple_200"
            android:src="@android:drawable/ic_menu_send"
            android:tint="@color/white" />

    </LinearLayout>

</RelativeLayout>
```

**第 5 步:创建一个模态类来存储我们的消息**

导航到**应用程序> java >你的应用程序的包名>右键点击它>新建> Java 类**并将其命名为 **MessageModal** 并添加下面的代码。在代码中添加注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class MessageModal {

    // string to store our message and sender
    private String message;
    private String sender;

    // constructor.
    public MessageModal(String message, String sender) {
        this.message = message;
        this.sender = sender;
    }

    // getter and setter methods.
    public String getMessage() {
        return message;
    }

    public void setMessage(String message) {
        this.message = message;
    }

    public String getSender() {
        return sender;
    }

    public void setSender(String sender) {
        this.sender = sender;
    }
}
```

**第六步:为用户消息创建布局文件**

该文件中使用的图标出现在可绘制文件夹中。导航至 **app > res >布局>右键点击>新建>布局资源文件**并将文件命名为 **user_msg** 并添加以下代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.cardview.widget.CardView 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_gravity="end"
    android:layout_margin="5dp"
    android:elevation="8dp"
    app:cardCornerRadius="8dp">

    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="horizontal">

        <!--text view for displaying user message-->
        <TextView
            android:id="@+id/idTVUser"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_gravity="center_vertical"
            android:layout_margin="5dp"
            android:padding="3dp"
            android:text="User message"
            android:textColor="@color/black" />

        <!--we are displaying user icon-->
        <ImageView
            android:layout_width="50dp"
            android:layout_height="50dp"
            android:layout_margin="10dp"
            android:src="@drawable/ic_user" />

    </LinearLayout>

</androidx.cardview.widget.CardView>
```