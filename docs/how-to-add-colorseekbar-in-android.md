# 如何在安卓中添加 ColorSeekBar

> 原文:[https://www . geesforgeks . org/how-add-colorseekbar-in-Android/](https://www.geeksforgeeks.org/how-to-add-colorseekbar-in-android/)

[**Seekbar**](https://www.geeksforgeeks.org/seekbar-in-kotlin/) 是进度条的一种类型。我们可以将 seekbar 从左向右拖动，反之亦然，从而改变当前进度。 **ColorSeekbar** 与 Seekbar 类似，但是我们使用它从多种颜色中选择一种颜色，并且可以选择任何自定义颜色。在这个小部件的帮助下，我们可以给用户更多的控制权来根据他的需要定制它的应用程序。

**进场:**

1.  将支持库添加到您的根 [**build.gradle**](https://www.geeksforgeeks.org/android-build-gradle/) 文件中(不是您的模块 build.gradle 文件)。这个库 jitpack 是一个新颖的包存储库。它是为 JVM 而做的，这样任何存在于[**【github】**](https://www.geeksforgeeks.org/ultimate-guide-git-github/)和 [**bigbucket**](https://www.geeksforgeeks.org/bitbucket-vs-github-vs-gitlab/) 中的库都可以直接在应用中使用。

    ```java
    allprojects {
        repositories {
            maven { url "https://jitpack.io" }
        }
    }
    ```

2.  在 **[build.gradle](https://www.geeksforgeeks.org/android-build-gradle/)** 文件中添加支持库，并在依赖项部分添加依赖项。这个库提供了各种内置的功能，我们可以使用这些功能给用户最大的独立性来定制。

```java
dependencies {
    implementation 'com.github.rtugeek:colorseekbar:1.7.7'
}
```

*   现在在 [**值**](https://www.geeksforgeeks.org/android-res-values-folder/) 目录的 **strings.xml** 文件中添加一组颜色， **custom_colors** 。

    ## 字符串

    ```java
    <array name="custom_colors">

                <item>#219806</item>
                <item>#F44336</item>
                <item>#FFEB3B</item>

    </array>
    ```

    *   现在在 **activity_main.xml** 文件中添加以下代码。这将在 activity_main 中添加一个 **textview** 和一个 **colorSeekbar** 。在这个文件中，我们将我们的数组**自定义颜色**添加到 Seekbar 中。

    ## activity _ main . XML

    ```java
    <?xml version="1.0" encoding="utf-8"?>
    <LinearLayout 
        xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:app="http://schemas.android.com/apk/res-auto"
        xmlns:tools="http://schemas.android.com/tools"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:gravity="center"
        android:orientation="vertical"
        android:padding="16dp"
        tools:context=".MainActivity">

        <TextView
            android:id="@+id/text_view"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="GeeksForGeeks"
            android:textSize="30sp"
            android:textStyle="bold" />

        <com.rtugeek.android.colorseekbar.ColorSeekBar
            android:id="@+id/color_seek_bar"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            app:colorSeeds="@array/custom_colors"
            app:showAlphaBar="true" />

    </LinearLayout>
    ```

    *   Now add the following code in the **MainActivity.java** file. **onClickListener** is added with the seekbar. As the value is changes via seekbar the onClickListener is invoked and color of texts in textview changes.

    ## MainActivity.java

    ```java
    package org.geeksforgeeks.colorseekbar;

    import androidx.appcompat.app.AppCompatActivity;
    import android.os.Bundle;
    import android.widget.TextView;
    import com.rtugeek.android.colorseekbar.ColorSeekBar;

    public class MainActivity
        extends AppCompatActivity {

        TextView textView;

        @Override
        protected void onCreate(
            Bundle savedInstanceState)
        {

            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_main);

            textView = findViewById(
                R.id.text_view);
            ColorSeekBar
                colorSeekBar
                = findViewById(
                    R.id.color_seek_bar);

            colorSeekBar.setOnColorChangeListener(
                new ColorSeekBa
                    r.OnColorChangeListener() {

                        @Override
                        public void
                        onColorChangeListener(
                            int i, int i1, int i2)
                        {
                            textView
                                .setTextColor(i2);
                        }
                    });
        }
    }
    ```

    **输出:**

    <video class="wp-video-shortcode" id="video-416921-1" width="320" height="540" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200515132427/Record_2020-05-15-13-23-04_1a4811e1943b5c025442b43456dabc2c.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200515132427/Record_2020-05-15-13-23-04_1a4811e1943b5c025442b43456dabc2c.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200515132427/Record_2020-05-15-13-23-04_1a4811e1943b5c025442b43456dabc2c.mp4)</video>