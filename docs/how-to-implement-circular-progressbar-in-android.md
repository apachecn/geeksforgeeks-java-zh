# 如何在安卓系统中实现循环进度条？

> 原文:[https://www . geesforgeks . org/how-implement-circular-progress bar-in-Android/](https://www.geeksforgeeks.org/how-to-implement-circular-progressbar-in-android/)

[ProgressBar](https://www.geeksforgeeks.org/progressbar-in-kotlin/) 是当我们从另一个来源获取一些数据时使用的，需要时间，所以为了用户的满意，我们一般会向他们显示任务的进度。在本文中，我们将学习如何使用 **Java** 在 android 应用程序中实现循环进度条。因此，本文将为您提供一个在**安卓工作室**中构建的应用程序中实现循环进度条的完整想法。因此，在不浪费更多时间的情况下，让我们转到文章中，阅读如何实现这一任务。

### 我们将在这篇文章中开发什么？

我们将构建一个简单的应用程序，其中我们将实现一个带有文本显示的圆形进度条。下面给出了一个示例视频，以了解我们将在本文中做什么。注意，我们将使用 **Java** 语言来实现这个项目。

![ Implement Circular ProgressBar in Android Sample GIF](img/e9562556e0c67229c1339d7e8e79fcca.png)

### 逐步实施

**第一步:创建新项目**

在安卓工作室创建新项目请参考 [<u>【如何在安卓工作室创建/启动新项目】</u>](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/) 。注意选择 **Java** 作为编程语言。

**第二步:创建循环进度条 xml**

导航到**应用程序> res >可绘制** **>右键单击**并选择**新建>可绘制资源文件**，并将新的 XML 文件命名为**圆形进度条**。 **xml** 并参考以下代码。代码中添加了注释，以更详细地理解代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<rotate 
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromDegrees="270"
    android:toDegrees="270">

    <!--styling the progress bar-->
    <shape
        android:innerRadiusRatio="2.5"
        android:shape="ring"
        android:thickness="8dp"
        android:useLevel="true">
        <gradient
            android:angle="0"
            android:endColor="@color/colorPrimary"
            android:startColor="#000000"
            android:type="sweep"
            android:useLevel="false" />
    </shape>

</rotate>
```

**第三步:创建圆形**

同样，创建一个新的**可绘制资源文件**，并将该文件命名为 **circular_shape.xml** ，并参考以下代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<shape 
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:innerRadiusRatio="2.5"
    android:shape="ring"
    android:thickness="3dp"
    android:useLevel="false">
    <solid android:color="@color/colorPrimary" />
</shape>
```

**第 4 步:使用 activity_main.xml 文件**

现在是时候设计应用程序的布局了。为此，导航到**应用程序> res >布局> activity_main.xml** 并参考下面编写的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center_horizontal"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <RelativeLayout
        android:id="@+id/progress_layout"
        android:layout_width="200dp"
        android:layout_height="200dp"
        android:layout_margin="100dp">

        <!--progress bar implementation-->
        <ProgressBar
            android:id="@+id/progress_bar"
            style="?android:attr/progressBarStyleHorizontal"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:background="@drawable/circular_shape"
            android:indeterminate="false"
            android:progressDrawable="@drawable/circular_progress_bar"
            android:textAlignment="center" />

        <!--Text implementation in center of the progress bar-->
        <TextView
            android:id="@+id/progress_text"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_alignParentLeft="true"
            android:layout_alignParentRight="true"
            android:layout_centerVertical="true"
            android:gravity="center"
            android:text="---"
            android:textColor="@color/colorPrimary"
            android:textSize="28sp"
            android:textStyle="bold" />
    </RelativeLayout>

</LinearLayout>
```

**步骤 5:使用 MainActivity.java 文件**

转到 **app > java >包名>MainActivity.java**文件，参考以下代码。下面是 MainActivity.java 文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.os.Bundle;
import android.os.Handler;
import android.widget.ProgressBar;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    private ProgressBar progressBar;
    private TextView progressText;
    int i = 0;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // set the id for the progressbar and progress text
        progressBar = findViewById(R.id.progress_bar);
        progressText = findViewById(R.id.progress_text);

        final Handler handler = new Handler();
        handler.postDelayed(new Runnable() {
            @Override
            public void run() {
                // set the limitations for the numeric
                // text under the progress bar
                if (i <= 100) {
                    progressText.setText("" + i);
                    progressBar.setProgress(i);
                    i++;
                    handler.postDelayed(this, 200);
                } else {
                    handler.removeCallbacks(this);
                }
            }
        }, 200);
    }
}
```

仅此而已，现在应用程序已准备好安装在设备上。下面是应用程序的输出。

**输出:**

<video class="wp-video-shortcode" id="video-582797-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210325193420/WhatsApp-Video-2021-03-25-at-7.33.38-PM.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210325193420/WhatsApp-Video-2021-03-25-at-7.33.38-PM.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210325193420/WhatsApp-Video-2021-03-25-at-7.33.38-PM.mp4)</video>

**GitHub Link:**

该项目在 GitHub 上提供，您可以通过以下链接访问: [<u>安卓应用中的圆形进度条</u>](https://github.com/Nehaadnekar/progress_bar_android)