# 如何在安卓系统的谷歌地图上绘制轨迹？

> 原文:[https://www . geeksforgeeks . org/如何在安卓系统中绘制谷歌地图轨迹/](https://www.geeksforgeeks.org/how-to-draw-a-track-on-google-maps-in-android/)

在许多安卓应用程序中，我们已经看到从源位置到目的地位置有一个路线标记。在这篇文章中，我们将看看**我们如何在安卓系统中的谷歌地图上绘制轨迹。**

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将显示两个[编辑文本](https://www.geeksforgeeks.org/edittext-widget-in-android-using-java-with-examples/)字段，在这些字段中，我们必须输入源位置和目的地位置，我们将显示一个按钮来显示路线。点击该按钮后，我们将在谷歌地图上显示该位置的路线以及时间。下面给出了一个示例视频，让我们了解一下在本文中要做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-554394-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210127150850/1611740152955.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210127150850/1611740152955.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210127150850/1611740152955.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <!--edit text for our source location-->
    <EditText
        android:id="@+id/idEdtSource"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="20dp"
        android:hint="Source"
        android:padding="8dp" />

    <!--edit text for our destination location-->
    <EditText
        android:id="@+id/idEdtDestination"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="20dp"
        android:hint="Destination"
        android:padding="8dp" />

    <!--button to draw route on maps-->
    <Button
        android:id="@+id/idBtnTrack"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="20dp"
        android:background="@color/purple_500"
        android:padding="8dp"
        android:text="Show Track"
        android:textAllCaps="false"
        android:textColor="@color/white" />

</LinearLayout>
```

**第三步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.content.ActivityNotFoundException;
import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    // creating variables for 
    // edit texts and button.
    EditText sourceEdt, destinationEdt;
    Button trackBtn;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initializing our edit text and buttons
        sourceEdt = findViewById(R.id.idEdtSource);
        destinationEdt = findViewById(R.id.idEdtDestination);
        trackBtn = findViewById(R.id.idBtnTrack);

        // adding on click listener to our button.
        trackBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // calling a method to draw a track on google maps.
                drawTrack(sourceEdt.getText().toString(), destinationEdt.getText().toString());
            }
        });
    }

    private void drawTrack(String source, String destination) {
        try {
            // create a uri
            Uri uri = Uri.parse("https://www.google.co.in/maps/dir/" + source + "/" + destination);

            // initializing a intent with action view.
            Intent i = new Intent(Intent.ACTION_VIEW, uri);

            // below line is to set maps package name
            i.setPackage("com.google.android.apps.maps");

            // below line is to set flags
            i.setFlags(Intent.FLAG_ACTIVITY_NEW_TASK);

            // start activity
            startActivity(i);
        } catch (ActivityNotFoundException e) {
            // when the google maps is not installed on users device
            // we will redirect our user to google play to download google maps.
            Uri uri = Uri.parse("https://play.google.com/store/apps/details?id=com.google.android.apps.maps");

            // initializing intent with action view.
            Intent i = new Intent(Intent.ACTION_VIEW, uri);

            // set flags
            i.setFlags(Intent.FLAG_ACTIVITY_NEW_TASK);

            // to start activity
            startActivity(i);
        }
    }
}
```

运行您的应用程序并查看应用程序的输出。

### **输出:**

<video class="wp-video-shortcode" id="video-554394-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210127150850/1611740152955.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210127150850/1611740152955.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210127150850/1611740152955.mp4)</video>