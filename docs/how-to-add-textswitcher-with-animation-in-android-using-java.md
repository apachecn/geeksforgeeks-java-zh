# 如何用 Java 在安卓中添加带动画的 TextSwitcher】

> 原文:[https://www . geesforgeks . org/how-add-text switcher-with-animation-in-Android-use-Java/](https://www.geeksforgeeks.org/how-to-add-textswitcher-with-animation-in-android-using-java/)

一个 **[文本切换器](https://developer.android.com/reference/android/widget/TextSwitcher)** 用于在屏幕上激活文本。它是 **[视图切换器](https://developer.android.com/reference/android/widget/ViewSwitcher)** 类的子类。它只包含一个 TextView 类型的子级。为了在文本切换器上设置动画，我们必须添加动画标签，或者我们可以编程添加。以下是文本切换器的一些用法:

*   **在日期选择器中更改数字**
    *   **Countdown of timer clock**

        文本切换器使用两种类型的动画:

        *   **动画中**
        *   **输出动画**

        **进场:**

        1.  在 **activity_main.xml** 文件中添加以下代码。

            ## activity _ main . XML

            ```
            <?xml version="1.0" encoding="utf-8"?>
            <RelativeLayout 
                xmlns:android="http://schemas.android.com/apk/res/android"
                xmlns:app="http://schemas.android.com/apk/res-auto"
                xmlns:tools="http://schemas.android.com/tools"
                android:layout_width="match_parent"
                android:layout_height="match_parent"
                tools:context=".MainActivity">

                <TextSwitcher
                    android:id="@+id/textSwitcher"
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:layout_marginTop="80dp"
                    android:inAnimation="@android:anim/slide_in_left"
                    android:outAnimation="@android:anim/slide_out_right" />

                <Button
                    android:id="@+id/button"
                    android:textSize="20sp"
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:layout_centerHorizontal="true"
                    android:layout_centerVertical="true"
                    android:text="Next" />

            </RelativeLayout>
            ```

        2.  现在在**MainActivity.java**文件中添加以下代码。

            ## MainActivity.java

            ```
            package com.madhav.maheshwari.gfgTextSwitcher;

            import android.graphics.Color;
            import android.os.Bundle;
            import android.view.Gravity;
            import android.view.View;
            import android.widget.Button;
            import android.widget.TextSwitcher;
            import android.widget.TextView;
            import android.widget.ViewSwitcher;

            import androidx.appcompat.app.AppCompatActivity;

            public class MainActivity extends AppCompatActivity {
                private TextSwitcher textSwitcher;
                private Button nextButton;
                private int index = 0;
                private String[] arr
                    = { "GeeksForGeeks", "A",
                        "Computer", "Science",
                        "Portal", "For",
                        "Geeks" };
                private TextView textView;

                @Override
                protected void onCreate(
                    Bundle savedInstanceState)
                {
                    super.onCreate(savedInstanceState);
                    setContentView(R.layout.activity_main);

                    textSwitcher = findViewById(R.id.textSwitcher);
                    nextButton = findViewById(R.id.button);
                    nextButton.setOnClickListener(
                        new View.OnClickListener() {
                            @Override
                            public void onClick(View v)
                            {

                                // when the text switcher
                                // reaches at the end
                                // of our array. It will
                                // be reset to 0.
                                if (index == arr.length - 1) {
                                    index = 0;
                                    textSwitcher.setText(arr[index]);
                                }
                                else {
                                    textSwitcher.setText(arr[++index]);
                                }
                            }
                        });

                    // Here we have to create
                    // a TextView for our TextSwitcher
                    textSwitcher.setFactory(
                        new ViewSwitcher.ViewFactory() {
                            @Override
                            public View makeView()
                            {
                                textView
                                    = new TextView(
                                        MainActivity.this);
                                textView.setTextColor(
                                    Color.parseColor("#219806"));

                                textView.setTextSize(40);
                                textView.setGravity(
                                    Gravity.CENTER_HORIZONTAL);
                                return textView;
                            }
                        });

                    // This is used to set the text
                    // when app starts which is
                    // at index i.e 0.
                    textSwitcher.setText(arr[index]);
                }
            }
            ```

        **输出:**

        <video class="wp-video-shortcode" id="video-411708-1" width="665" height="739" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200507201203/Record_2020-05-07-14-48-35_57221fc09667155554b960549e018558.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200507201203/Record_2020-05-07-14-48-35_57221fc09667155554b960549e018558.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200507201203/Record_2020-05-07-14-48-35_57221fc09667155554b960549e018558.mp4)</video>