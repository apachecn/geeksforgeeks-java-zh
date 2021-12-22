# 安卓中可绘制视图

> 原文:[https://www.geeksforgeeks.org/drawableview-in-android/](https://www.geeksforgeeks.org/drawableview-in-android/)

在本文中，我们将展示 DrawableView 的实现。我们将在笔记本电脑上实现绘画。让我们看看这个特性的实现。下面给出了一个示例视频，以了解我们将在本文中做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-613903-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210517143050/drawablev.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210517143050/drawablev.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210517143050/drawablev.mp4)</video>

**可用功能**

*   增加笔画宽度
*   减小笔画宽度
*   更改笔画的颜色
*   撤销这幅画

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:添加依赖关系**

导航到**渐变脚本>构建.渐变(模块:应用)**，并在依赖项部分添加以下依赖项。

> 编译“me.panavtec:drawableview:0.6.0”

**步骤 3:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal">

        <Button
            android:id="@+id/increase"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="+" />

        <Button
            android:id="@+id/decrease"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="-" />

        <Button
            android:id="@+id/color"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Color" />

        <Button
            android:id="@+id/undo"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Undo" />

    </LinearLayout>

    <me.panavtec.drawableview.DrawableView
        android:id="@+id/paintView"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="1" />

</LinearLayout>
```

**第四步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.graphics.Color;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

import androidx.appcompat.app.AppCompatActivity;

import java.util.Random;

import me.panavtec.drawableview.DrawableView;
import me.panavtec.drawableview.DrawableViewConfig;

public class MainActivity extends AppCompatActivity {

    DrawableView drawableView;
    DrawableViewConfig config;
    Button increase, decrease, color, undo;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initialise the value
        initiaselayout();
    }

    private void initiaselayout() {

        // initialise the layout
        drawableView = findViewById(R.id.paintView);
        increase = findViewById(R.id.increase);
        decrease = findViewById(R.id.decrease);
        color = findViewById(R.id.color);
        undo = findViewById(R.id.undo);
        config = new DrawableViewConfig();

        // set stroke color as black initially
        config.setStrokeColor(getResources().getColor(android.R.color.black));

        // If the view is bigger than canvas, 
        // with this the user will see the bounds (Recommended)
        config.setShowCanvasBounds(true);

        // set width as 20
        config.setStrokeWidth(20.0f);
        config.setMinZoom(1.0f);
        config.setMaxZoom(3.0f);

        // set canvas height
        config.setCanvasHeight(1080);

        // set canvas width
        config.setCanvasWidth(1920);
        drawableView.setConfig(config);
        increase.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                // increase the stroke width by 10
                config.setStrokeWidth(config.getStrokeWidth() + 10);
            }
        });
        decrease.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                // decrease stroke width by 10
                config.setStrokeWidth(config.getStrokeWidth() - 10);
            }
        });
        color.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                // initialise Random
                Random random = new Random();
                // set the color using random
                config.setStrokeColor(Color.rgb(255, random.nextInt(256), random.nextInt(256)));
            }
        });
        undo.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                // undo the most recent changes
                drawableView.undo();
            }
        });
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-613903-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210517143050/drawablev.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210517143050/drawablev.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210517143050/drawablev.mp4)</video>