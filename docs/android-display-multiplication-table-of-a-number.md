# 安卓|显示一个数字的乘法表

> 原文:[https://www . geesforgeks . org/Android-display-乘法表-数字/](https://www.geeksforgeeks.org/android-display-multiplication-table-of-a-number/)

给定一个数，任务是用安卓 App 显示这个数的乘法表。

**构建应用的步骤:**

*   **STEP-1:** 打开 **activity_main.xml** 文件，添加文本视图、编辑文本和一个按钮
*   **步骤 2:** 为每个组件分配标识
*   **STEP-3:** 现在，打开 MainActivity 文件并声明变量。
*   **STEP-4:** 使用上面 XML 代码中设置的 id 读取编辑文本框中输入的值。
*   **STEP-5:** 向添加按钮添加点击监听器
*   **STEP-6:** 点击添加按钮后，我们需要将数值相乘并存储在缓冲区中
*   **STEP-7:** 然后通过在文本视图中设置缓冲区，在文本视图中显示结果输出。

**实施:**

**文件名:activity_main.xml**

## 可扩展标记语言

```
<!-- First make the layout file xml and add button, edit text, text view -->

<?xml version="1.0" encoding="utf-8"?>
<android.support.constraint.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    tools:layout_editor_absoluteY="25dp">

    <!-- Add the button for run table logic and print result-->
    <!-- give id "button"-->
    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:text="TABLE"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toEndOf="@+id/editText"
        app:layout_constraintTop_toTopOf="parent" />

    <!-- Text view for result view-->
    <!-- give the id TextView-->
    <TextView
        android:id="@+id/textView"
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:layout_marginBottom="18dp"
        android:layout_marginEnd="36dp"
        android:layout_marginLeft="36dp"
        android:layout_marginRight="36dp"
        android:layout_marginStart="36dp"
        android:textColor="@color/colorPrimary"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/editText" />

    <!-- edit Text for take input from user-->
    <!-- give the id editText-->
    <EditText
        android:id="@+id/editText"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="20dp"
        android:layout_marginEnd="9dp"
        android:layout_marginRight="9dp"
        android:layout_marginTop="16dp"
        android:ems="10"
        android:inputType="number"
        app:layout_constraintBottom_toTopOf="@+id/textView2"
        app:layout_constraintEnd_toStartOf="@+id/button"
        app:layout_constraintHorizontal_chainStyle="packed"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        tools:ignore="UnknownId" />
</android.support.constraint.ConstraintLayout>
```

**文件名:MainActivity。Java〔t1〕**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Build the java logic for multiplication table
// using button, text view, edit text

package com.example.windows10.table;

import android.app.Dialog;
import android.content.Intent;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

public class MainActivity
    extends AppCompatActivity
    implements View.OnClickListener {

    // define the global variable

    // variable number1, number2 for input input number
    // Add_button, result textView

    EditText editText;
    Button button;
    TextView result;
    int ans = 0;

    protected void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // by ID we can use each component
        // whose id is assigned in the XML file

        editText = (EditText)findViewById(R.id.editText);
        button = (Button)findViewById(R.id.button);
        result = (TextView)findViewById(R.id.textView);

        // set clickListener on button
        button.setOnClickListener(this);
    }

    @Override
    public void onClick(View v)
    {

        switch (v.getId()) {

        case R.id.button:
            StringBuffer buffer = new StringBuffer();
            int res;

            // get the input number from editText
            String fs = editText.getText().toString();

            // convert it to integer
            int n = Integer.parseInt(fs);

            // build the logic for table
            for (int i = 1; i <= 10; i++) {
                ans = (i * n);
                buffer.append(n + " X " + i
                              + " = " + ans + "\n\n");
            }

            // set the buffer textview
            result.setText(buffer);
            break;
        }
    }
}
```

**输出:**

![](img/519096eb7a17e0504b417adbad87a52b.png)