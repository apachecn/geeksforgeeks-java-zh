# 如何在安卓中更改输入法动作按钮？

> 原文:[https://www . geesforgeks . org/how-change-input-method-action-button in-Android/](https://www.geeksforgeeks.org/how-to-change-input-method-action-button-in-android/)

本文中，根据我们的要求，在安卓系统中更改了 **IME** (输入法动作)选项。输入法操作按钮位于软键盘的右下角。默认情况下，系统将此按钮用于“下一步”或“完成”操作，除非您的文本字段允许多行文本，在这种情况下，操作按钮是回车。但是，您可以指定可能更适合您的文本字段的其他操作，如“开始”、“发送”、“上一个”、“无”等。“下一步”和“完成”的 IME 选项如下所示。

*   下一步行动
*   Action Done
    1.  在 **activity_main.xml** 文件中添加以下代码。在这个文件中，我们根据需要为编辑文本指定 IME 选项。此处添加了一个图像视图和两个编辑文本，并为**操作完成**指定了 IME 选项。

        ## activity _ main . XML

        ```java
        <?xml version="1.0" encoding="utf-8"?>
        <LinearLayout
            xmlns:android="http://schemas.android.com/apk/res/android"
            xmlns:tools="http://schemas.android.com/tools"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:orientation="vertical"
            tools:context=".MainActivity">

            <ImageView
                android:layout_gravity="center"
                android:layout_marginTop="50dp"
                android:layout_width="200dp"
                android:layout_height="200dp"
                android:src="@drawable/gfg"
                />

            <EditText
                android:layout_marginTop="50dp"
                android:layout_marginStart="10dp"
                android:layout_marginEnd="10dp"
                android:id="@+id/editText1"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:hint="Username"
                android:paddingBottom="20dp"
                android:inputType="text" />

            <EditText
                android:paddingTop="20dp"
                android:layout_margin="10dp"
                android:id="@+id/editText2"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:hint="Password"
                android:imeOptions="actionDone"
                android:inputType="textPassword" />

        </LinearLayout>
        ```

    现在在**MainActivity.java**文件中添加以下代码。在这个文件中，我们将侦听器添加到我们的编辑文本中，这将相应地对应于我们的操作。在这里，我们覆盖一个编辑操作方法，并为**操作完成**和**操作下一个** IME 选项显示祝酒词。

    ## MainActivity.java

    ```java
    package org.geeksforgeeks.imeoption;

    import androidx.appcompat.app.AppCompatActivity;
    import android.os.Bundle;
    import android.view.KeyEvent;
    import android.view.inputmethod.EditorInfo;
    import android.widget.EditText;
    import android.widget.TextView;
    import android.widget.Toast;

    public class MainActivity extends AppCompatActivity {

        @Override
        protected void onCreate(Bundle savedInstanceState)
        {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_main);

            EditText login = findViewById(R.id.editText1);
            EditText password = findViewById(R.id.editText2);

            login.setOnEditorActionListener(actionListener);
            password.setOnEditorActionListener(actionListener);
        }

        // whenever the user clicks on IME button this listener will
        // get invoked automatically.
        private TextView.OnEditorActionListener actionListener
            = new TextView.OnEditorActionListener() {
                  @Override
                  public boolean onEditorAction(TextView v,
                                                int actionId, KeyEvent event)
                  {
                      switch (actionId) {

                      case EditorInfo.IME_ACTION_NEXT:
                          Toast.makeText(MainActivity.this,
                                         "Next", Toast.LENGTH_SHORT)
                              .show();
                          break;

                      case EditorInfo.IME_ACTION_DONE:
                          Toast.makeText(MainActivity.this,
                                         "Login", Toast.LENGTH_SHORT)
                              .show();
                          break;
                      }
                      return false;
                  }
              };
    }
    ```