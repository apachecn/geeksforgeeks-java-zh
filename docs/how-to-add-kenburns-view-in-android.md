# 如何在安卓中添加 KenBurns 视图？

> 原文:[https://www . geesforgeks . org/how-add-kenburns-view-in-Android/](https://www.geeksforgeeks.org/how-to-add-kenburns-view-in-android/)

在本文中，我们将学习如何使用 java 在 android 中添加 **KenBurns View** 。KenBurns 视图是一个有用的库，是 ImageView 的扩展。它通过制作其 Drawable 的动画来创建沉浸式体验。我们可以使用**随机过渡生成器**来更改持续时间，并充当过渡的插值器。如果我们想对过渡有更多的控制，那么我们可以实现我们自己的**过渡生成器**。
**进场:**

1.  在 **[build.gradle](https://www.geeksforgeeks.org/android-build-gradle/)** 文件中添加支持库，并在依赖项部分添加依赖项。通过这个肯伯恩斯视图可以直接添加到 xml 文件中，并有许多内置的功能来轻松定制它。

    ```
    dependencies {         
          implementation 'com.flaviofaria:kenburnsview:1.0.7'      
    }         
    ```

2.  现在在 **activity_main.xml** 文件中添加以下代码。在这个文件中，我们在布局中添加了肯伯恩斯视图。

    ## activity _ main . XML

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <androidx.constraintlayout.widget.ConstraintLayout
        xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:app="http://schemas.android.com/apk/res-auto"
        xmlns:tools="http://schemas.android.com/tools"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        tools:context=".MainActivity">

        <com.flaviofaria.kenburnsview.KenBurnsView
            android:id="@+id/kView"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:scaleType="fitXY"
            android:src="@drawable/g"
            app:layout_constraintBottom_toBottomOf="parent"
            app:layout_constraintLeft_toLeftOf="parent"
            app:layout_constraintRight_toRightOf="parent"
            app:layout_constraintTop_toTopOf="parent" />

    </androidx.constraintlayout.widget.ConstraintLayout>
    ```

3.  现在在**MainActivity.java**文件中添加以下代码。onClickListener 添加了 kenBurns 视图。如果动画处于运动状态，它会使动画暂停，反之亦然。

    ## MainActivity.java

    ```
    package org.geeksforgeeks.gfganimatedGradient;

    import androidx.appcompat.app.AppCompatActivity;
    import android.os.Bundle;
    import android.view.View;
    import android.view.animation.AccelerateDecelerateInterpolator;
    import com.flaviofaria.kenburnsview.KenBurnsView;
    import com.flaviofaria.kenburnsview.RandomTransitionGenerator;

    public class MainActivity extends AppCompatActivity {
        KenBurnsView kenBurnsView;
        boolean moving = true;

        @Override
        protected void onCreate(Bundle savedInstanceState)
        {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_main);

            kenBurnsView = findViewById(R.id.kView);

            AccelerateDecelerateInterpolator interpolator
                = new AccelerateDecelerateInterpolator();

            // It is used to change the duration and
            // the interpolator of transitions
            RandomTransitionGenerator generator
                = new RandomTransitionGenerator(2000, interpolator);
            kenBurnsView.setTransitionGenerator(generator);

            kenBurnsView.setOnClickListener(new View.OnClickListener() {
                @Override
                public void onClick(View v)
                {
                    if (moving) {
                        kenBurnsView.pause();
                        moving = false;
                    }
                    else {
                        kenBurnsView.resume();
                        moving = true;
                    }
                }
            });
        }
    }
    ```

4.  现在编译并运行安卓应用。

**输出:**

<video class="wp-video-shortcode" id="video-425412-1" width="320" height="540" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200605125906/Record_2020-06-05-12-56-45_de653d391fd57e9d09033828c1f8381e.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200605125906/Record_2020-06-05-12-56-45_de653d391fd57e9d09033828c1f8381e.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200605125906/Record_2020-06-05-12-56-45_de653d391fd57e9d09033828c1f8381e.mp4)</video>