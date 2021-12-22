# 如何在安卓

中添加淡入淡出的 TextView 动画

> 原文:[https://www . geesforgeks . org/how-add-fading-textview-animation-in-Android/](https://www.geeksforgeeks.org/how-to-add-fading-textview-animation-in-android/)

**[TextView](https://www.geeksforgeeks.org/textview-widget-in-android-using-java-with-examples/)** 是用户界面组件的基本构建模块。它用于设置文本并将其显示给用户。它是一个非常基本的组件，使用了很多。

一个**渐变文本视图**是一个每几秒钟自动改变其内容的文本视图。如果我们想设计一个比我们可以使用衰落文本视图更漂亮的界面。

**进场:**

1.  将此添加到您的根 **[build.gradle](https://www.geeksforgeeks.org/android-build-gradle/)** 文件中(不是您的模块 build.gradle 文件):

```
allprojects {
    repositories {
           jcenter()
    }
}
```

*   在模块的 **[build.gradle](https://www.geeksforgeeks.org/android-build-gradle/)** 文件中添加支持库，并在依赖项部分添加依赖项。

    ```
    dependencies {
        implementation 'com.tomer:fadingtextview:2.5'
    }
    ```

    *   现在在 **activity_main.xml** 文件中添加以下代码。

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

        <com.tomer.fadingtextview.FadingTextView
            android:id="@+id/fadingTextView"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:textSize="22sp"
            android:textColor="#2AC308"
            android:textStyle="bold"
            app:timeout="500"
            app:layout_constraintBottom_toBottomOf="parent"
            app:layout_constraintLeft_toLeftOf="parent"
            app:layout_constraintRight_toRightOf="parent"
            app:layout_constraintTop_toTopOf="parent" />

    </androidx.constraintlayout.widget.ConstraintLayout>
    ```

    *   Now add the following code in the **MainActivity.java** file.

    ## MainActivity.java

    ```
    package org.geeksforgeeks.gfgFadingTextView;

    import androidx.appcompat.app.AppCompatActivity;
    import android.os.Bundle;
    import com.tomer.fadingtextview.FadingTextView;

    public class MainActivity extends AppCompatActivity {

        FadingTextView fadingTextView;
        String[] text
            = { "GeeksForGeeks", "A",
                "Computer", "Science", "Portal",
                "For", "Geeks" };

        @Override
        protected void onCreate(Bundle savedInstanceState)
        {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_main);

            fadingTextView
                = findViewById(R.id.fadingTextView);
            fadingTextView.setTexts(text);
        }
    }
    ```

    **输出:**

    <video class="wp-video-shortcode" id="video-411713-1" width="665" height="739" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200507013947/Record_2020-05-06-19-55-21_a2713a04fe48232cffc9a346995b5281.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200507013947/Record_2020-05-06-19-55-21_a2713a04fe48232cffc9a346995b5281.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200507013947/Record_2020-05-06-19-55-21_a2713a04fe48232cffc9a346995b5281.mp4)</video>