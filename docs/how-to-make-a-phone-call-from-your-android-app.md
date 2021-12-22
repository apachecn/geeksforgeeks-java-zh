# 如何用你的安卓 App 打电话？

> 原文:[https://www . geeksforgeeks . org/如何用你的安卓应用打电话/](https://www.geeksforgeeks.org/how-to-make-a-phone-call-from-your-android-app/)

在本文中，您将制作一个基本的 [android 应用程序](https://www.geeksforgeeks.org/android-app-development-fundamentals-for-beginners/)，它可以用来通过您的 android 应用程序拨打某个号码。

你可以在的帮助下完成，动作为 **ACTION_CALL** 。基本上，Intent 是一个简单的消息对象，用于在安卓组件(如活动、内容提供商、广播接收器和服务)之间进行通信，这里用于打电话。这个应用程序基本上包含一个编辑文本的活动，用于编写您想要拨打的电话号码和拨打该号码的按钮。

*   **第一步。安卓-Manifest.xml 文件**
    中的权限代码您需要从用户那里获得电话呼叫的权限，为此 CALL_PHONE 权限会添加到清单文件中。这里是清单文件的代码:

    ## 安卓-清单

    ```
    <?xml version="1.0" encoding="utf-8"?>  
    <manifest xmlns:androclass="http://schemas.android.com/apk/res/android"  
        package="com.geeksforgeeks.phonecall"  
        android:versionCode="1"  
        android:versionName="1.0" >  
        <uses-sdk  
            android:minSdkVersion="8"  
            android:targetSdkVersion="16" />  
        <!--permission for phone call-->
        <uses-permission android:name="android.permission.CALL_PHONE" />  
        <application  
            android:icon="@drawable/ic_launcher"  
            android:label="@string/gfg"  
            android:theme="@style/AppTheme" >  
            <activity  
                android:name="com.geeksforgeeks.phonecall.MainActivity"  
                android:label="@string/gfg" >  
                <intent-filter>  
                    <action android:name="android.intent.action.MAIN" />  
                    <category android:name="android.intent.category.LAUNCHER" />  
                </intent-filter>  
            </activity>  
        </application>  
    </manifest>  
    ```

*   **第二步。activity _ main . XML**
    activity _ main . XML 包含一个[相对布局](https://www.geeksforgeeks.org/android-ui-layouts/)，该布局包含编辑文本以编写您想要拨打电话的电话号码和用于开始意图或拨打电话的按钮:

    ## activity _ main . XML

```
<?xml version="1.0" encoding="utf-8"?>
<!--Relative Layout-->
<RelativeLayout
    xmlns:androclass="http://schemas.android.com/apk/res/android"  
    xmlns:tools="http://schemas.android.com/tools"  
    android:layout_width="match_parent"  
    android:layout_height="match_parent"  
    tools:context=".MainActivity">
   <!--Edit text for phone number-->
    <EditText  
        android:id="@+id/editText"  
        android:layout_marginTop="30dp" 
        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"  
        android:layout_alignParentTop="true"  
        android:layout_centerHorizontal="true"  
        />  
   <!--Button to make call-->
    <Button  
        android:id="@+id/button"  
        android:layout_marginTop="115dp"
        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"
        android:text="Make Call!!" 
        android:padding="5dp" 
        android:layout_alignParentTop="true"  
        android:layout_centerHorizontal="true"     
         />  
</RelativeLayout>
```