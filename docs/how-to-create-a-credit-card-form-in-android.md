# 如何在安卓系统中创建信用卡表单？

> 原文:[https://www . geesforgeks . org/如何创建安卓信用卡表单/](https://www.geeksforgeeks.org/how-to-create-a-credit-card-form-in-android/)

许多应用程序都有一个漂亮的用户界面，可以将你的信用卡添加到应用程序中并保存。这种功能可以在 **CRED 应用程序**中看到，我们可以在该应用程序中保存我们的信用卡。在本文中，我们将简单地创建一个应用程序中的信用卡表单。我们将在我们的应用程序中为信用卡创建一个用户界面。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将显示一张信用卡和一些文本字段，以在这些文本字段中输入数据。输入数据后，我们将看到数据显示在上面显示的卡片中。下面给出了一个示例视频，以了解我们将在本文中做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-593591-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210418122046/Screenrecorder-2021-04-18-12-12-55-58.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210418122046/Screenrecorder-2021-04-18-12-12-55-58.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210418122046/Screenrecorder-2021-04-18-12-12-55-58.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:添加依赖和 JitPack 存储库**

导航到**渐变脚本>构建.渐变(模块:应用)**，并在依赖项部分添加以下依赖项。

> 实现' com . github . fevziomurtekin:PayView:1 . 0 . 3 '

将 JitPack 存储库添加到构建文件中。将其添加到 allprojects{ }部分内存储库末尾的 root build.gradle 中。

> *所有项目{*
> 
> *存储库{*
> 
> *……*
> 
> *maven { URL " https://jitpack . io " }*
> 
> *}*
> 
> *}*

添加这个依赖项后，同步您的项目，现在我们将开始实现它。

### **用于支付视图的重要属性**

<figure class="table">

| 

属性

 | 

描述

 |
| --- | --- |
| 卡片颜色 | 该属性用于为我们的卡片提供背景颜色。 |
| 卡片颜色 | 该属性用于为我们的卡片提供前景色。 |
| 卡片文本颜色 | 该属性用于提供我们卡片中使用的文本颜色。 |
| cardAnimationType | 卡片上有 2 个动画，分别是水平和垂直的。它们在我们添加 cvv 时使用。 |
| 卡片名称文本大小 | 该属性用于指定我们为卡添加的名称的文本大小。 |
| cardNoTextSize | 该属性用于指定我们为卡添加的卡号的文本大小。 |
| cardYearTextSize | 该属性用于指定我们为卡片添加的卡片年份的文本大小。 |
| cardMonthTextSize | 该属性用于指定我们为卡片添加的卡片月份的文本大小。 |
| cardCvTextSize | 该属性用于指定我们为卡片添加的卡片 cvv 的文本大小。 |
| 卡号帮助文本 | 该属性用于提供输入卡号的提示。 |
| cardNameHelperText | 该属性用于提供输入卡名的提示。 |
| cardCvErrorText | 该属性用于提供输入卡 cvv 的提示。 |
| cardMonthErrorText | 该属性用于提供进入卡月的提示。 |
| 卡片年错误文本 | 此属性用于提供输入卡年的提示。 |
| cardExpiredErrorText | 此属性用于在输入的卡年无效时提供提示。 |

</figure>

**步骤 3:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--on below line we are creating a pay view-->
    <com.fevziomurtekin.payview.Payview
        android:id="@+id/payview"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:cardAnimationType="vertical"
        app:cardBgColor="@color/purple_200"
        app:cardCvErrorText="You must enter 3-digit characters"
        app:cardCvTextSize="14"
        app:cardExpiredErrorText="Your card has expired. Please enter the usage date correctly."
        app:cardFgColor="@android:color/white"
        app:cardMonthErrorText="You must enter 2-digit characters and you'll enter to number the most digit-value is '12'"
        app:cardMonthTextSize="13"
        app:cardNameHelperText="Enter to name on Your Card."
        app:cardNameTextSize="15"
        app:cardNoTextSize="14"
        app:cardNumberHelperText="Enter your 16-digit card number."
        app:cardTextColor="@color/purple_200"
        app:cardYearErrorText="You must enter 2-digit characters and you'll enter to number the most digit-value is '99'"
        app:cardYearTextSize="13" />

</RelativeLayout>
```

**第四步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.os.Bundle;
import android.view.View;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

import com.fevziomurtekin.payview.Payview;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // on below line we are creating a variable
        // for our pay view and initializing it.
        Payview payview = findViewById(R.id.payview);

        // on below line we are setting pay on listener for our card.
        payview.setPayOnclickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // after clicking on pay we are displaying toast message as card added.
                Toast.makeText(MainActivity.this, "Card Added. ", Toast.LENGTH_SHORT).show();
            }
        });
    }
}
```

现在运行你的应用程序，看看代码的输出。

**输出:**

<video class="wp-video-shortcode" id="video-593591-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210418122046/Screenrecorder-2021-04-18-12-12-55-58.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210418122046/Screenrecorder-2021-04-18-12-12-55-58.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210418122046/Screenrecorder-2021-04-18-12-12-55-58.mp4)</video>