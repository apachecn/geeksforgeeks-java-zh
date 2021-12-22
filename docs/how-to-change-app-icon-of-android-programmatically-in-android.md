# 如何在安卓中通过编程改变安卓的 App 图标？

> 原文:[https://www . geesforgeks . org/how-to-change-app-icon-of-Android-programming-in-Android/](https://www.geeksforgeeks.org/how-to-change-app-icon-of-android-programmatically-in-android/)

在本文中，我们将学习如何在按钮点击时更改应用程序的应用程序图标。当我们有一个针对不同类型用户的应用程序时，可以使用这个功能。然后根据用户类型，我们可以动态改变应用图标。

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在 AndroidManifest.xml 文件**中添加这个

## 可扩展标记语言

```
<?xml version="1.0" encoding="UTF-8"?>

<manifest package="com.prepare.packagename" 
          xmlns:android="http://schemas.android.com/apk/res/android">

<application 
  android:theme="@style/Theme.packagename"
  android:supportsRtl="true" 
  android:roundIcon="@mipmap/ic_launcher_round"
  android:label="@string/app_name" 
  android:icon="@mipmap/ic_launcher_old"
  android:allowBackup="true">

<activity android:name=".MainActivity">

    <intent-filter>

        <action android:name="android.intent.action.MAIN"/>
        <category android:name="android.intent.category.LAUNCHER"/>

    </intent-filter>

</activity>

<activity-alias 
  android:name=".MainActivityAlias" 
  android:roundIcon="@drawable/ic_launcher_p_foreground"
  android:label="@string/app_name"
  android:icon="@mipmap/ic_launcher"
  android:enabled="false" 
  android:targetActivity=".MainActivity">

    <intent-filter>

        <action android:name="android.intent.action.MAIN"/>
        <category android:name="android.intent.category.LAUNCHER"/>

    </intent-filter>

        </activity-alias>
    </application>
</manifest>
```

**步骤 3:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:layout_gravity="center"
    android:gravity="center"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/newicon"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text=" New Icon"
        android:textColor="@color/black"
        android:textSize="20sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/oldicon"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text=" Old Icon"
        android:textColor="@color/black"
        android:textSize="20sp"
        android:layout_marginTop="40dp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</LinearLayout>
```

**步骤 4:** **处理 MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.ComponentName;
import android.content.pm.PackageManager;
import android.graphics.Color;
import android.os.Bundle;
import android.text.SpannableString;
import android.text.Spanned;
import android.text.method.LinkMovementMethod;
import android.text.style.BackgroundColorSpan;
import android.text.style.ClickableSpan;
import android.text.style.ForegroundColorSpan;
import android.view.View;
import android.widget.TextView;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    TextView click,newicon;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        click=findViewById(R.id.oldicon);
        newicon=findViewById(R.id.newicon);
        click.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                changeicon();
            }
        });
        newicon.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                newicon();
            }
        });

    }
    private void changeicon() {

          // enable old icon
        PackageManager manager=getPackageManager();
        manager.setComponentEnabledSetting(new ComponentName(MainActivity.this,"com.prepare.makedirectory.MainActivity")
                ,PackageManager.COMPONENT_ENABLED_STATE_ENABLED,PackageManager.DONT_KILL_APP);

          // disable new icon
        manager.setComponentEnabledSetting(new ComponentName(MainActivity.this,"com.prepare.makedirectory.MainActivityAlias")
                ,PackageManager.COMPONENT_ENABLED_STATE_DISABLED,PackageManager.DONT_KILL_APP);
        Toast.makeText(MainActivity.this,"Enable Old Icon" ,Toast.LENGTH_LONG).show();
    }

    private void newicon() {

          // enable old icon
        PackageManager manager=getPackageManager();
        manager.setComponentEnabledSetting(new ComponentName(MainActivity.this,"com.prepare.makedirectory.MainActivity")
                ,PackageManager.COMPONENT_ENABLED_STATE_DISABLED,PackageManager.DONT_KILL_APP);

          // enable new icon
        manager.setComponentEnabledSetting(new ComponentName(MainActivity.this,"com.prepare.makedirectory.MainActivityAlias")
                ,PackageManager.COMPONENT_ENABLED_STATE_ENABLED,PackageManager.DONT_KILL_APP);
        Toast.makeText(MainActivity.this,"Enable New Icon" ,Toast.LENGTH_LONG).show();
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-630158-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210612090302/icon.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210612090302/icon.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210612090302/icon.mp4)</video>