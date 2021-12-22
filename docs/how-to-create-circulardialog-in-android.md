# 如何在安卓中创建循环对话框？

> 原文:[https://www . geesforgeks . org/how-create-circulation-in-Android/](https://www.geeksforgeeks.org/how-to-create-circulardialog-in-android/)

**循环对话框**是安卓应用中表示信息或数据的另一种最佳方式。您可以在大多数应用程序中看到这些循环对话框，它们用于以吸引人的形式显示流程完成的消息。在本文中，我们将看到如何在安卓应用程序中实现循环对话框。下面给出了一个 GIF 示例，来了解一下我们将在本文中做什么。注意，我们将使用 **Java** 语言来实现这个项目。

![CircularDialog in Android Sample GIF](img/9a3a92ff140a81e67d3efd3180e3c209.png)

### 循环对话框的应用

*   用于以吸引人的形式表示信息。
*   循环对话框是在警报对话框中表示消息的一种独特方式。
*   创造优质的用户体验。

### **圆形对话框的属性**

<figure class="table">

| 

属性

 | 

描述

 |
| --- | --- |
| CDConstants。成功ˌ成就 | 在循环对话框中显示成功消息。 |
| 。设置动画 | 用于将动画设置为循环对话框。 |
| 。setTextSize | 用于在循环对话框中设置文本大小。 |
| 。设置持续时间 | 用于以毫秒为单位设置动画时间。 |
| 疾控中心。大的 | 用于设置对话框的大小。 |

</figure>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:添加依赖和 JitPack 存储库**

导航到**渐变脚本>构建.渐变(模块:应用)**，并在依赖项部分添加以下依赖项。

> 实现' com . github . hassanusman:circulationdialogs:1.2 '

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

**步骤 3:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--After clicking button you will
        get circular dialog-->
    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:text="CLICK" />

</RelativeLayout>
```

**第四步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

import androidx.appcompat.app.AppCompatActivity;

import com.example.circulardialog.CDialog;
import com.example.circulardialog.extras.CDConstants;

public class MainActivity extends AppCompatActivity {

    // Initialize button
    Button button;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Called button by Id
        button = (Button) findViewById(R.id.button);

        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

                // Circular Dialog Box Created
                new CDialog(MainActivity.this).createAlert("Great",
                        CDConstants.SUCCESS,   // Type of dialog
                        CDConstants.LARGE)     // Size of dialog
                        .setAnimation(CDConstants.SLIDE_FROM_BOTTOM_TO_TOP)  // Animation for enter/exit
                        .setDuration(2000)   // in milliseconds
                        .setTextSize(CDConstants.LARGE_TEXT_SIZE)  // CDConstants.LARGE_TEXT_SIZE, 
                                                                   // CDConstants.NORMAL_TEXT_SIZE
                        .show();
            }
        });
    }
}
```

现在点击**运行**选项**构建 Gradle 需要一些时间。**之后，您将在设备上获得如下所示的输出。

### **输出:**

<video class="wp-video-shortcode" id="video-546140-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210117163728/Screenrecorder-2021-01-17-16-32-45-522.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210117163728/Screenrecorder-2021-01-17-16-32-45-522.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210117163728/Screenrecorder-2021-01-17-16-32-45-522.mp4)</video>