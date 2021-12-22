# 如何在安卓系统中与另一个应用共享你的应用的文本，反之亦然？

> 原文:[https://www . geesforgeks . org/如何与安卓中的另一个应用程序共享您的应用程序文本/](https://www.geeksforgeeks.org/how-to-share-text-of-your-app-with-another-app-in-android/)

大多数情况下，在使用一个应用程序时，我们希望将该应用程序中的文本共享给另一个应用程序。在使用许多社交媒体平台时，当我们想要在一个应用程序和另一个应用程序之间共享信息时，我们发现这个功能非常有用。当将数据发送到另一个应用程序时，安卓意图解析器被用作定义明确的任务流的一部分。要使用安卓意图解析器，创建一个意图并添加额外内容。在这里，我们将了解如何做到这一点。此外，我们将在本文中实现反过来(另一个应用到你的应用)案例。

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

转到 **activity_main.xml** 文件，参考以下代码。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

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
    tools:context=".MainActivity">

    <!--Here we will be input out=r text share-->
    <EditText
        android:id="@+id/text"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:hint="write Something here to share"
        android:textColor="#000"
        android:textSize="22sp" />

    <!--We will click on it then shareonlytext
        function will be called-->
    <Button
        android:id="@+id/share"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="10dp"
        android:background="@color/black"
        android:padding="5dp"
        android:text="Share"
        android:textSize="10dp" />

</LinearLayout>
```

**步骤 3:使用 MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

public class MainActivity extends AppCompatActivity {

    Button share;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        share = findViewById(R.id.share);

        // initialising text field where we will enter data
        final EditText editText = findViewById(R.id.text);
        share.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Now share text only function will be called
                // here we  will be passing the text to share
                shareTextOnly(editText.getText().toString());
            }
        });
    }

    private void shareTextOnly(String titlee) {
        String sharebody = titlee;

        // The value which we will sending through data via
        // other applications is defined
        // via the Intent.ACTION_SEND
        Intent intentt = new Intent(Intent.ACTION_SEND);

        // setting type of data shared as text
        intentt.setType("text/plain");
        intentt.putExtra(Intent.EXTRA_SUBJECT, "Subject Here");

        // Adding the text to share using putExtra
        intentt.putExtra(Intent.EXTRA_TEXT, sharebody);
        startActivity(Intent.createChooser(intentt, "Share Via"));
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-566679-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210226010752/sharetext1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210226010752/sharetext1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210226010752/sharetext1.mp4)</video>

## 反之亦然

假设我们正在开发一个聊天应用程序。在这种情况下，我们可能希望与我们应用程序的一些用户共享另一个应用程序中的文本。这里基本上我们正在做的是从谷歌上获取文本，并在我们的应用程序中共享，然后在编辑文本中输入该文本。在这种情况下，我们需要编写一些代码来在我们的应用程序中实现这个功能(从另一个应用程序共享文本到我们的应用程序)。

### **分步实施**

**第一步:创建新项目**

在安卓工作室创建新项目请参考 [<u>【如何在安卓工作室创建/启动新项目】</u>](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/) 。注意选择 **Java** 作为编程语言。

**步骤 2:使用 AndroidManifest.xml 文件**

为了向 Firebase 添加数据，我们应该授予访问互联网的权限。要添加这些权限，请导航至**应用程序> AndroidManifest.xml** ，并在该文件中添加以下权限。

```java
<uses-permission android:name="android.permission.INTERNET" />
```

另外，在清单文件中进行以下更改。完整的 **AndroidManifest.xml** 文件如下。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.sharetext">

    <uses-permission android:name="android.permission.INTERNET" />

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.ShareText">
        <activity android:name=".MainActivity">

            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>

            <intent-filter>
                <action android:name="android.intent.action.SEND" />

                <category android:name="android.intent.category.DEFAULT" />

                <data android:mimeType="image/*" />
            </intent-filter>

            <intent-filter>
                <action android:name="android.intent.action.SEND" />

                <category android:name="android.intent.category.DEFAULT" />

                <data android:mimeType="text/plain" />
            </intent-filter>

        </activity>
    </application>

</manifest>
```

**步骤 3:使用 activity_main.xml 文件**

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
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/gettext"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:hint="Get text"
        android:textSize="22sp"
        android:textStyle="bold" />

</LinearLayout>
```

**第四步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.content.Intent;
import android.os.Bundle;
import android.widget.EditText;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText gettext;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        gettext = findViewById(R.id.gettext);

        // initiating the intent
        Intent intent = getIntent();
        String action = intent.getAction();

        // getting type of content shared
        String type = intent.getType();

        // if value is not null then show the content
        if (Intent.ACTION_SEND.equals(action) && type != null) {
            handlesendText(intent);
        }
    }

    private void handlesendText(Intent intent) {
        // here we are getting the text
        String sharedText = intent.getStringExtra(Intent.EXTRA_TEXT);
        if (sharedText != null) {
            // showing the text in edittext
            gettext.setText(sharedText);
        }
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-566679-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210226013234/gettext.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210226013234/gettext.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210226013234/gettext.mp4)</video>