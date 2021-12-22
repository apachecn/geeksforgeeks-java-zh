# 如何在安卓中添加 Snackbar

> 原文:[https://www . geesforgeks . org/如何在安卓中添加 snackbar/](https://www.geeksforgeeks.org/how-to-add-a-snackbar-in-android/)

**Snackbar** 提供关于操作的轻量级反馈。该消息出现在手机屏幕的底部和较大设备的左下方。Snackbar 显示在屏幕所有元素的上方。但是没有任何组件受其影响。在你的视图层次结构中有一个**坐标布局**允许 Snackbar 启用某些功能，比如轻扫关闭和自动移动小部件。Snackbar 类似于 Toast，但唯一的主要区别是可以用 Snackbar 添加一个动作。

**进场:**

1.  在 **[build.gradle](https://www.geeksforgeeks.org/android-build-gradle/)** 文件中添加支持库，并在依赖项部分添加材料设计依赖项。它是**材料设计**的一部分，这就是为什么我们要增加一个依赖。

    ```java
    dependencies {
        implementation 'com.google.android.material:material:1.1.0'
    }
    ```

2.  现在在 **activity_main.xml** 文件中添加以下代码。它将创建一个名为**的按钮来打开“T4”。

    ## activity _ main . XML

    ```java
    <?xml version="1.0" encoding="utf-8"?>
    <androidx.coordinatorlayout.widget.CoordinatorLayout
        xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:tools="http://schemas.android.com/tools"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id/layout"
        tools:context=".MainActivity">

        <Button
            android:layout_gravity="center"
            android:id="@+id/button"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:textSize="18sp"
            android:textAllCaps="false"
            android:text="Open Snackbar"
             />

    </androidx.coordinatorlayout.widget.CoordinatorLayout>
    ```** 
3.  现在在**MainActivity.java**文件中添加以下代码。这将定义按钮，并向按钮添加 onClickListener。在 onClickListener 中，创建并调用一个 Snackbar。因此，每当单击按钮时，onClickListener 都会创建一个 snackbar 并调用它，用户就会看到该消息。此 snackbar 包含一个操作，如果单击，将显示一个祝酒词。

    ## MainActivity.java

    ```java
    package org.geeksforgeeks.gfgsnackbar;

    import androidx.appcompat.app.AppCompatActivity;
    import androidx.coordinatorlayout
        .widget.CoordinatorLayout;
    import android.os.Bundle;
    import android.view.View;
    import android.widget.Button;
    import android.widget.Toast;

    import com.google.android.material
        .snackbar
        .Snackbar;

    public class MainActivity
        extends AppCompatActivity {

        Button button;
        CoordinatorLayout layout;

        @Override
        protected void onCreate(
            Bundle savedInstanceState)
        {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_main);

            button = findViewById(R.id.button);
            layout = findViewById(R.id.layout);

            button.setOnClickListener(
                new View.OnClickListener() {
                    @Override
                    public void onClick(View v)
                    {

                        // Create a snackbar
                        Snackbar snackbar
                            = Snackbar
                                  .make(
                                      layout,
                                      "Message is deleted",
                                      Snackbar.LENGTH_LONG)
                                  .setAction(
                                      "UNDO",

                                      // If the Undo button
                                      // is pressed, show
                                      // the message using Toast
                                      new View.OnClickListener() {
                                          @Override
                                          public void onClick(View view)
                                          {
                                              Toast
                                                  .makeText(
                                                      MainActivity.this,
                                                      "Undo Clicked",
                                                      Toast.LENGTH_SHORT)
                                                  .show();
                                          }
                                      });

                        snackbar.show();
                    }
                });
        }
    }
    ```

**输出:**

<video class="wp-video-shortcode" id="video-408891-1" width="665" height="1330" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200505003945/Record_2020-05-05-00-35-43_6f6ad7a6a32d4495fc2b19b76a14ac9e1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200505003945/Record_2020-05-05-00-35-43_6f6ad7a6a32d4495fc2b19b76a14ac9e1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200505003945/Record_2020-05-05-00-35-43_6f6ad7a6a32d4495fc2b19b76a14ac9e1.mp4)</video>