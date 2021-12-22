# 如何在安卓系统中与其他应用分享你的应用的图片？

> 原文:[https://www . geeksforgeeks . org/如何与另一个安卓应用程序共享您的应用程序图像/](https://www.geeksforgeeks.org/how-to-share-image-of-your-app-with-another-app-in-android/)

大多数情况下，在使用一个应用程序时，我们希望将应用程序中的图像共享给另一个应用程序。在使用许多社交媒体平台时，当我们想要在一个应用程序和另一个应用程序之间共享信息时，我们发现这个功能非常有用。安卓[意图](https://www.geeksforgeeks.org/what-is-intent-in-android/)解析器作为定义明确的任务流的一部分，在向另一个应用程序发送数据时使用。要使用安卓意图解析器，创建一个意图并添加额外内容。在这里，我们将了解如何做到这一点。

> **注:**如果你想在安卓中与另一个 App 共享  你的 App 的文本，那么请参考 [这个](https://www.geeksforgeeks.org/how-to-share-text-of-your-app-with-another-app-in-android/) 。

### **分步实施**

**第一步:创建新项目**

在安卓工作室创建新项目请参考 [<u>【如何在安卓工作室创建/启动新项目】</u>](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/) 。注意选择 **Java** 作为编程语言。

**步骤 2:使用 AndroidManifest.xml 文件**

将以下权限添加到 **AndroidManifest.xml** 文件

> <中使用-权限安卓:name = " AnDroid . permission . read _ EXTERNAL _ STORAGE "/>
> 
> <使用-权限安卓:name = " AnDroid . permission . write _ EXTERNAL _ STORAGE "/>

在 **<应用>** 标签内和**</activity>**标签后添加以下行。

## XML

```
<provider
  android:name="androidx.core.content.FileProvider"

  <!-- Write down your package name -->
  android:authorities="com.anni.shareimage.fileprovider"

  android:exported="false"
  android:grantUriPermissions="true">
    <!-- we intend to request content
          URIs for the images/subdirectory
          of your private file area -->
    <meta-data
      android:name="android.support.FILE_PROVIDER_PATHS"
      android:resource="@xml/paths" />
</provider>
```

以下是 **AndroidManifest.xml** 文件

## XML

的完整代码

```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.anni.shareimage">

    <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
        <activity android:name=".ViewPdfActivity"></activity>
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>

        <provider
            android:name="androidx.core.content.FileProvider"
            android:authorities="com.anni.shareimage.fileprovider"
            android:exported="false"
            android:grantUriPermissions="true">
            <meta-data
                android:name="android.support.FILE_PROVIDER_PATHS"
                android:resource="@xml/paths" />
        </provider>
    </application>

</manifest>
```