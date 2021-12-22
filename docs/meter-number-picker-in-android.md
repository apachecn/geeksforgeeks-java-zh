# 安卓系统中的仪表号选择器

> 原文:[https://www . geesforgeks . org/meter-number-picker-in-Android/](https://www.geeksforgeeks.org/meter-number-picker-in-android/)

血糖仪选择器是安卓应用中最常用的追踪血糖仪的功能之一。你可以在距离追踪应用中看到这个功能。有了这个帮助，你就可以追踪自己走了多远。在本文中，我们将学习如何在 android 应用程序中实现一个抄表器。下面给出了一个 GIF 示例，来了解一下在本文中要做什么。请注意，我们将使用 **Java** 语言来实现这个项目。

![Meter Number Picker in Android](img/458f0bae189f046faf1381a5164e686c.png)

### 仪表**号**拾取器的应用

*   这个测速器是一些用来追踪你旅行了多少的游戏。
*   在大多数送餐应用程序中，这个计量器用来跟踪送餐员的行程。

### **仪表编号选择器的属性**

<figure class="table">

| 

属性

 | 

描述

 |
| --- | --- |
| **mnp_textSize** | 用于表示数字的文本大小 |
| **mnp_min** | 表示小部件的最小值 |
| **mnp_max** | 表示小部件的最大值 |
| **mnp_textColor** | 表示数字的文本颜色 |
| **MNP _ 字样** | 代表数字字体 |
| **mnp_minHeight** | 表示小部件的最小高度 |
| **mnp_minWidth** | 表示小部件的最小宽度 |
| **MNP _ padding 垂直** | 用于给小部件提供从顶部和底部的填充 |
| **mnp_paddingHorizontal** | 用于从右向左给小部件填充 |

</figure>

**第一步:创建新项目**

在安卓工作室创建新项目请参考 [如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/) 。注意选择 **Java** 作为编程语言。

**第二步:在 build.gradle 文件**中添加电表编号选择器库的依赖关系

首先导航到渐变脚本，然后导航到**构建.渐变**(项目)级别。在 allprojects{}部分添加下面给出的行。

> mavenuentral _)

然后导航到分级脚本，然后导航到构建.分级(模块)级别。在依赖项部分的 **build.gradle** 文件中添加以下行。

> 实现' com . Alex-zait sev:meter number picker:1 . 0 . 5 '

现在点击**立即同步**它将同步你在 **build.gradle()中的所有文件。**

**第三步:在 themes.xml 文件**中添加样式代码

首先导航到 **res** 文件夹，然后转到 **values** 文件夹，然后导航到 **themes.xml 文件**，并在 **<资源>** 标签中添加以下代码。

## 可扩展标记语言

```
<!--style created for meter picker--> 
<style name="MeterNumberPickerStyle">
  <item name="mnp_min">0</item>
  <item name="mnp_max">9</item>
  <item name="mnp_textColor">@android:color/white</item>
  <item name="mnp_textSize">50sp</item>
  <item name="mnp_paddingHorizontal">5dp</item>
  <item name="mnp_paddingVertical">25dp</item>
</style>

<!--style given for first 5 elements is black
    And for last element is red-->
<style name="MeterViewStyle">
  <item name="mv_firstColor">@android:color/black</item>
  <item name="mv_numberOfFirst">5</item>
  <item name="mv_numberOfSecond">1</item>
  <item name="mv_pickerStyle">@style/MeterNumberPickerStyle</item>
  <item name="mv_secondColor">@android:color/holo_red_dark</item>
</style>
```

**第四步:在你的 activity_main.xml 文件**中创建新的 ShadowImageView

转到**activity _ main . XML**文件，参考以下代码。下面是**activity _ main . XML**文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <com.alexzaitsev.meternumberpicker.MeterView
        android:id="@+id/meterView"
        style="@style/MeterViewStyle"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true" />

    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/meterView"
        android:layout_centerInParent="true"
        android:layout_marginTop="70dp"
        android:text="Get"
        android:textColor="@color/white"
        android:textSize="20dp"
        android:textStyle="bold" />

</RelativeLayout>
```

**步骤 5:使用 MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

import com.alexzaitsev.meternumberpicker.MeterView;

public class MainActivity extends AppCompatActivity {

    // variable to pick number
    MeterView meterNumberPicker;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // number picker called using meter picker id
        meterNumberPicker = findViewById(R.id.meterView);

        // button called using button id
        Button button = (Button) findViewById(R.id.button);
        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                int number = meterNumberPicker.getValue();

                // Toast value to display the number
                Toast.makeText(MainActivity.this, "" + number, Toast.LENGTH_SHORT).show();
            }
        });
    }
}
```

### 输出:

<video class="wp-video-shortcode" id="video-536203-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201229153804/Screenrecorder-2020-12-29-15-33-20-776.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201229153804/Screenrecorder-2020-12-29-15-33-20-776.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201229153804/Screenrecorder-2020-12-29-15-33-20-776.mp4)</video>