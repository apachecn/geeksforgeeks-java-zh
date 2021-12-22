# 在安卓使用木材库更好的伐木

> 原文:[https://www . geesforgeks . org/better-logging-using-timber-library-in-Android/](https://www.geeksforgeeks.org/better-logging-using-timber-library-in-android/)

在本文中，我们将在安卓中构建一个应用程序来实现一个比安卓的默认日志类更好的日志实用程序类。为此，我们将使用木材库，这是一个具有可扩展应用编程接口的小型记录器。作为安卓开发人员，我们在项目中使用大量日志语句来生成输出，以在不同阶段测试我们的应用程序。日志有许多类型，如详细、调试、警告、信息、错误。我们在应用程序中使用各种日志语句来查找错误和调试。一旦应用程序准备发布，我们需要删除所有的日志语句，这样生成的 APK 就不会携带任何额外的应用程序数据。要解决这个问题，我们有几种方法:

*   **基于条件的测井**
*   **progresp**
*   **木材**

### 基于条件的**记录**

使用这种方法，我们检查启用记录器的级别，然后将消息记录到该级别。我们只需要在我们的应用程序类中创建一个布尔变量来检查日志记录。在应用程序中的每个日志语句之前和释放应用程序之前，使用此布尔条件，将其更改为 isDebug = false。下面是应用程序类的代码片段。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.app.Application;

public class LogApplication extends Application {

    public static boolean checkDebug;
    @Override
    public void onCreate() {
        super.onCreate();
        checkDebug = true;
    }
}
```

## 我的锅

```
import android.os.Bundle
import androidx.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {

    var checkDebug = false
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        checkDebug = true
    }
}
```

### **progresp**

ProGuard 用于清除未使用的代码。在这里，我们可以使用它来删除发布版本中的日志语句。在 proguard-android-optimize.txt 中添加您想要在发布版本中删除的日志方法。从 Gradle Scripts 中打开此文件，并添加发布时需要删除的所有日志语句。下面是代码片段

> -assume sideffects 类 android.util.Log {
> 
> 公共静态布尔 isLoggable(java.lang.String，int)；
> 
> 公共静态 int d(…)；
> 
> 公共静态 int w(…)；
> 
> 公共静态 int v(…)；
> 
> 公共静态 int I(…)；
> 
> }

### **木材**

这就是木材记录库的用武之地，它通过自动生成标记并在以后从生成的 apk 中删除日志来减少繁琐的任务。让我们讨论一下将木材集成到我们的安卓项目中。

**分步实施**

**第一步:添加依赖关系**

木材是由杰克·沃顿制作的开源图书馆。要添加其依赖项，请打开 **build.gradle** 文件并添加–

> **实施‘com . jakewharton . timber:timber:4 . 7 . 1’**

和同步项目。

**第二步:制作应用类**

我们需要为应用程序创建一个单独的基类，这样木材库就可以在所有活动中使用。要在应用程序启动时初始化木材，最好将其保存在应用程序类中。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.app.Application;
import timber.log.Timber;

public class MyTimber extends Application {
    @Override
    public void onCreate() {
        super.onCreate();

        // initialize timber in application class
        Timber.plant(new Timber.DebugTree());
    }
}
```

## 我的锅

```
import android.os.Bundle
import androidx.appcompat.app.AppCompatActivity
import timber.log.Timber
import timber.log.Timber.DebugTree

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        // initialize timber in application class
        Timber.plant(DebugTree())
    }
}
```

创建应用程序类后，更改**和**文件中的默认应用程序类

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    <application
        android:name=".MyTimber"
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.TimberLogger">
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>
```

**第三步:使用木材伐木**

现在我们可以使用木材来登录我们所有的安卓活动。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import timber.log.Timber;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        Timber.i("Timber logging is ready");
    }
}
```

## 我的锅

```
import android.os.Bundle
import androidx.appcompat.app.AppCompatActivity
import timber.log.Timber

class MainActivity : AppCompatActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)

        Timber.i("Timber logging is ready");
    }
}
```