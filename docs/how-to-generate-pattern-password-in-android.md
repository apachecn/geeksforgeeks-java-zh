# 如何在安卓系统中生成模式密码？

> 原文:[https://www . geesforgeks . org/如何生成模式-安卓密码/](https://www.geeksforgeeks.org/how-to-generate-pattern-password-in-android/)

设备的模式密码是保持设备私密和受保护的必要条件之一。如今，在大多数应用程序中，我们可以看到这个密码被应用在许多应用程序中，如共同基金或股票市场应用程序，以保持我们的财务细节隐私。在本文中，我们将看到如何在我们的安卓应用程序中实现模式密码。下面给出了一个 GIF 示例，来了解一下在本文中要做什么。请注意，我们将使用 **Java** 语言来实现这个项目。

![Generate Pattern Password in Android Sample GIF](img/611666f2339f109068704982e0439fe7.png)

### 模式密码的应用

*   用于在安卓应用程序中保护我们的隐私细节和个人信息。
*   使用模式密码代替 pin 变得非常方便。
*   它在我们的设备上作为应用锁定我们的应用。

### **模式密码的属性**

<figure class="table">

| 属性 | 描述 |
| --- | --- |
| **布局 _ 宽度** | 显示点的宽度。 |
| **布局 _ 高度** | 显示点的高度。 |
| **正确状态颜色** | 显示点的颜色。 |

</figure>

### 逐步实施

**第一步:创建新项目**

在安卓工作室创建新项目请参考 [如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/) 。注意选择 **Java** 作为编程语言。

**第二步:在 build.gradle 文件**中添加模式密码库的依赖关系

然后导航到梯度脚本，然后导航到**构建.梯度(模块)**级别。在 dependencies 部分的 build.gradle 文件中添加以下行。

> 实现' com .雄核尼托. patternlockview:patternlockview:1 . 0 . 0 '

现在点击**立即同步**它将同步你在 **build.gradle()中的所有文件。**

**第三步:在你的 activity_main.xml 文件**中创建一个加载屏幕

导航到**应用程序> res >** 布局，打开 **activity_main.xml** 文件。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--Text view for giving loading-->
    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:text="Loading...." />

</RelativeLayout>
```

**步骤 4:使用 MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.Intent;
import android.content.SharedPreferences;
import android.os.Bundle;
import android.os.Handler;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Handler handler = new Handler();
        handler.postDelayed(new Runnable() {
            @Override
            public void run() {
                // loading is given
                SharedPreferences sharedPreferences = getSharedPreferences("PREFS", 0);
                String password = sharedPreferences.getString("password", "0");
                if (password.equals("0")) {
                    // Intent to navigate to Create Password Screen
                    Intent intent = new Intent(getApplicationContext(), CreatePasswordActivity.class);
                    startActivity(intent);
                    finish();
                } else {
                    // Intent to navigate to Input Password Screen
                    Intent intent = new Intent(getApplicationContext(), InputPasswordActivity.class);
                    startActivity(intent);
                    finish();
                }
            }
        }, 2000);
    }
}
```

**步骤 5:创建一个新的空活动，并将其命名为 CreatePasswordActivity**

转到**应用程序> java >您的应用程序的包名>右键单击>新建>活动>清空活动**并将活动命名为**创建密码活动**。

**使用 activity_create_password.xml 文件:**

转到 **活动 _create_password.xml** 文件，参考以下代码。下面是**activity _ create _ password . XML**文件的代码。在该文件中，您将显示点以创建图案密码，如下所示。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <!--Dots to create pattern pass word-->
    <com.andrognito.patternlockview.PatternLockView
        android:id="@+id/pattern_lock_view"
        android:layout_width="300dp"
        android:layout_height="300dp"
        android:layout_centerInParent="true"
        app:correctStateColor="@color/purple_200"
        app:normalStateColor="@color/purple_200"
        app:wrongStateColor="@color/teal_700" />

    <!--Text View to display title-->
    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="10dp"
        android:text="Create Password"
        android:textSize="30dp"
        android:textStyle="bold" />

</RelativeLayout>
```

**处理 CreatePasswordActivity.java 文件:**

转到**CreatePasswordActivity.java**文件，参考以下代码。以下是**CreatePasswordActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.Intent;
import android.content.SharedPreferences;
import android.os.Bundle;

import androidx.appcompat.app.AppCompatActivity;

import com.andrognito.patternlockview.PatternLockView;
import com.andrognito.patternlockview.listener.PatternLockViewListener;
import com.andrognito.patternlockview.utils.PatternLockUtils;

import java.util.List;

public class CreatePasswordActivity extends AppCompatActivity {

    // Initialize pattern lock view
    PatternLockView mPatternLockView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_create_password);

        mPatternLockView = (PatternLockView) findViewById(R.id.pattern_lock_view);
        mPatternLockView.addPatternLockListener(new PatternLockViewListener() {
            @Override
            public void onStarted() {

            }

            @Override
            public void onProgress(List<PatternLockView.Dot> progressPattern) {

            }

            @Override
            public void onComplete(List<PatternLockView.Dot> pattern) {
                // Shared Preferences to save state
                SharedPreferences sharedPreferences = getSharedPreferences("PREFS", 0);
                SharedPreferences.Editor editor = sharedPreferences.edit();
                editor.putString("password", PatternLockUtils.patternToString(mPatternLockView, pattern));
                editor.apply();

                // Intent to navigate to home screen when password added is true
                Intent intent = new Intent(getApplicationContext(), ProgramActivity.class);
                startActivity(intent);
                finish();
            }
            @Override
            public void onCleared() {

            }
        });
    }
}
```