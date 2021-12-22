# 如何使用单选按钮在安卓中切换主题？

> 原文:[https://www . geesforgeks . org/如何在 android 中切换主题-使用-radio button/](https://www.geeksforgeeks.org/how-to-switch-themes-in-android-using-radiobuttons/)

我们已经看到安卓应用有两种不同类型的模式或主题，分别是黑暗模式或光明模式，或者我们也称之为夜晚和早晨模式。在本文中，我们将使用 [RadioButton](https://www.geeksforgeeks.org/android-how-to-add-radio-buttons-in-an-android-application/) 在 android 中实现明暗模式。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将显示简单的文本和单选按钮，我们将使用简单的单选按钮将我们的主题从亮切换到暗。下面给出一个视频样本，了解一下在本文中我们要做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-576444-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210319120811/20210319_120558.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210319120811/20210319_120558.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210319120811/20210319_120558.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <!--text view for displaying simple heading-->
    <TextView
        android:id="@+id/idTVHeading"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="40dp"
        android:gravity="center_horizontal"
        android:text="Welcome to Geeks for Geeks"
        android:textAlignment="center"
        android:textSize="20sp" />

    <!--text view for displaying the selected theme-->
    <TextView
        android:id="@+id/idtvTheme"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idTVHeading"
        android:layout_marginTop="30dp"
        android:gravity="center_horizontal"
        android:text="System Default Theme"
        android:textAlignment="center"
        android:textSize="20sp" />

    <!--radio group for switching theme-->
    <RadioGroup
        android:id="@+id/idRGgroup"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idtvTheme"
        android:layout_marginTop="30dp"
        android:orientation="vertical"
        android:padding="4dp">

        <!--radio button for light theme-->
        <RadioButton
            android:id="@+id/idRBLight"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="center_horizontal"
            android:layout_margin="5dp"
            android:padding="5dp"
            android:text="Light" />

        <!--radio button for dark theme-->
        <RadioButton
            android:id="@+id/idRBDark"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="center_horizontal"
            android:layout_margin="5dp"
            android:layout_weight="1"
            android:padding="5dp"
            android:text="Dark" />

    </RadioGroup>

</RelativeLayout>
```

**步骤 3:使用 colors.xml 文件**

导航至**应用程序>RES>values>colors . XML**并添加以下代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="purple_200">#0F9D58</color>
    <color name="purple_500">#0F9D58</color>
    <color name="purple_700">#0F9D58</color>
    <color name="teal_200">#0F9D58</color>
    <color name="teal_700">#FF018786</color>
    <color name="black">#FF000000</color>
    <color name="white">#FFFFFFFF</color>
</resources>
```

**第 4 步:使用主题. xml 进行光照模式**

导航到**应用程序>RES>values>themes>themes . XML**获取灯光模式，并添加以下代码。

## 可扩展标记语言

```
<resources xmlns:tools="http://schemas.android.com/tools">
    <!-- Base application theme. -->
    <style name="Theme.Your Package Name" parent="Theme.MaterialComponents.DayNight.DarkActionBar">
        <!-- Primary brand color. -->
        <item name="colorPrimary">@color/purple_500</item>
        <item name="colorPrimaryVariant">@color/purple_700</item>
        <item name="colorOnPrimary">@color/white</item>
        <!-- Secondary brand color. -->
        <item name="colorSecondary">@color/teal_200</item>
        <item name="colorSecondaryVariant">@color/teal_700</item>
        <item name="colorOnSecondary">@color/black</item>
        <!--below is the text color-->
        <item name="android:textColor">@color/black</item>
        <!-- Status bar color. -->
        <item name="android:statusBarColor" tools:targetApi="l">?attr/colorPrimaryVariant</item>
        <!-- Customize your theme here. -->
    </style>
</resources>
```

**第五步:使用 themes.xml(night)进行黑暗模式。**

导航到**应用程序>RES>values>themes>themes . XML(夜间)**进入黑暗模式，并添加以下代码。

## 可扩展标记语言

```
<resources xmlns:tools="http://schemas.android.com/tools">
    <!-- Base application theme. -->
    <style name="Theme.Your Package Name" parent="Theme.MaterialComponents.DayNight.DarkActionBar">
        <!-- Primary brand color. -->
        <item name="colorPrimary">@color/purple_200</item>
        <item name="colorPrimaryVariant">@color/purple_700</item>
        <item name="colorOnPrimary">@color/white</item>
        <!-- Secondary brand color. -->
        <item name="colorSecondary">@color/teal_200</item>
        <item name="colorSecondaryVariant">@color/teal_200</item>
        <item name="colorOnSecondary">@color/white</item>
        <!--text color-->
        <item name="android:textColor">@color/white</item>
        <!-- Status bar color. -->
        <item name="android:statusBarColor" tools:targetApi="l">?attr/colorPrimaryVariant</item>
        <!-- Customize your theme here. -->
    </style>
</resources>
```

**第 6 步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.os.Bundle;
import android.widget.RadioGroup;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;
import androidx.appcompat.app.AppCompatDelegate;

public class MainActivity extends AppCompatActivity {
    // initializing variables for
    // our radio group and text view.
    private RadioGroup radioGroup;
    private TextView themeTV;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initializing all our variables.
        radioGroup = findViewById(R.id.idRGgroup);
        themeTV = findViewById(R.id.idtvTheme);

        // on below line we are setting on check change method for our radio group.
        radioGroup.setOnCheckedChangeListener(new RadioGroup.OnCheckedChangeListener() {
            @Override
            public void onCheckedChanged(RadioGroup group, int checkedId) {
                // on radio button check change
                switch (checkedId) {
                    case R.id.idRBLight:
                        // on below line we are checking the radio button with id.
                        // on below line we are setting the text to text view as light mode.
                        themeTV.setText("Light Theme");
                        // on below line we are changing the theme to light mode.
                        AppCompatDelegate.setDefaultNightMode(AppCompatDelegate.MODE_NIGHT_NO);
                        break;
                    case R.id.idRBDark:
                        // this method is called when dark radio button is selected
                        // on below line we are setting dark theme text to our text view.
                        themeTV.setText("Dark Theme");
                        // on below line we are changing the theme to dark mode.
                        AppCompatDelegate.setDefaultNightMode(AppCompatDelegate.MODE_NIGHT_YES);
                        break;
                }
            }
        });
    }
}
```

现在运行您的应用程序，并查看应用程序的输出。

**输出:**

<video class="wp-video-shortcode" id="video-576444-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210319120811/20210319_120558.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210319120811/20210319_120558.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210319120811/20210319_120558.mp4)</video>