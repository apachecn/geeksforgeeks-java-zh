# 如何在安卓中使用 Alerter 库创建弹出消息

> 原文:[https://www . geesforgeks . org/如何创建-弹出消息-使用-alerter-library-in-Android/](https://www.geeksforgeeks.org/how-to-create-popup-message-using-alerter-library-in-android/)

在本文中，我们将学习如何借助**警报库**创建弹出消息。如果要向用户显示一些提醒信息，最好使用**提醒器**而不是使用或 **[提醒条](https://www.geeksforgeeks.org/how-to-add-a-snackbar-in-android/)** 。我们可以添加各种**onclicklisters**到我们的提醒器消息中，这使得它更好，也有很好的吸引人的用户界面。

[![](img/44da2fc23c0c76a5472c2775918a2c06.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200519184403/Screenshot-975.png) 
**进场:**

1.  在 **[build.gradle](https://www.geeksforgeeks.org/android-build-gradle/)** 文件中添加支持库，并在依赖项部分添加依赖项。该库便于在应用程序中轻松集成警报视图。警报视图是可定制的，它显示在应用程序中正在进行的活动上。该库还兼容 **AndroidX** 。

    ```java
    dependencies {
        implementation 'com.tapadoo.android:alerter:2.0.4'
    }
    ```

2.  现在在 **activity_main.xml** 文件中添加以下代码。该代码在主活动中添加一个按钮，如果点击该按钮，则调用**显示警报**功能。

    ## activity _ main . XML

    ```java
    <?xml version="1.0" encoding="utf-8"?>
    <androidx.constraintlayout.widget.ConstraintLayout

        xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:app="http://schemas.android.com/apk/res-auto"
        xmlns:tools="http://schemas.android.com/tools"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        tools:context=".MainActivity">

        <Button
            android:id="@+id/button"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:onClick="showAlerter"
            android:text="Show Alerter"
            app:layout_constraintBottom_toBottomOf="parent"
            app:layout_constraintLeft_toLeftOf="parent"
            app:layout_constraintRight_toRightOf="parent"
            app:layout_constraintTop_toTopOf="parent" />
    </androidx.constraintlayout.widget.ConstraintLayout>
    ```

3.  现在在**MainActivity.java**文件中添加以下代码。它定义了**显示警告器**功能。该功能创建**警报器**。调用各种方法来初始化警报器的不同属性。**设置**设置标题，**设置文字**设置标题下方显示的文字，**设置图标**设置图标等。还附加了各种 onClickListeners，以便您可以响应用户的操作。

    ## MainActivity.java

    ```java
    package org.geeksforgeeks.gfgAlerter;

    import androidx.appcompat.app.AppCompatActivity;
    import android.os.Bundle;
    import android.view.View;
    import android.widget.Button;
    import com.tapadoo.alerter.Alerter;
    import com.tapadoo.alerter.OnHideAlertListener;
    import com.tapadoo.alerter.OnShowAlertListener;

    public class MainActivity extends AppCompatActivity {

        Button button;
        @Override
        protected void onCreate(Bundle savedInstanceState)
        {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_main);

            button = findViewById(R.id.button);
        }

        public void showAlerter(View v)
        {
            Alerter.create(this)
                .setTitle("Alert Title")
                .setText("Alert Text")
                .setIcon(
                    R.drawable.ic_android_black_24dp)
                .setBackgroundColorRes(
                    R.color.colorAccent)
                .setDuration(3000)
                .setOnClickListener(
                    new View.OnClickListener() {

                        @Override
                        public void onClick(View v)
                        {
                            // do something when
                            // Alerter message was clicked
                        }
                    })

                .setOnShowListener(
                    new OnShowAlertListener() {

                        @Override
                        public void onShow()
                        {
                            // do something when
                            // Alerter message shows
                        }
                    })

                .setOnHideListener(
                    new OnHideAlertListener() {

                        @Override
                        public void onHide()
                        {
                            // do something when
                            // Alerter message hides
                        }
                    })
                .show();
        }
    }
    ```

    T21】

**输出:**

<video class="wp-video-shortcode" id="video-414832-1" width="320" height="540" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200515020622/Record_2020-05-15-01-40-59_6b74ffc4bac337f4991463b14cbc486a.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200515020622/Record_2020-05-15-01-40-59_6b74ffc4bac337f4991463b14cbc486a.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200515020622/Record_2020-05-15-01-40-59_6b74ffc4bac337f4991463b14cbc486a.mp4)</video>