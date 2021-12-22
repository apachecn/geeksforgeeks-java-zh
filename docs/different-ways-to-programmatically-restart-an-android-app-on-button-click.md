# 通过按钮点击以编程方式重启安卓应用的不同方式

> 原文:[https://www . geeksforgeeks . org/不同方式-以编程方式-重启一个安卓应用-点击按钮/](https://www.geeksforgeeks.org/different-ways-to-programmatically-restart-an-android-app-on-button-click/)

有时我们想刷新一个活动，但在那里不可能刷新。在那个地方，如果我们重启我们的应用程序，它会自动刷新。此外，每当我们的应用程序崩溃时，我们都可以用它来重启。大多数时候，当我们打开任何应用程序时，它都会获取当前可用的所有数据。但是，如果同时有更多的数据更新到数据库中，那么我们可以使用这个特性来重新启动，以便在每次获得新数据时再次获取所有数据。

接下来的重点是我们如何通过程序重启安卓应用程序点击按钮。因此，在本文中，我们将讨论 **三种** 不同的方法来通过按钮点击以编程方式重启安卓应用程序。

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
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Click on Button to restart the app"
        android:textStyle="bold" />

    <Button
        android:id="@+id/click"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="10dp"
        android:background="@color/black"
        android:padding="10dp"
        android:text="Click to Restart" />

</LinearLayout>
```

### 方法 1

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    Button click;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        click = findViewById(R.id.click);
        click.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                // after on CLick we are using finish to close and then just after that
                // we are calling startactivity(getIntent()) to open our application
                finish();
                startActivity(getIntent());

                // this basically provides animation
                overridePendingTransition(0, 0);
                String time = System.currentTimeMillis() + "";

                // Showing a toast message at the time when we are capturing screenshot
                Toast.makeText(MainActivity.this, "Current time in millisecond after app restart" + time, Toast.LENGTH_SHORT).show();
            }
        });
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-564830-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210226134950/screesnshot1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210226134950/screesnshot1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210226134950/screesnshot1.mp4)</video>

### **方法二**

将此实现添加到您的[构建中。渐变](https://www.geeksforgeeks.org/android-build-gradle/)文件

> 实现' com . jakewharton:process-phoenix:2 . 0 . 0 '

将此默认值添加到 **Androidmanifest.xml** 文件中

```java
<activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.DEFAULT" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
</activity>
```

将以下代码添加到**MainActivity.java**文件中

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

import androidx.appcompat.app.AppCompatActivity;

import com.jakewharton.processphoenix.ProcessPhoenix;

public class MainActivity extends AppCompatActivity {

    Button click;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        setContentView(R.layout.activity_main);
        click = findViewById(R.id.click);

        click.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // this process phoenix library is used 
                // in case to restart our application
                ProcessPhoenix.triggerRebirth(getApplicationContext());
            }
        });
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-564830-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210226135127/screesnhot2.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210226135127/screesnhot2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210226135127/screesnhot2.mp4)</video>

### **方法 3**

将以下代码添加到**MainActivity.java**文件中

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    Button click;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        click = findViewById(R.id.click);
        click.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // Navigating From MainActivity to MainActivity.
                // Navigate from this activity to the activity 
                // specified by upIntent,
                // basically finishing this activity in the process.
                navigateUpTo(new Intent(MainActivity.this, MainActivity.class));
                startActivity(getIntent());
            }
        });
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-564830-3" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210226134807/screenshot.mp4?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/20210226134807/screenshot.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210226134807/screenshot.mp4)</video>