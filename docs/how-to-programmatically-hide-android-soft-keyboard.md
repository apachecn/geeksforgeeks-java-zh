# 如何编程隐藏安卓软键盘

> 原文:[https://www . geeksforgeeks . org/如何编程-隐藏-安卓-软键盘/](https://www.geeksforgeeks.org/how-to-programmatically-hide-android-soft-keyboard/)

在本文中，我们将学习如何以编程方式隐藏软键盘。键盘通常会隐藏，但在某些情况下它不会隐藏。所以为了更好的用户体验，键盘是以编程方式隐藏的。

**不使用下图方法，app 默认响应如下:-**

<video class="wp-video-shortcode" id="video-413410-1" width="440" height="520" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200513200946/Record_2020-05-13-20-08-52_750d96ee45c2372059ea1c16be9c6b891.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200513200946/Record_2020-05-13-20-08-52_750d96ee45c2372059ea1c16be9c6b891.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200513200946/Record_2020-05-13-20-08-52_750d96ee45c2372059ea1c16be9c6b891.mp4)</video>

**进场:**

1.  现在在 **activity_main.xml** 文件中添加以下代码。下面的代码在 activity_main 中添加了一个**文本视图**、**编辑文本**和一个**按钮**。点击该按钮将调用 MainActivity 类中的 **setText** 功能。

    ## activity _ main . XML

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <LinearLayout
        xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:tools="http://schemas.android.com/tools"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="vertical"
        android:padding="16dp"
        tools:context=".MainActivity">

        <TextView
            android:textStyle="bold"
            android:textColor="#219806"
            android:id="@+id/text_view_result"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="center_horizontal"
            android:text="GeeksForGeeks"
            android:textSize="22sp" />

        <EditText
            android:layout_marginTop="20dp"
            android:id="@+id/edit_text_input"
            android:layout_width="match_parent"
            android:layout_height="wrap_content" />

        <Button
            android:layout_marginTop="20dp"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="center_horizontal"
            android:onClick="setText"
            android:text="Set Text" />

    </LinearLayout>
    ```

2.  现在在**MainActivity.java**文件中添加以下代码。这里我们定义**设置文本**和**关闭键盘**功能。当用户点击按钮时，setText 函数被调用。它从 edittext 获取输入，并在 textview 中替换它。然后它调用 closeKeyboard 函数并清除 edittext 的值。closeKeyboard 功能隐藏键盘。

    ## MainActivity.java

    ```
    package org.geeksforgeeks.gfgHideKey

        import android.content.Context;
    import android.os.Bundle;
    import android.view.View;
    import android.view.inputmethod
        .InputMethodManager;
    import android.widget.EditText;
    import android.widget.TextView;

    public class MainActivity
        extends AppCompatActivity {
        private TextView textViewResult;
        private EditText editTextInput;

        @Override
        protected void onCreate(
            Bundle savedInstanceState)
        {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_main);

            textViewResult
                = findViewById(
                    R.id.text_view_result);
            editTextInput
                = findViewById(
                    R.id.edit_text_input);
        }

        public void setText(View v)
        {
            String newText
                = editTextInput
                      .getText()
                      .toString();
            textViewResult.setText(newText);

            closeKeyboard();
            editTextInput.setText("");
        }

        private void closeKeyboard()
        {
            // this will give us the view
            // which is currently focus
            // in this layout
            View view = this.getCurrentFocus();

            // if nothing is currently
            // focus then this will protect
            // the app from crash
            if (view != null) {

                // now assign the system
                // service to InputMethodManager
                InputMethodManager manager
                    = (InputMethodManager)
                        getSystemService(
                            Context.INPUT_METHOD_SERVICE);
                manager
                    .hideSoftInputFromWindow(
                        view.getWindowToken(), 0);
            }
        }
    }
    ```

**输出:**

<video class="wp-video-shortcode" id="video-413410-2" width="440" height="520" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200505213321/Record_2020-05-05-21-26-14_750d96ee45c2372059ea1c16be9c6b891.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200505213321/Record_2020-05-05-21-26-14_750d96ee45c2372059ea1c16be9c6b891.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200505213321/Record_2020-05-05-21-26-14_750d96ee45c2372059ea1c16be9c6b891.mp4)</video>