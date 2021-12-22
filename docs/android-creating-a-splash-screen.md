# 安卓|创建闪屏

> 原文:[https://www . geesforgeks . org/Android-creating-a-splash-screen/](https://www.geeksforgeeks.org/android-creating-a-splash-screen/)

闪屏大多是应用程序打开时的第一个屏幕。它是一个持续出现特定时间的屏幕，通常在应用程序启动时首次显示。闪屏用于在应用程序完全加载之前显示一些基本的介绍性信息，如公司徽标、内容等。

**在安卓中使用处理程序创建闪屏**

这里我们创建了两个活动 MainActivity，显示闪屏和 SecondActivity，以便从 MainActivity 切换到 SecondActivity。主程序是用 MainActivity 编写的，你可以根据需要改变活动。

*   要删除 ActionBar，您需要在 styles.xml 文件中进行以下更改。

    ```
    style name="AppTheme" parent="Theme.AppCompat.Light.NoActionBar"
    ...

    ```

*   使用适合您应用的颜色。
*   No need to make any changes in your manifest file.

    **使用“后置延迟()”功能:**

    ```
    public final boolean postDelayed(Runnable Object token, long delayMillisec)
    ```

    该函数将进程延迟指定的时间。这与允许您发送和处理与线程的消息队列相关联的消息和可运行对象的处理程序一起使用。每个处理程序实例都是一个线程。

    下面是创建闪屏的代码:

    *MainActivity.java*

    ```
    package com.example.hp.splashscreen;

    import android.content.Intent;
    import android.os.Handler;
    import android.support.v7.app.AppCompatActivity;
    import android.os.Bundle;
    import android.view.WindowManager;

    public class MainActivity extends AppCompatActivity {

        private static int SPLASH_SCREEN_TIME_OUT=2000;
        #After completion of 2000 ms, the next activity will get started.
        @Override
        protected void onCreate(Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);

            getWindow().setFlags(WindowManager.LayoutParams.FLAG_FULLSCREEN, 
                         WindowManager.LayoutParams.FLAG_FULLSCREEN);
            //This method is used so that your splash activity
            //can cover the entire screen.

            setContentView(R.layout.activity_main);
            //this will bind your MainActivity.class file with activity_main.

            new Handler().postDelayed(new Runnable() {
                @Override
                public void run() {
                    Intent i=new Intent(MainActivity.this,
                                             SecondActivity.class);
                    //Intent is used to switch from one activity to another.

                    startActivity(i);
                    //invoke the SecondActivity.

                    finish();
                    //the current activity will get finished.
                }
            }, SPLASH_SCREEN_TIME_OUT);
        }
    }
    ```

    *activity_main.xml* :你可以使用任何一张图片作为闪屏，先粘贴到可绘制的文件夹中。XML 文件很容易通过拖放的方式生成，只需使用 imageview 并选择合适的图像。

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <android.support.constraint.ConstraintLayout
        xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:tools="http://schemas.android.com/tools"
        xmlns:app="http://schemas.android.com/apk/res-auto"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        tools:context="com.example.hp.splashscreen.MainActivity">

        <ImageView
            android:id="@+id/imageView"
            android:layout_width="250dp"
            android:layout_height="200dp"
            app:srcCompat="@drawable/geeks"
            app:layout_constraintTop_toTopOf="parent"
            android:layout_marginTop="8dp"
            android:layout_marginRight="8dp"
            app:layout_constraintRight_toRightOf="parent"
            android:layout_marginLeft="8dp"
            app:layout_constraintLeft_toLeftOf="parent"
            app:layout_constraintBottom_toBottomOf="parent"
            android:layout_marginBottom="8dp"
            app:layout_constraintVertical_bias="0.447" />
    </android.support.constraint.ConstraintLayout>
    ```

    **输出:**

    <video class="wp-video-shortcode" id="video-213185-1" width="380" height="552" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/splashscreen.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/splashscreen.mp4](https://media.geeksforgeeks.org/wp-content/uploads/splashscreen.mp4)</video>