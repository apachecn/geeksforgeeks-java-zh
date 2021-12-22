# 如何在安卓中实现 View Shaker

> 原文:[https://www . geeksforgeeks . org/如何实现查看安卓中的 shaker/](https://www.geeksforgeeks.org/how-to-implement-view-shaker-in-android/)

**查看 Shaker** 是一个动画，画面的 UI 在有限的时间内震动。这可以在整个布局或某个特定的小部件上实现。这是开发人员使用的一种非常常见的效果，尤其是显示不正确的凭据。

查看 Shaker 帮助我们**激活**小部件。可以添加各种效果。
T3【效果】T4

*   **Attension** *   ****Special**** *   ******Bounce****** *   ******Fade****** *   ******Flip****** *   ******Rotate****** *   ******Slide****** *   ******Zoom

    在本文中，我们将看到一个在应用程序中添加这种效果的例子。

    在本例中，用户想要登录[极客博客](https://www.geeksforgeeks.org/)门户。用户输入了错误的密码，然后点击登录按钮。然后，我们可以使用视图摇动器来动画化视图，使应用程序更具响应性。
    **进场**

    1.  在 **[build.gradle](https://www.geeksforgeeks.org/android-build-gradle/)** 文件中添加支持库，并在依赖项部分添加依赖项。该库具有上述各种动画效果。它有助于使我们的应用程序更加灵敏和动态。

        ```java
        dependencies {
            implementation 'com.daimajia.easing:library:2.0@aar'
            implementation 'com.daimajia.androidanimations:library:2.3@aar'
        }
        ```

    2.  现在在 **activity_main.xml** 文件中添加以下代码。此代码在 activity_main 上添加一个**文本视图**，两个**编辑文本**和一个**按钮**。

        ## activity _ main . XML

        ```java
        <?xml version="1.0" encoding="utf-8"?>
        <LinearLayout
            xmlns:android="http://schemas.android.com/apk/res/android"
            xmlns:tools="http://schemas.android.com/tools"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            tools:context=".MainActivity"
            android:orientation="vertical">

            <TextView
                android:textStyle="bold"
                android:textSize="24sp"
                android:textColor="#219806"
                android:layout_margin="15dp"
                android:layout_gravity="center"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="GeeksForGeeks"
                />
            <EditText
                android:id="@+id/editText1"
                android:layout_margin="15dp"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:hint="Enter ID"
                />
            <EditText
                android:id="@+id/editText2"
                android:layout_margin="15dp"
                android:inputType="textPassword"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:hint="Enter Password"
                />
            <Button
                android:id="@+id/button"
                android:layout_margin="25dp"
                android:layout_gravity="center"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="Log In"/>
        </LinearLayout>
        ```

    3.  现在在**MainActivity.java**文件中添加以下代码。onClickListener 被添加到登录按钮，该按钮在两个编辑文本上添加了**摇动**效果。不同的功能如**持续时间**设置持续时间，**重复**设置效果应该重复的次数，**播放**设置特定小部件的效果。

        ## MainActivity.java

        ```java
        package org.geeksforgeeks.gfgviewshaker;

        import androidx.appcompat.app.AppCompatActivity;
        import android.os.Bundle;
        import android.view.View;
        import android.widget.Button;
        import android.widget.EditText;
        import com.daimajia.androidanimations
            .library
            .Techniques;
        import com.daimajia.androidanimations
            .library
            .YoYo;

        public class MainActivity
            extends AppCompatActivity {

            Button login;
            EditText id, password;
            @Override
            protected void onCreate(
                Bundle savedInstanceState)
            {
                super.onCreate(savedInstanceState);
                setContentView(R.layout.activity_main);

                login = findViewById(R.id.button);
                id = findViewById(R.id.editText1);
                password = findViewById(R.id.editText2);

                login.setOnClickListener(
                    new View.OnClickListener() {

                        @Override
                        public void onClick(View v)
                        {
                            YoYo.with(Techniques.Shake)
                                .duration(500)
                                .repeat(2)
                                .playOn(id);

                            YoYo.with(Techniques.Shake)
                                .duration(500)
                                .repeat(2)
                                .playOn(password);
                        }
                    });
            }
        }
        ```

    **输出:**

    <video class="wp-video-shortcode" id="video-414965-1" width="320" height="540" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200515021807/Record_2020-05-15-02-16-31_8c8eb4b8b3a162c987ad6534919c52091.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200515021807/Record_2020-05-15-02-16-31_8c8eb4b8b3a162c987ad6534919c52091.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200515021807/Record_2020-05-15-02-16-31_8c8eb4b8b3a162c987ad6534919c52091.mp4)</video>******