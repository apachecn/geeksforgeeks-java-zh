# 如何在安卓中使用 IconSwitch 库添加自定义 Switch？

> 原文:[https://www . geesforgeks . org/how-add-custom-switch-using-icon switch-library-in-Android/](https://www.geeksforgeeks.org/how-to-add-custom-switch-using-iconswitch-library-in-android/)

在本文中，我们将学习如何在我们的项目中添加**自定义开关**。我们知道 [**开关**](https://www.geeksforgeeks.org/switch-in-kotlin/) 只有开和关两种状态。在自定义开关中，我们根据我们的要求添加了可用于不同目的的图标。借助这个库 **IconSwitch** ，我们可以轻松添加一个自定义开关，当用户改变状态时，它会自动动画化。

**进场:**

1.  在 **[build.gradle](https://www.geeksforgeeks.org/android-build-gradle/)** 文件中添加支持库，并在依赖项部分添加依赖项。借助于此，我们可以直接在布局中使用小部件。

    ```java
    dependencies {         
          implementation 'com.polyak:icon-switch:1.0.0'      
    }         
    ```

2.  在 activity_main.xml 文件中添加以下代码。这里我们在布局中添加了自定义开关。在 **app:isw_icon_left** 和 **app:isw_icon_right** 中，我们分别为左右切换添加了可绘制的图标。

    ## activity _ main . XML

    ```java
    <?xml version="1.0" encoding="utf-8"?>
    <RelativeLayout 
        xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:app="http://schemas.android.com/apk/res-auto"
        xmlns:tools="http://schemas.android.com/tools"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        tools:context=".MainActivity">

        <com.polyak.iconswitch.IconSwitch
            android:id="@+id/icon_switch"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_centerHorizontal="true"
            android:layout_centerVertical="true"
            app:isw_default_selection="right"
            app:isw_icon_left="@drawable/ic_algorithm"
            app:isw_icon_right="@drawable/ic_online_course"
            app:isw_icon_size="25dp" />

    </RelativeLayout>
    ```

3.  现在在**MainActivity.java**文件中添加以下代码。这里我们在我们的开关上添加 **setCheckChangedListener** ，如果开关改变，它将被调用。如果左开关打开，则执行情况**左**，如果右开关打开，则执行情况**右**。

    ## MainActivity.java

    ```java
    package org.geeksforgeeks.gfgCustomSwitch;

    import android.os.Bundle;
    import android.widget.Toast;
    import androidx.appcompat.app.AppCompatActivity;
    import com.polyak.iconswitch.IconSwitch;

    public class MainActivity extends AppCompatActivity {

        @Override
        protected void onCreate(Bundle savedInstanceState)
        {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity);

            IconSwitch iconSwitch = findViewById(R.id.icon_switch);
            iconSwitch.setCheckedChangeListener(
                new IconSwitch.CheckedChangeListener() {
                    @Override
                    public void onCheckChanged(IconSwitch.Checked current)
                    {
                        switch (current) {

                        case LEFT:
                            Toast.makeText(MainActivity.this,
                                           "Algorithms", Toast.LENGTH_SHORT)
                                .show();
                            break;

                        case RIGHT:
                            Toast.makeText(MainActivity.this,
                                           "Courses", Toast.LENGTH_SHORT)
                                .show();
                            break;
                        }
                    }
                });
        }
    }
    ```

**输出:**

<video class="wp-video-shortcode" id="video-429647-1" width="320" height="540" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200607193336/Record_2020-06-07-19-19-59_13aadd56c6b43953177d9efb56a138ce.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200607193336/Record_2020-06-07-19-19-59_13aadd56c6b43953177d9efb56a138ce.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200607193336/Record_2020-06-07-19-19-59_13aadd56c6b43953177d9efb56a138ce.mp4)</video>