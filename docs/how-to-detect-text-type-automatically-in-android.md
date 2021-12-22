# 如何在安卓系统中自动检测文字类型？

> 原文:[https://www . geesforgeks . org/如何在安卓中自动检测文本类型/](https://www.geeksforgeeks.org/how-to-detect-text-type-automatically-in-android/)

在本文中，我们将实现一个与 TextView 相关的特性，它在每个视角中都非常重要。在使用任何社交媒体应用程序或笔记应用程序时，您可能已经看到，当我们键入某些内容时，它会自动检测文本类型，如电子邮件、电话或网址。这里我们将实现这个特性。下面给出了一个示例视频，以了解我们将在本文中做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-593579-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210420234736/autotext.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210420234736/autotext.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210420234736/autotext.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/mobile"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="10dp"
        android:textColor="@color/black"
        android:textSize="32sp" />

    <TextView
        android:id="@+id/email"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="15dp"
        android:textColor="@color/black"
        android:textSize="32sp" />

    <TextView
        android:id="@+id/google"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="15dp"
        android:textColor="@color/black"
        android:textSize="32sp" />

</LinearLayout>
```

**第三步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。这就是我们如何实现文本的自动检测文本类型

> Linkify.addLinks(电子邮件，Linkify。ALL)；

以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.os.Bundle;
import android.text.util.Linkify;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        //initialising the layout
        TextView mobile = (TextView) findViewById(R.id.mobile);
        TextView google = (TextView) findViewById(R.id.google);
        TextView email = (TextView) findViewById(R.id.email);

        // setting the email
        email.setText("kumarianni1213@gmail.com");

        // setting the mobile number
        mobile.setText("+919065239713");

        // setting the web url to visit
        google.setText("www.google.com");

        // linking all type of text
        Linkify.addLinks(email, Linkify.ALL);
        Linkify.addLinks(mobile, Linkify.ALL);
        Linkify.addLinks(google, Linkify.ALL);
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-593579-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210420234736/autotext.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210420234736/autotext.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210420234736/autotext.mp4)</video>