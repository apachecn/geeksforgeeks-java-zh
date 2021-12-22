# 安卓系统如何防止截图或录屏？

> 原文:[https://www . geeksforgeeks . org/如何防止安卓屏幕截图或屏幕记录器/](https://www.geeksforgeeks.org/how-to-prevent-screenshot-or-screen-recorder-in-android/)

在某些情况下，我们不希望允许对我们的安卓应用程序进行截图或屏幕录制。下面我们就来解释一下如何防止安卓在 app 去后台的时候截图或者录屏。通常，当我们截图时，我们会在通知栏中看到一个屏幕截图通知，如果您单击该通知，您可以在图库应用程序中看到该截图。而且有些安卓应用程序我们无法拍摄可视屏幕的截图，因为屏幕是由开发者保护的。在这种情况下，我们会在通知栏或屏幕上方的[吐司](https://www.geeksforgeeks.org/android-what-is-toast-and-how-to-use-it-with-examples/)中看到消息。一些支付转账应用程序或包含课程的应用程序具有此功能。在本文中，我们将创建一个简单的项目来演示这个特性是如何工作的。下面给出了一个 GIF 示例，来了解一下我们将在本文中做什么。注意，我们将使用 **Java** 语言来实现这个项目。

![](img/f3b5aa241e5633bbf3fb97e3483a32f7.png)

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** ，并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。我们将在 **activity_main.xml** 文件中创建一个简单的[文本视图](https://www.geeksforgeeks.org/textview-widget-in-android-using-java-with-examples/)。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Preventing App from Taking Screenshot"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        android:textStyle="bold"
        android:textSize="18sp"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

### 方法 1

在**MainActivity.java**文件中，只需添加以下代码，它将阻止在安卓应用中拍摄截图。

> getWindow()。setFlags(WindowManager)。布局参数. FLAG_SECURE，
> 
> 温杜夫经理。布局参数. FLAG_SECURE：

以下是**MainActivity.java**文件的完整代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.WindowManager;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Adding this line will prevent taking screenshot in your app
        getWindow().setFlags(WindowManager.LayoutParams.FLAG_SECURE,
                             WindowManager.LayoutParams.FLAG_SECURE);

    }
}
```

### 方法 2

**方法 1** 只适用于单个活动，但是对所有活动的区块截图有什么解决方案。我们将在方法 2 中讨论这个问题。首先，制作一个**自定义应用类**，并添加一个**注册活动活动循环回**。然后在你的清单上登记。

**第一步:在这里把给定的代码写入 MyApplicationContext.java 文件**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.app.Activity;
import android.app.Application;
import android.content.Context;
import android.os.Bundle;
import android.view.WindowManager;

public class MyApplicationContext extends Application {
    private Context context;
    public void onCreate() {
        super.onCreate();
        context = getApplicationContext();
        setupActivityListener();
    }

    private void setupActivityListener() {
        registerActivityLifecycleCallbacks(new ActivityLifecycleCallbacks() {
            @Override
            public void onActivityCreated(Activity activity, Bundle savedInstanceState) {
                activity.getWindow().setFlags(WindowManager.LayoutParams.FLAG_SECURE, WindowManager.LayoutParams.FLAG_SECURE);            }
            @Override
            public void onActivityStarted(Activity activity) {
            }
            @Override
            public void onActivityResumed(Activity activity) {

            }
            @Override
            public void onActivityPaused(Activity activity) {

            }
            @Override
            public void onActivityStopped(Activity activity) {
            }
            @Override
            public void onActivitySaveInstanceState(Activity activity, Bundle outState) {
            }
            @Override
            public void onActivityDestroyed(Activity activity) {
            }
        });
    }
}
```

**第二步:像下面这样在清单文件中注册**

```java
<application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:name=".MyApplicationContext"
        android:theme="@style/AppTheme">
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>
```

### **输出:**

在这里你可以清楚地看到，它既不允许截图，也不允许屏幕录制，因为当我们尝试拍摄屏幕录制时，它会变黑。

<video class="wp-video-shortcode" id="video-562281-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210218210539/WhatsApp-Video-2021-02-18-at-9.03.37-PM.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210218210539/WhatsApp-Video-2021-02-18-at-9.03.37-PM.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210218210539/WhatsApp-Video-2021-02-18-at-9.03.37-PM.mp4)</video>