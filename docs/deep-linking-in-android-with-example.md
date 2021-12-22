# 安卓深度链接示例

> 原文:[https://www . geeksforgeeks . org/深度链接-带示例的安卓/](https://www.geeksforgeeks.org/deep-linking-in-android-with-example/)

**深度链接**是各种应用程序用来以 URL 链接的形式收集其应用程序内部数据的最重要功能之一。因此，其他应用程序的用户可以轻松地与不同的应用程序共享数据，这变得很有帮助。在本文中，我们将看看深度链接在我们的安卓应用程序中的实现。

### 什么是深层联系？

深度链接是一个生成的网址链接，当任何人点击该链接时，我们的应用程序将打开一个特定的活动或屏幕。使用这个网址，我们可以向我们的应用程序发送带有参数的消息。在 WhatsApp 中，我们可以生成一个深度链接，将消息发送到包含某些消息的电话号码。深度链接用于打开带有网址链接的应用程序特定屏幕。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，在其中我们将创建一个深度链接，点击该链接，我们将把我们的消息传递给我们的应用程序，并在文本视图中显示该消息。下面给出了一个示例视频，让我们了解一下在本文中要做什么。请注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-553332-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210128101827/Screenrecorder-2021-01-28-10-14-37-248.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210128101827/Screenrecorder-2021-01-28-10-14-37-248.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210128101827/Screenrecorder-2021-01-28-10-14-37-248.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:weightSum="5"
    tools:context=".MainActivity">

    <!--text view for displaying welcome message-->
    <TextView
        android:id="@+id/idTVWelcome"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:padding="10dp"
        android:text="Welcome to "
        android:textAlignment="center"
        android:textAllCaps="false"
        android:textColor="@color/purple_500"
        android:textSize="30sp" />

    <!--text view for displaying the organization
        name from the link which we have generated-->
    <TextView
        android:id="@+id/idTVMessage"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idTVWelcome"
        android:text="Organization Name"
        android:textAlignment="center"
        android:textAllCaps="false"
        android:textColor="@color/purple_500"
        android:textSize="30sp"
        android:textStyle="bold" />

</RelativeLayout>
```

**第 3 步:使用 AndroidManifest.xml 文件**

导航到**应用程序> AndroidManifest.xml** ，并在其中添加以下代码。因为我们正在为我们的**MainActivity.java**文件创建一个深度链接，所以我们必须在主活动部分添加这段代码。下面是将要添加到**和**文件中的代码。代码中添加了注释，以便更详细地了解。

## 可扩展标记语言

```
<!--as we want to open main activity from our link so we are specifying
    only in main activity or we can specify that in different activity as well
    on below line we are adding intent filter to our MainActivity-->
<intent-filter>
  <!--below line is to set the action to our intent to view-->
  <action android:name="android.intent.action.VIEW" />

  <!--on below line we are adding a default category to our intent-->
  <category android:name="android.intent.category.DEFAULT" />

  <!--on below line we are adding a category to make our app browsable-->
  <category android:name="android.intent.category.BROWSABLE" />

  <!--on below line we are specifying the host name and
      the scheme type from which we will be calling our app-->
   <data
        android:host="www.chaitanyamunje.com"
        android:scheme="https" />
</intent-filter>

<!--below is the same filter as above just the scheme is changed to http -->
<!--so we can open our app with the url starting with https and http as well-->
<intent-filter>
  <action android:name="android.intent.action.VIEW" />

  <category android:name="android.intent.category.DEFAULT" />
  <category android:name="android.intent.category.BROWSABLE" />

  <data
    android:host="www.chaitanyamunje.com"
    android:scheme="http" />
</intent-filter>
```

下面是 **AndroidManifest.xml** 文件的完整代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.deeplinks">

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.DeepLinks">
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>

            <!--as we want to open main activity from our link so we are specifying
                only in main activity or we can specify that in different activity as well-->
            <!--on below line we are adding intent filter to our MainActivity-->
            <intent-filter>
                <!--below line is to set the action to our intent to view-->
                <action android:name="android.intent.action.VIEW" />
                <!--on below line we are adding a default category to our intent-->
                <category android:name="android.intent.category.DEFAULT" />
                <!--on below line we are adding a category to make our app browsable-->
                <category android:name="android.intent.category.BROWSABLE" />
                <!--on below line we are specifying the host name and
                    the scheme type from which we will be calling our app-->
                <data
                    android:host="www.chaitanyamunje.com"
                    android:scheme="https" />
            </intent-filter>

            <!--below is the same filter as above just the scheme is changed to http -->
            <!--so we can open our app with the url starting with https and http as well-->
            <intent-filter>
                <action android:name="android.intent.action.VIEW" />

                <category android:name="android.intent.category.DEFAULT" />
                <category android:name="android.intent.category.BROWSABLE" />

                <data
                    android:host="www.chaitanyamunje.com"
                    android:scheme="http" />
            </intent-filter>

        </activity>
    </application>
</manifest>
```

**第四步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
package com.example.deeplinks;

import android.net.Uri;
import android.os.Bundle;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

import java.util.List;

public class MainActivity extends AppCompatActivity {

    // creating a variable for our text view
    private TextView messageTV;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initializing our variable
        messageTV = findViewById(R.id.idTVMessage);

        // getting the data from our
        // intent in our uri.
        Uri uri = getIntent().getData();

        // checking if the uri is null or not.
        if (uri != null) {
            // if the uri is not null then we are getting the 
            // path segments and storing it in list.
            List<String> parameters = uri.getPathSegments();

            // after that we are extracting string from that parameters.
            String param = parameters.get(parameters.size() - 1);

            // on below line we are setting
            // that string to our text view
            // which we got as params.
            messageTV.setText(param);
        }
    }
}
```

现在我们已经在我们的安卓清单文件中添加了网址**https://www.chaitanyamunje.com/hello/GeeksForGeeks**。我们将向 MainActivity.java 文件发送消息的网址。在上面的网址中，“https”是我们的方案，“www.chaitanyamunje.com”是我们的主机名，“hello”是我们的第一个参数，“GeeksForGeeks”是第二个参数，我们将在我们的应用程序中显示为组织名称。您可以根据自己的要求更改参数。现在运行您的应用程序，并查看应用程序的输出。

### **输出:**

运行应用程序后，您将看到“组织名称”文本，现在关闭应用程序，并从安装应用程序的设备中单击上面显示的链接。点击该链接后，将显示一条弹出消息来选择应用程序。在弹出消息中，选择您的应用程序，您的应用程序将被打开。我们传递的信息是“极客博客”，将显示在组织名称的位置。

<video class="wp-video-shortcode" id="video-553332-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210128101827/Screenrecorder-2021-01-28-10-14-37-248.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210128101827/Screenrecorder-2021-01-28-10-14-37-248.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210128101827/Screenrecorder-2021-01-28-10-14-37-248.mp4)</video>