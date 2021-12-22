# 如何在安卓工作室搭建便利贴应用？

> 原文:[https://www . geesforgeks . org/how-to-build-a-sticks-notes-in-Android-studio/](https://www.geeksforgeeks.org/how-to-build-a-sticky-notes-application-in-android-studio/)

作为人类，我们倾向于忘记一些小而重要的事情，为了解决这个问题，我们试图把这些事情写下来，粘贴在某个地方，我们经常会看到。在这个数字时代，我们最有可能看到的东西是笔记本电脑、电脑或手机屏幕。为此，我们都曾经使用过 Windows 上的便利贴或 Mac 上的便利贴，今天在这篇文章中，我们将讨论如何为 Android 构建这样一个应用程序。

### 方法

现在，如果我们想到一些粘在屏幕上的东西，在安卓系统中，我们想到的组件是主屏幕小部件。主屏幕小部件是最好的交互式组件，可以粘在屏幕上，并可以以任何方式调整大小。我们将创建一个也有自己的小部件的应用程序。我们将首先在主应用程序中编写一些文本，并将其保存到内存中的一个文件中。此时，我们将使用用户刚刚保存的文本更新小部件。还有霍雷！我们的便利贴准备好了。

### 什么是主屏幕小部件？

这里需要注意的一点是，在安卓系统中，视图也被称为小部件，所以为了避免混淆，我们使用了主屏幕小部件这个术语。这些是提供交互组件的[广播接收器](https://www.geeksforgeeks.org/broadcast-receiver-in-android-with-example/)。它们通常显示某种信息，并鼓励用户与之互动。例如，它可以显示时间、天气或电子邮件，一旦你点击它们，主应用程序就会启动。小部件使用远程视图来构建其用户界面。使用与原始应用程序相同的权限，远程视图可以由另一种方法运行。因此，小部件以创建它的应用程序的权限运行。小部件的用户界面由广播接收器决定。这个接收器将其布局扩展成一个 RemoteView 对象。

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 AndroidManifest.xml 文件**

添加用户从存储读取和写入文件的权限。此外，为了注册小部件，我们必须创建一个带有意图过滤器的广播接收器。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.notes">

    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
    <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.Notes">
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>

        <!-- To register a widget, you create a broadcast receiver with
             an intent filter for the android.appwidget.action.APPWIDGET_UPDATE action-->
        <receiver
            android:name=".AppWidget"
            android:label="StickyNotes">
            <intent-filter>
                <action android:name="android.appwidget.action.APPWIDGET_UPDATE" />

            </intent-filter>
            <!-- This metadata contains the configuration of your widget,
                 the resource attribute contains the layout of your widget as
                 it will be seen in the list of widgets -->
            <meta-data
                android:name="android.appwidget.provider"
                android:resource="@xml/new_app_widget_info" />
        </receiver>

    </application>

</manifest>
```

**第 3 步:创建小部件**

按照本文中提到的步骤[创建一个安卓应用的基本小部件](https://www.geeksforgeeks.org/how-to-create-a-basic-widget-of-an-android-app/)将小部件添加到您的项目中。文件 **new_app_widget_info.xml** 包含确定我们的 widget 在 Widgets 列表中的外观的代码。

**第 4 步:使用 AppWidget 类**

这个类将在上一步中形成。转到**文件，参考以下代码。以下是**AppWidget.java**文件的代码。代码中添加了注释，以更详细地理解代码。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
import android.app.PendingIntent;
import android.appwidget.AppWidgetManager;
import android.appwidget.AppWidgetProvider;
import android.content.Context;
import android.content.Intent;
import android.widget.RemoteViews;

// Implementation of App Widget functionality
public class AppWidget extends AppWidgetProvider {

    // Create an Intent to launch activity
    @Override
    public void onUpdate(Context context, AppWidgetManager appWidgetManager, int[] appWidgetIds) {

        // Perform this loop procedure for each App Widget
        // that belongs to this provider
        for (int appWidgetId : appWidgetIds) {

            // Create an Intent to launch MainActivity
            Intent launchActivity = new Intent(context, MainActivity.class);

            // Attaching a Pending Intent 
            // to trigger it when
            // application is not alive
            PendingIntent pendingIntent = PendingIntent.getActivity(context, 0, launchActivity, 0);

            // Get the layout for the App Widget and attach
            // an on-click listener to the button
            RemoteViews remoteViews = new RemoteViews(context.getPackageName(), R.layout.new_app_widget);
            remoteViews.setOnClickPendingIntent(R.id.appwidget_text, pendingIntent);

            // Tell the AppWidgetManager to perform an
            // update on the current app widget
            appWidgetManager.updateAppWidget(appWidgetId, remoteViews);
        }
    }
}
```

****第五步:创建粘贴注释类****

**这是一个助手类，提供保存、更新和检索文件内容的功能。前往 **坚持注意。java** 文件并参考以下代码。以下是 **标签的代码。java** 文件。代码中添加了注释，以更详细地理解代码。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
import android.content.Context;

import java.io.BufferedReader;
import java.io.File;
import java.io.FileOutputStream;
import java.io.FileReader;
import java.io.IOException;

import static android.content.Context.MODE_PRIVATE;

class StickyNote {

    // this function will return
    // the content from the text
    // file(if any)
    String getStick(Context context) {

        // get the file from path
        File fileEvents = new File(context.getFilesDir().getPath() + "/gfg.txt");

        // create a StringBuilder to store the text from file
        StringBuilder text = new StringBuilder();

        try {
            // use the BufferedReader
            // to Read the file
            // efficiently
            BufferedReader br = new BufferedReader(new FileReader(fileEvents));
            String line;

            // read a single line at a time
            // append newline character after each line
            while ((line = br.readLine()) != null) {
                text.append(line);
                text.append('\n');
            }

            // close the BufferedReader
            br.close();
        } catch (IOException e) {
            e.printStackTrace();
        }

        // finally return the 
        // string i.e. the retrieved data
        // from file
        return text.toString();
    }

    // this function saves the new 
    // content in the file if it
    // exists or will create a new one
    void setStick(String textToBeSaved, Context context) {

        String text = textToBeSaved;

        // create the FileOutputStream 
        // to efficiently write the file
        FileOutputStream fos = null;
        try {
            // get the file from storage
            fos = context.getApplicationContext().openFileOutput("gfg.txt", MODE_PRIVATE);

            // write to the file at once
            fos.write(text.getBytes());
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (fos != null) {
                try {
                    fos.close();
                } catch (IOException e) {
                    e.printStackTrace();
                }
            }
        }
    }
}
```

****第 6 步:使用****MainActivity.java 文件****

**转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
import android.appwidget.AppWidgetManager;
import android.content.ComponentName;
import android.widget.EditText;
import android.widget.RemoteViews;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText mEditText;

    // creating a new note
    StickyNote note = new StickyNote();

    @Override
    protected void
    onCreate(android.os.Bundle savedInstanceState) {

        setContentView(R.layout.activity_main);
        super.onCreate(savedInstanceState);

        // getting the reference of the EditText
        mEditText = findViewById(R.id.editText);

        // retrieve the text from the saved file in
        // memory(if any) and set it to the edittext
        mEditText.setText(note.getStick(this));
    }

    // function to update the 
    // Widget(Sticky Note) every time
    // user saves the note
    public void updateWidget() {
        // the AppWidgetManager helps
        // us to manage all the
        // widgets from this app
        AppWidgetManager appWidgetManager = AppWidgetManager.getInstance(this);

        // the RemoteViews class allows us to inflate a
        // layout resource file hierarchy and provides some
        // basic operations for modifying the content of the
        // inflated hierarchy
        RemoteViews remoteViews = new RemoteViews(this.getPackageName(), R.layout.new_app_widget);

        // by using ComponentName class we can get specific
        // application component and to identify the
        // component we pass the package name and the class
        // name inside of that package
        ComponentName thisWidget = new ComponentName(this, AppWidget.class);

        // update the text of the textview of the widget
        remoteViews.setTextViewText(R.id.appwidget_text, mEditText.getText().toString());

        // finally us the AppWidgetManager instance to
        // update all the widgets
        appWidgetManager.updateAppWidget(thisWidget, remoteViews);
    }

    // this function saves 
    // the current status 
    // of the EditText
    public void saveButton(android.view.View v) {
        // update the content of file stored in the memory
        note.setStick(mEditText.getText().toString(), this);
        updateWidget();
        Toast.makeText(this, "Updated Successfully!!", Toast.LENGTH_SHORT).show();
    }
}
```

****第七步:我们小工具的布局文件****

**由于我们只希望我们的小部件保存文本，我们只需在布局资源文件中添加[文本视图](https://www.geeksforgeeks.org/textview-widget-in-android-using-java-with-examples/)，该文件将不时更新。**

## **可扩展标记语言**

```
<FrameLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/widgetLayout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#FDD835"
    android:orientation="horizontal"
    android:padding="8dp">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="vertical">

        <TextView
            android:id="@+id/appwidget_text"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Text"
            android:textColor="#ffffff"
            android:textSize="20sp"
            tools:layout_editor_absoluteX="1dp"
            tools:layout_editor_absoluteY="1dp" />

    </LinearLayout>

</FrameLayout>
```

****输出:****

**<video class="wp-video-shortcode" id="video-590620-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210406135019/gfgsticky.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210406135019/gfgsticky.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210406135019/gfgsticky.mp4)</video>**

****Github 项目链接****

**所有可绘制的资源文件请参考以下 GitHub 扭结:[https://github.com/raghavtilak/StickyNotes](https://github.com/raghavtilak/StickyNotes)**

### **未来范围**

1.  **您可以添加功能来更改小部件的外观，如文本样式、背景颜色、透明度、宽度等。**
2.  **可以对 UI 做一些改进。**
3.  **您可以通过将数据保存到数据库并获取相同的数据来创建多个便笺。**
4.  **此外，您可以尝试向小部件添加一些不同的视图。**