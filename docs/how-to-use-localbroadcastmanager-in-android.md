# 如何在安卓系统中使用 LocalBroadcastManager？

> 原文:[https://www . geesforgeks . org/how-localboardcastmanager-in-Android/](https://www.geeksforgeeks.org/how-to-use-localbroadcastmanager-in-android/)

本地广播管理器是我们使用的大多数应用程序中最重要的功能之一。这个功能通常在后台工作，我们看不到。当特定事件发生时，广播管理器会通知我们。例如，当我们订阅了极客网站上的任何课程时，如果该课程正在进行更新或竞赛，我们会收到关于该活动的电子邮件通知。在那里，使用了广播管理器，它用消息、邮件或任何其他关于特定事件的格式通知用户。在本文中，我们将看看如何在我们的安卓应用程序中使用这个广播管理器。

### **如何在安卓系统中使用 Broad Cast Manager？**

为了在我们的安卓应用程序中使用 Broad Cast Manager，使用它的过程分为两种类型，首先我们必须注册我们的广播，然后从同一个广播接收更新。

**步骤 1:注册广播**

为了使用广播管理器执行特定的操作，我们必须首先注册我们的广播，然后只有我们可以使用这个广播来接收更新。有两种方法来注册我们的广播，我们可以在我们的安卓清单文件或我们想要接收其更新的活动中注册它。

**步骤 2:接收来自广播的更新**

这一步用于接收更新，我们将在应用程序中执行某个操作后通过广播管理器发送更新。为了接收更新，我们将使用 onRecieve()方法来接收更新。

### **我们要建什么？**

我们将建立一个简单的应用程序，我们将使用广播管理器点击按钮发送我们的数据。下面是视频，我们将在其中看到我们将在本文中构建的内容。

<video class="wp-video-shortcode" id="video-593666-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210418161850/Screenrecorder-2021-04-18-16-16-59-400.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210418161850/Screenrecorder-2021-04-18-16-16-59-400.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210418161850/Screenrecorder-2021-04-18-16-16-59-400.mp4)</video>

### **广播管理器的分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/idRLView"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--text view for receiving our data updates
        using broad cast manager-->
    <TextView
        android:id="@+id/idTVHeading"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:padding="10dp"
        android:text="Welcome"
        android:textAlignment="center"
        android:textAllCaps="false"
        android:textColor="@color/black"
        android:textSize="30sp" />

    <!--button for sending the updated data with 
        the help of broad cast manager-->
    <Button
        android:id="@+id/idBtnStartBroadCast"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/idTVHeading"
        android:layout_centerInParent="true"
        android:layout_marginTop="30dp"
        android:text="Send BroadCast"
        android:textAllCaps="false" />

</RelativeLayout>
```

**第三步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.BroadcastReceiver;
import android.content.Context;
import android.content.Intent;
import android.content.IntentFilter;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;
import androidx.localbroadcastmanager.content.LocalBroadcastManager;

public class MainActivity extends AppCompatActivity {

    // creating a variable for 
    // our text view and button
    private TextView headingTV;
    private Button sendBroadCastBtn;

    // on below line we are creating a new broad cast manager.
    private BroadcastReceiver broadcastReceiver = new BroadcastReceiver() {
        // we will receive data updates in onRecieve method.
        @Override
        public void onReceive(Context context, Intent intent) {
            // Get extra data included in the Intent
            String message = intent.getStringExtra("message");
            // on below line we are updating the data in our text view.
            headingTV.setText(message);
        }
    };

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initializing our variables.
        headingTV = findViewById(R.id.idTVHeading);
        sendBroadCastBtn = findViewById(R.id.idBtnStartBroadCast);

        // on below line we are registering our local broadcast manager.
        LocalBroadcastManager.getInstance(this).registerReceiver(broadcastReceiver, new IntentFilter("custom-action-local-broadcast"));

        // on below line we are adding click listener to our button
        sendBroadCastBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // inside on click we are calling the intent with the action.
                Intent intent = new Intent("custom-action-local-broadcast");
                // on below line we are passing data to our broad cast receiver with key and value pair.
                intent.putExtra("message", "Welcome \n to \n Geeks For Geeks");
                // on below line we are sending our broad cast with intent using broad cast manager.
                LocalBroadcastManager.getInstance(MainActivity.this).sendBroadcast(intent);
            }
        });
    }
}
```

现在运行您的应用程序，并查看应用程序的输出。

**输出:**

<video class="wp-video-shortcode" id="video-593666-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210418161850/Screenrecorder-2021-04-18-16-16-59-400.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210418161850/Screenrecorder-2021-04-18-16-16-59-400.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210418161850/Screenrecorder-2021-04-18-16-16-59-400.mp4)</video>