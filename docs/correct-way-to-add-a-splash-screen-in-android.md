# 在安卓中添加闪屏的正确方法

> 原文:[https://www . geesforgeks . org/正确添加安卓闪屏方式/](https://www.geeksforgeeks.org/correct-way-to-add-a-splash-screen-in-android/)

谷歌之前建议不要对安卓应用程序使用闪屏。毫无意义。然后，当他们发布材料设计规范时，我们中的几个人注意到闪屏已经改名为启动屏。非常适合展示您的品牌。那么，一个糟糕的启动屏幕和一个好的启动屏幕有什么区别呢？

所以你无疑是在问，**“创建理想的闪屏能有多难？”**你可能是对的——我们说的是只显示几秒钟的屏幕(如果是这样的话)。还有一个屏幕，似乎在消失前会向用户闪烁一个标志。所以没那么复杂。**不！**

### **分步实施**

**步骤#1:创建背景 XML**

要制作一个合适的闪屏，你必须首先建立一个背景，在屏幕上显示你的品牌标志。您必须为此在 RES/drawing 文件夹中创建一个 XML 文件。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<layer-list xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:drawable="@color/colorAccent" />
    <item>
        <bitmap android:src="@drawable/gfgLogo"
                android:gravity="center" />
    </item>
</layer-list>
```

**步骤 2:为你的启动屏幕创建一个专用的定制主题**

下一步是为你的闪屏活动设计一个独特的主题。

> **极客提示:**主题要继承**主题。因为我们不希望在显示启动时状态栏可见。**

## XML

```java
<resources>
    <style name="AppTheme" parent="Theme.AppCompat.Light.DarkActionBar">
        <item name="colorNative">@color/colorNative</item>
        <item name="colorPrimaryDark">@color/colorPrimaryDark</item>
        <item name="colorAccent">@color/colorAccent</item>
    </style>

    <style name="LaunchTheme" parent="Theme.AppCompat.NoActionBar">
        <item name="android:windowBackground">@drawable/background</item>
    </style>
</resources>
```

**第三步:最后点码烹饪**

现在是有趣的部分，我们以正确的方式控制启动屏幕！这里最好的部分是，与添加闪屏的传统方法不同，不需要为闪屏活动指定内容视图，因为闪屏主题将应用于它。因此，您所要做的就是启动您的安卓应用程序的主活动，然后使用 finish()函数结束 SplashActivity。这里是活动:

## 爪哇

```java
import android.content.Intent;
import android.os.Bundle;
import android.support.annotation.Nullable;
import android.support.v7.app.AppCompatActivity;

public class LaunchScreen extends AppCompatActivity {
    @Override
    protected void onCreate(@Nullable Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        Intent intent = new Intent(this, LandingActivity.class);
        startActivity(intent);
        finish();
    }
}
```

**第四步:最后，设置主题**

现在我们已经做好了一切，现在唯一剩下的事情就是为我们的活动应用我们之前在步骤 2 中创建的主题，这很容易，只需弹出**安卓。清单**文件，按以下方式编辑。

## XML

```java
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.geeksforgeeks.launchcreen">

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:theme="@style/AppTheme">

        <activity android:name=".LaunchScreen" android:theme="@style/LaunchTheme">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
        <activity android:name=".LandingActivity" />
    </application>
</manifest>
```

就像你以正确的方式拥有闪屏一样，这种方法非常好，即使你的应用程序冷启动，也没有白色主题，因为安卓操作系统首先从清单中获取主题，这弥补了闪屏的时间！