# 如何用 Jitsi Meet SDK 搭建视频通话安卓 App？

> 原文:[https://www . geesforgeks . org/how-build-a-video-call-Android-app-with-jitsi-meet-SDK/](https://www.geeksforgeeks.org/how-to-build-a-video-calling-android-app-with-jitsi-meet-sdk/)

**视频通话**成为许多社交媒体应用中要求最高的功能，如 **WhatsApp、Instagram、脸书**等。不仅如此，还有一些其他应用程序仅提供这一功能来连接世界各地的人，如**二人组**。因此，这给了我们一个关于视频通话重要性的想法。所以在本文中，我们将使用 [Jitsi](https://en.wikipedia.org/wiki/Jitsi) 开发我们自己的视频通话应用程序。现在，在不浪费更多时间的情况下，让我们看看这个**视频通话应用在安卓系统中的实现。**

### 我们将在本文中构建什么？

在本文中，我们将开发一个示例应用程序，在其主活动中包含一个[编辑文本](https://www.geeksforgeeks.org/edittext-widget-in-android-using-java-with-examples/)和一个[按钮](https://www.geeksforgeeks.org/handling-click-events-button-android/)。使用编辑文本，我们将为我们的视频通话命名一个房间，然后，通过单击按钮，我们将加入该房间，一个新的活动将以我们创建的房间的名称打开，最后，通过使用该活动，我们将进行视频通话。下面给出了一个视频示例，以了解我们在本文中要做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-548263-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210126163141/gfg_output.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210126163141/gfg_output.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210126163141/gfg_output.mp4)</video>

### 用 Jitsi Meet SDK 逐步实现视频通话应用

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。选择最小 SDK **21 或更高的**。

**第二步:添加 jitsi maven 资源库**

现在，转到根 **build.gradle(Project)** 并在 allprojects{ }部分中的 **jcenter()** 下面的存储库末尾添加这些行。

> *所有项目{*
> 
> *存储库{*
> 
> *……*
> 
> *maven { URL " https://github . com/jitsi/jitsi-maven-repository/raw/master/releases " }*
> 
> **}**
> 
> **}**

***第三步:添加依赖关系***

*现在，导航到**渐变脚本>构建.渐变(模块:应用)**在依赖项部分添加下面的依赖项。*

> *实现(' org . jitsi . react:jitsi-meet-SDK:2 . 9 . 0 '){ transitive = true }*

***第 4 步:在 build.gradle(Module:app)中添加 java 1.8 兼容性支持***

*现在，要将 java 1.8 兼容性支持添加到项目中，请将下面这些行粘贴到 android { }标记中的 buildTypes {}下方(如果还没有的话)。*

> *编译{*
> 
> *source compatibility JavaRough。版本 1_8*
> 
> *target compatibility JavaRough。版本 1_8*
> 
> *}*

***第五步:添加程序规则***

*现在，我们将添加一些 proguard 规则，所以转到**Gradle Scripts>proguard-rules . pro**并粘贴以下行。*

> ***参考:**[https://github . com/jitsi/jitsi-meet/blob/master/Android/app/proguard-rules . pro](https://github.com/jitsi/jitsi-meet/blob/master/android/app/proguard-rules.pro)*

```java
*# Add project specific ProGuard rules here.
# By default, the flags in this file are appended to flags specified
# in /usr/local/Cellar/android-sdk/24.3.3/tools/proguard/proguard-android.txt
# You can edit the include path and order by changing the proguardFiles
# directive in build.gradle.
#
# For more details, see
#   http://developer.android.com/guide/developing/tools/proguard.html

# Add any project specific keep options here:

# React Native

# Keep our interfaces so they can be used by other ProGuard rules.
# See http://sourceforge.net/p/proguard/bugs/466/
-keep,allowobfuscation @interface com.facebook.proguard.annotations.DoNotStrip
-keep,allowobfuscation @interface com.facebook.proguard.annotations.KeepGettersAndSetters
-keep,allowobfuscation @interface com.facebook.common.internal.DoNotStrip

# Do not strip any method/class that is annotated with @DoNotStrip
-keep @com.facebook.proguard.annotations.DoNotStrip class *
-keep @com.facebook.common.internal.DoNotStrip class *
-keepclassmembers class * {
    @com.facebook.proguard.annotations.DoNotStrip *;
    @com.facebook.common.internal.DoNotStrip *;
}

-keepclassmembers @com.facebook.proguard.annotations.KeepGettersAndSetters class * {
  void set*(***);
  *** get*();
}

-keep class * extends com.facebook.react.bridge.JavaScriptModule { *; }
-keep class * extends com.facebook.react.bridge.NativeModule { *; }
-keepclassmembers,includedescriptorclasses class * { native <methods>; }
-keepclassmembers class *  { @com.facebook.react.uimanager.UIProp <fields>; }
-keepclassmembers class *  { @com.facebook.react.uimanager.annotations.ReactProp <methods>; }
-keepclassmembers class *  { @com.facebook.react.uimanager.annotations.ReactPropGroup <methods>; }

-dontwarn com.facebook.react.**
-keep,includedescriptorclasses class com.facebook.react.bridge.** { *; }

# okhttp

-keepattributes Signature
-keepattributes *Annotation*
-keep class okhttp3.** { *; }
-keep interface okhttp3.** { *; }
-dontwarn okhttp3.**

# okio

-keep class sun.misc.Unsafe { *; }
-dontwarn java.nio.file.*
-dontwarn org.codehaus.mojo.animal_sniffer.IgnoreJRERequirement
-keep class okio.** { *; }
-dontwarn okio.**

# WebRTC

-keep class org.webrtc.** { *; }
-dontwarn org.chromium.build.BuildHooksAndroid

# Jisti Meet SDK

-keep class org.jitsi.meet.** { *; }
-keep class org.jitsi.meet.sdk.** { *; }

# We added the following when we switched minifyEnabled on. Probably because we
# ran the app and hit problems...

-keep class com.facebook.react.bridge.CatalystInstanceImpl { *; }
-keep class com.facebook.react.bridge.ExecutorToken { *; }
-keep class com.facebook.react.bridge.JavaScriptExecutor { *; }
-keep class com.facebook.react.bridge.ModuleRegistryHolder { *; }
-keep class com.facebook.react.bridge.ReadableType { *; }
-keep class com.facebook.react.bridge.queue.NativeRunnable { *; }
-keep class com.facebook.react.devsupport.** { *; }

-dontwarn com.facebook.react.devsupport.**
-dontwarn com.google.appengine.**
-dontwarn com.squareup.okhttp.**
-dontwarn javax.servlet.**

# ^^^ We added the above when we switched minifyEnabled on.

# Rule to avoid build errors related to SVGs.
-keep public class com.horcrux.svg.** {*;}*
```

*最后，同步您的项目，现在我们拥有了实施过程中所需的一切，现在，开始实施吧。*

***第 6 步:使用 activity_main.xml 文件***

*现在是时候设计应用程序的布局了。为此，转到**应用程序> res >布局> activity_main.xml** 并将下面编写的代码粘贴到 **activity_main.xml** 文件中。*

## *可扩展标记语言*

```java
*<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <!--EditText for taking input room name from user-->
    <EditText
        android:id="@+id/conferenceName"
        android:layout_width="match_parent"
        android:layout_height="52dp"
        android:layout_margin="12dp"
        android:hint="Enter room name" />

    <!--Button for creating a room for video 
        calling by it's clicking event-->
    <!--When clicking event occur on button
        then onButtonClick method will call -->
    <Button
        android:layout_width="match_parent"
        android:layout_height="52dp"
        android:layout_margin="12dp"
        android:background="#0F9D58"
        android:onClick="onButtonClick"
        android:text="Join"
        android:textColor="#FFFFFF" />

</LinearLayout>*
```

***步骤 7:使用 MainActivity.java 文件***

*转到 **app > java >包名>MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。*

## *Java 语言(一种计算机语言，尤用于创建网站)*

```java
*import android.os.Bundle;
import android.view.View;
import android.widget.EditText;

import androidx.appcompat.app.AppCompatActivity;

import org.jitsi.meet.sdk.JitsiMeetActivity;
import org.jitsi.meet.sdk.JitsiMeetConferenceOptions;

import java.net.MalformedURLException;
import java.net.URL;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // using try catch block to handle exceptions
        try {
            // object creation of JitsiMeetConferenceOptions
            // class by the name of options
            JitsiMeetConferenceOptions options = new JitsiMeetConferenceOptions.Builder()
                    .setServerURL(new URL(""))
                    .setWelcomePageEnabled(false)
                    .build();
        } catch (MalformedURLException e) {
            e.printStackTrace();
        }
    }

    // we have declared the name of onButtonClick() method 
    // in our xml file  now we are going to define it.
    public void onButtonClick(View v) {
        // initialize editText with method findViewById()
        // here editText will hold the name of room which is given by user
        EditText editText = findViewById(R.id.conferenceName);

        // store the string input by user in editText in 
        // an local variable named text of string type
        String text = editText.getText().toString();

        // if user has typed some text in 
        // EditText then only room will create 
        if (text.length() > 0) {
            // creating a room using  JitsiMeetConferenceOptions class 
            // here .setRoom() method will set the text in room name
            // here launch method with launch a new room to user where
            // they can invite others too.
            JitsiMeetConferenceOptions options
                    = new JitsiMeetConferenceOptions.Builder()
                    .setRoom(text)
                    .build();
            JitsiMeetActivity.launch(this, options);
        }
    }
}*
```

*仅此而已，现在视频通话应用程序已准备好安装在设备上。下面是应用程序的输出。*

### *输出:在物理设备上运行*

*<video class="wp-video-shortcode" id="video-548263-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210126163141/gfg_output.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210126163141/gfg_output.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210126163141/gfg_output.mp4)</video>*

***Github 链接:**要获得更多帮助，请浏览这个[存储库](https://github.com/Blitzcoder01/GFG_VideoCallingApp)。*