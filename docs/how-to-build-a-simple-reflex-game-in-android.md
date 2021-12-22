# 如何在安卓中构建一款简单的反射游戏？

> 原文:[https://www . geeksforgeeks . org/如何在安卓中构建简单反射游戏/](https://www.geeksforgeeks.org/how-to-build-a-simple-reflex-game-in-android/)

反射游戏是一个简单有趣的游戏，可以测量你的反应速度。制作和理解都很简单。我们将设计一个反射游戏来计算你的反应速度。规则很简单，当你看到背景颜色的变化时，只需按下停止按钮，你这样做的时间就是你的速度。一个更快的回应会比一个更慢的回应显示更好的赞美。

### 逐步实施

**第一步:创建新项目**

在安卓工作室创建新项目请参考 [**如何在安卓工作室创建/启动新项目。**](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/) 注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

XML 代码用于构建活动的结构及其样式部分。它包含一个 [**TextView**](https://www.geeksforgeeks.org/textview-widget-in-android-using-java-with-examples/) 在活动中心展示游戏指令。然后它包含两个**按钮**，开始和停止。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/rlVar1"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--TextView to display game instruction-->
    <TextView
        android:id="@+id/tvVar1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:padding="20dp"
        android:text="Click on Start first, and wait
                      until the background color changes.
                      As soon as it changes hit Stop"
        android:textSize="25dp" />

    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/tvVar1"
        android:layout_centerHorizontal="true"
        android:orientation="horizontal"
        android:padding="20dp">

        <!--start button-->
        <Button
            android:id="@+id/btVar1"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_margin="10dp"
            android:text="Start" />

        <!--stop button-->
        <Button
            android:id="@+id/btVar2"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_margin="10dp"
            android:text="Stop" />

    </LinearLayout>

</RelativeLayout>
```

**步骤 3:使用 MainActivity.java 文件**

当玩家点击开始按钮时，该按钮的 **onClickListener()** 功能被调用。在这个函数中，我们将生成一个 1-10 的随机整数。这个数字是显示背景改变的秒数。为了生成数字，我们将使用**随机**功能。得到整数后，我们将创建一个**处理程序**类，并在一个后置延迟后调用一个**可运行**函数。处理程序的主要功能是调度消息和可运行。在可运行界面内部，我们将使用 **setBackgroundResource()** 功能设置屏幕的背景。我们将使用**system . CurrentMemillis()**函数获取当前时间，单位为毫秒。首先我们会得到屏幕背景变化时系统的时间，然后我们会得到点击停止按钮时系统的时间。这两个时间的差异会给出玩家的反应时间。下面是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.os.Bundle;
import android.os.Handler;
import android.view.View;
import android.widget.Button;
import android.widget.RelativeLayout;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

import java.util.Random;

public class MainActivity extends AppCompatActivity {

    public Button button1, button2;
    public RelativeLayout relativeLayout;

    // runnable function
    Runnable runnable = new Runnable() {
        @Override
        public void run() {

            // set the background on the screen
            relativeLayout.setBackgroundResource(R.color.green);

            // get the system time in milli second
            // when the screen background is set
            final long time = System.currentTimeMillis();

            // function when stop button is clicked
            button2.setOnClickListener(new View.OnClickListener() {
                @Override
                public void onClick(View view) {
                    // get the system time in milli second
                    // when the stop button is clicked
                    long time1 = System.currentTimeMillis();

                    // display reflex time in toast message
                    Toast.makeText(getApplicationContext(), "Your reflexes takes " + (time1 - time) + " time to work", Toast.LENGTH_LONG).show();

                    // remove the background again
                    relativeLayout.setBackgroundResource(0);
                }
            });
        }
    };

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        relativeLayout = findViewById(R.id.rlVar1);
        button1 = findViewById(R.id.btVar1);
        button2 = findViewById(R.id.btVar2);

        // function when the start button is clicked
        button1.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

                // generate a random number from 1-10
                Random random = new Random();
                int num = random.nextInt(10);

                // call the runnable function after
                // a post delay of num seconds
                Handler handler = new Handler();
                handler.postDelayed(runnable, num * 1000);
            }
        });
    }
}
```

### 输出:

<video class="wp-video-shortcode" id="video-539291-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210108235641/Simple-Reflex-Game-in-Android.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210108235641/Simple-Reflex-Game-in-Android.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210108235641/Simple-Reflex-Game-in-Android.mp4)</video>