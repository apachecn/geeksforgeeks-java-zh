# 如何用示例在安卓中创建一个可访问性服务？

> 原文:[https://www . geeksforgeeks . org/如何通过示例在安卓中创建可访问性服务/](https://www.geeksforgeeks.org/how-to-create-an-accessibility-service-in-android-with-example/)

无障碍服务就像安卓框架提供的魔杖。虽然辅助功能服务的唯一目的是为不同能力的用户提供访问设备的便利，但它也可以用来实现一些功能，帮助任何用户进行日常电话使用。强烈建议您在继续阅读这篇文章之前，先浏览一下安卓中的[辅助功能服务。](https://www.geeksforgeeks.org/what-is-accessibility-service-in-android/)

### 1.创建服务类

首先创建一个常规类，用 AccessibilityService 类扩展该类，并覆盖强制方法。可访问性服务可以在常规项目中使用，也可以作为独立项目开发。

## Java 语言(一种计算机语言，尤用于创建网站)

```
/*package whatever //do not write package name here */
import android.accessibilityservice.AccessibilityService;
import android.view.accessibility.AccessibilityEvent;

public class MyService extends AccessibilityService {
...
    @Override
    public void onAccessibilityEvent(AccessibilityEvent event) {
    }

      @Override
    public void onInterrupt() {

    }
...
}
```

### 2.清单声明和权限

要被安卓框架视为可访问性服务，提供可访问性服务的应用程序必须在其应用程序清单中包含特定的声明。辅助功能服务所需的权限与常规权限不同。像任何其他服务一样，我们需要在应用程序元素下的清单中声明它。为了将该服务与其他常规服务区分开来，我们还必须包含一个可访问性服务意图过滤器。在服务中，我们需要声明权限，以确保只有系统可以绑定到它。服务中的标签属性是用户通过设备设置明确打开服务时出现的文本。这通常是您的应用名称或服务名称。

## 可扩展标记语言

```
<application>
    <service android:name=".MyService"
        android:permission="android.permission.BIND_ACCESSIBILITY_SERVICE"
        android:label="@string/accessibility_service_label">
      <intent-filter>
        <action android:name="android.accessibilityservice.AccessibilityService" />
      </intent-filter>
    </service>
</application>
```

### 3.辅助功能服务配置

配置服务的方法主要有两种。

**步骤 1:** 首先通过创建一个 XML 配置文件，并声明和定义所有需要的属性。右键单击 res 文件夹，创建一个新的 android 资源目录 XML。现在在 XML 文件夹中创建**辅助功能 _ 服务 _ 配置. xml**

## 可扩展标记语言

```
<accessibility-service xmlns:android="http://schemas.android.com/apk/res/android"
    android:description="@string/accessibility_service_description"
    android:packageNames="com.example.android.sampleapp1,com.example.android.sampleapp2"
    android:accessibilityEventTypes="typeAllMask"
    android:accessibilityFlags="flagDefault"
    android:accessibilityFeedbackType="feedbackSpoken"
    android:notificationTimeout="100"
    android:canRetrieveWindowContent="true"
    android:settingsActivity="com.example.android.accessibility.ServiceSettingsActivity"
/>
```

这段代码定义了我们的应用程序可以对哪些类型的事件做出反应，应用程序可以提供哪些类型的输入，以及如果您希望您的应用程序只管理来自特定应用程序的事件，或者在特定时间范围内获取事件、检索窗口内容等，这个应用程序可以监听哪些特定的包。在这种方法中，我们必须通过在清单的服务标签中添加<meta-data>标签来引用 XML 配置文件。</meta-data>

## 可扩展标记语言

```
<service android:name=".MyService">
  ...
  <meta-data
    android:name="android.accessibilityservice"
    android:resource="@xml/accessibility_service_config" />
</service>
```

**第二步:**第二步是在 onServiceConnected 方法中使用 setServiceInfo(AccessibilityServiceInfo)方法动态设置属性。

## Java 语言(一种计算机语言，尤用于创建网站)

```
@Override
public void onServiceConnected() {
    // pass the typeof events you want your service to listen to
      // other will not be handledby this service
    info.eventTypes = AccessibilityEvent.TYPE_VIEW_CLICKED |
            AccessibilityEvent.TYPE_VIEW_FOCUSED;

    // In case you want your service to work only with a particular application
    //or when that application is in foreground, you should specify those applications package
    //names here, otherwise the service would listen events from all the applications
    info.packageNames = new String[]
            {"com.example.android.myFirstApp", "com.example.android.mySecondApp"};

    // Set the type of feedback your service will provide.
    info.feedbackType = AccessibilityServiceInfo.FEEDBACK_SPOKEN;
    // the notification timeout is the time interval after which the service would
      // listen from the system. Anything happening between that interval won't be
      // captured by the service
    info.notificationTimeout = 100;

      // finally set the serviceInfo
    this.setServiceInfo(info);

}
```

现在，既然我们已经成功地实例化了可访问性服务，让我们举个例子来理解它是如何工作的。

### 例子

在这个例子中，让我们创建一个监听设备按键事件的服务，即当用户按下音量向上和向下键时，我们的服务将接收回拨并执行任何特定任务。

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:创建可访问性 _service_config.xml**

创建一个新的布局资源文件，并将文件命名为**accessibility _ service _ config。**下面是**辅助功能文件**的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<accessibility-service xmlns:android="http://schemas.android.com/apk/res/android"
    android:packageNames=""
    android:accessibilityEventTypes="typeAllMask"
    android:accessibilityFlags="flagRequestFilterKeyEvents"
    android:accessibilityFeedbackType="feedbackSpoken"
    android:notificationTimeout="100"
    android:canRetrieveWindowContent="true"
    android:canRequestFilterKeyEvents="true"
    android:settingsActivity="com.example.android.accessibility.ServiceSettingsActivity"
    />
```

**第三步:创建我的服务类**

[在安卓工作室](https://www.geeksforgeeks.org/how-to-create-classes-in-android-studio/)中创建一个 java 类，并将该类命名为**我的服务。**以下是**MyService.java**文件的代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.accessibilityservice.AccessibilityService;
import android.util.Log;
import android.view.KeyEvent;
import android.view.accessibility.AccessibilityEvent;
import android.widget.Toast;

public class MyService extends AccessibilityService {
    @Override
    public void onAccessibilityEvent(AccessibilityEvent accessibilityEvent) {
    }

    @Override
    public void onInterrupt() {

    }

    @Override
    protected boolean onKeyEvent(KeyEvent event) {

        int action = event.getAction();
        int keyCode = event.getKeyCode();
        // the service listens for both pressing and releasing the key
        // so the below code executes twice, i.e. you would encounter two Toasts
        // in order to avoid this, we wrap the code inside an if statement
        // which executes only when the key is released
        if (action == KeyEvent.ACTION_UP) {
            if (keyCode == KeyEvent.KEYCODE_VOLUME_UP) {
                Log.d("Check", "KeyUp");
                Toast.makeText(this, "KeyUp", Toast.LENGTH_SHORT).show();
            } else if (keyCode == KeyEvent.KEYCODE_VOLUME_DOWN) {
                Log.d("Check", "KeyDown");
                Toast.makeText(this, "KeyDown", Toast.LENGTH_SHORT).show();
            }
        }
            return super.onKeyEvent(event);
    }
}
```

**第 4 步:使用 AndroidManifest.xml 文件**

下面是 **AndroidManifest.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.raghav.gfgkeyevent">

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.GFGKeyEvent">
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>

        <service android:name=".MyService"
            android:permission="android.permission.BIND_ACCESSIBILITY_SERVICE"
            android:label="">
            <intent-filter>
                <action android:name="android.accessibilityservice.AccessibilityService" />
            </intent-filter>

            <meta-data
                android:name="android.accessibilityservice"
                android:resource="@xml/accessibility_service_config" />
        </service>

    </application>

</manifest>
```

**步骤 5:使用 MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.provider.Settings;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        if(!checkAccessibilityPermission()){
            Toast.makeText(MainActivity.this, "Permission denied", Toast.LENGTH_SHORT).show();
        }
    }

    // method to check is the user has permitted the accessibility permission
    // if not then prompt user to the system's Settings activity
    public boolean checkAccessibilityPermission () {
        int accessEnabled = 0;
        try {
            accessEnabled = Settings.Secure.getInt(this.getContentResolver(), Settings.Secure.ACCESSIBILITY_ENABLED);
        } catch (Settings.SettingNotFoundException e) {
            e.printStackTrace();
        }
        if (accessEnabled == 0) {
            // if not construct intent to request permission
            Intent intent = new Intent(Settings.ACTION_ACCESSIBILITY_SETTINGS);
            intent.setFlags(Intent.FLAG_ACTIVITY_NEW_TASK);
            // request permission via start activity for result
            startActivity(intent);
            return false;
        } else {
            return true;
        }
    }
}
```