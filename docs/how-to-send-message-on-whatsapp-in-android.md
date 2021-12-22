# 如何在安卓 WhatsApp 上发送消息

> 原文:[https://www . geesforgeks . org/how-to-message-on-whatsapp-in-Android/](https://www.geeksforgeeks.org/how-to-send-message-on-whatsapp-in-android/)

**Whatsapp** 是最受欢迎的消息应用之一。许多安卓应用程序需要直接从他们的应用程序向 WhatsApp 共享一些消息的功能。例如，如果用户想要共享该应用程序或共享来自该应用程序的消息，则使用该功能。用户可以发送文本，也可以通过此发送预定义的文本。本文演示了安卓应用程序如何在 WhatsApp 上发送消息。Whatsapp 必须安装在用户的设备上。

**接近**

**第一步:**打开 **activity_main.xml** 文件，添加布局代码。增加了[编辑文本](https://www.geeksforgeeks.org/edittext-widget-in-android-using-java-with-examples/)等消息输入容器和发送该消息的[按钮](https://www.geeksforgeeks.org/button-in-kotlin/)。

## activity_main.xml

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:orientation="vertical">

   <!-- EditText to take message input from user-->
   <EditText
       android:id="@+id/message"
       android:layout_width="match_parent"
       android:layout_height="wrap_content"
       android:layout_margin="16dp"
       android:hint="Enter you message here"
       android:lines="8"
       android:inputType="textMultiLine"
       android:gravity="left|top"
       />

   <!-- Button to send message on Whatsapp-->
   <Button
       android:id="@+id/submit"
       android:layout_width="wrap_content"
       android:layout_height="wrap_content"
       android:layout_gravity="center_horizontal"
       android:text="Submit"
       android:background="@color/colorPrimary"
       android:textColor="@android:color/white"/>

</LinearLayout>
```

**第二步:**取 Java 文件中 EditText 和 Button 的引用。在 findViewById()方法的帮助下，使用 Id 获取引用。

*   参考编辑文本

    > 编辑文本消息编辑文本=查找视图。消息)；

*   参考按钮

    > 按钮提交= findwiewbyid(r . id。提交)；

**第三步:**写函数给 whatsapp 发消息。用**动作 _ 发送**创建一个**意图**，并为此指定 whatsapp 包名，以便直接打开 whatsapp。

> **com.whatsapp** 是官方 whatsapp 应用的包名。

```
private void sendMessage(String message)
{

    // Creating new intent
    Intent intent
        = new Intent(Intent.ACTION_SEND);

    intent.setType("text/plain");
    intent.setPackage("com.whatsapp");

    // Give your message here
    intent.putExtra(
        Intent.EXTRA_TEXT,
        message);

    // Checking whether Whatsapp
    // is installed or not
    if (intent
            .resolveActivity(
                getPackageManager())
        == null) {
        Toast.makeText(
                 this,
                 "Please install whatsapp first.",
                 Toast.LENGTH_SHORT)
            .show();
        return;
    }

    // Starting Whatsapp
    startActivity(intent);
}
```

**第 4 步:**将**开监听器**设置为按钮。它接受用户输入的文本，并调用功能**发送消息**，其中文本消息作为参数发送。

```
submit.setOnClickListener(
    new View.OnClickListener() {
        @Override
        public void onClick(View view)
        {

            // Getting the text
            // from edit text
            String message
                = messageEditText
                      .getText()
                      .toString();

            // Calling the function
            // to send message
            sendMessage(message);
        }
    });
```

以下是完整的**MainActivity.java**文件:

## MainActivity.java

```
package com.gfg;

import androidx.appcompat
    .app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

public class MainActivity
    extends AppCompatActivity {

    @Override
    protected void onCreate(
        Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Taking reference of Edit Text
        final EditText messageEditText
            = findViewById(R.id.message);

        // Taking reference to button
        Button submit
            = findViewById(R.id.submit);

        submit.setOnClickListener(
            new View.OnClickListener() {
                @Override
                public void onClick(View view)
                {

                    // Getting the text
                    // from edit text
                    String message
                        = messageEditText
                              .getText()
                              .toString();

                    // Calling the function
                    // to send message
                    sendMessage(message);
                }
            });
    }

    private void sendMessage(String message)
    {

        // Creating new intent
        Intent intent
            = new Intent(
                Intent.ACTION_SEND);

        intent.setType("text/plain");
        intent.setPackage("com.whatsapp");

        // Give your message here
        intent.putExtra(
            Intent.EXTRA_TEXT,
            message);

        // Checking whether Whatsapp
        // is installed or not
        if (intent
                .resolveActivity(
                    getPackageManager())
            == null) {
            Toast.makeText(
                     this,
                     "Please install whatsapp first.",
                     Toast.LENGTH_SHORT)
                .show();
            return;
        }

        // Starting Whatsapp
        startActivity(intent);
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-421045-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200528210120/2020_05_28_20_50_08_trim.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200528210120/2020_05_28_20_50_08_trim.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200528210120/2020_05_28_20_50_08_trim.mp4)</video>