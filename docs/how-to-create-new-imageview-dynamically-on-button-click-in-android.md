# 如何在安卓中点击按钮动态创建新的 ImageView？

> 原文:[https://www . geesforgeks . org/how-new-imageview-动态点击按钮-点击进入安卓/](https://www.geeksforgeeks.org/how-to-create-new-imageview-dynamically-on-button-click-in-android/)

在本文中，我们将实现一个与 ImageView 相关的非常重要的特性。这里我们将动态添加 ImageView。我们将只是改变背景颜色。每当我们点击一个按钮，就会创建一个新的图像视图。所以在这里，我们将学习如何实现这个特性。下面给出了一个示例视频，以了解我们将在本文中做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-593370-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210410232854/addiview.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210410232854/addiview.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210410232854/addiview.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/layout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:layout_marginTop="20dp"
    android:gravity="center_horizontal"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <!--Adding the Button in the layout-->
    <Button
        android:id="@+id/addiview"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:background="@color/purple_500"
        android:text="Add Image View"
        android:textColor="@color/black" />

</LinearLayout>
```

**步骤 3:使用 MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。这里我们正在创建一个图像视图和一个布局，并将在布局中添加图像视图。这就是我们创建图像视图的方式

```
ImageView imageView=new ImageView(AddImageViw.this);
// adding the image in ImageView
imageView.setImageResource(R.mipmap.ic_launcher);
```

这就是我们在布局中添加新创建的图像视图的方式。

```
LinearLayout.LayoutParams params=new LinearLayout.LayoutParams(width,height);
        params.setMargins(0,10,0,10); // setting the margin in the layout 
        imageView.setLayoutParams(params);
        layout.addView(imageView);    // adding the image in the layout
```

下面是完整的代码为**MainActivity.java**的文件。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.graphics.Color;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.ImageView;
import android.widget.LinearLayout;

import androidx.appcompat.app.AppCompatActivity;

import java.util.Random;

public class MainActivity extends AppCompatActivity {

    Button addview;
    LinearLayout layout;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initialising layout
        addview = findViewById(R.id.addiview);
        layout = findViewById(R.id.layout);

        // we will click on the add view button
        addview.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                // initialising new layout
                ImageView imageView = new ImageView(MainActivity.this);

                // setting the image in the layout
                imageView.setImageResource(R.mipmap.ic_launcher);

                // calling addview with width and height
                addvieW(imageView, 200, 200);

                // adding the background color
                colorrandom(imageView);
            }
        });
    }

    public void colorrandom(ImageView imageView) {

        // Initialising the Random();
        Random random = new Random();

        // adding the random background color
        int color = Color.argb(255, random.nextInt(256), random.nextInt(256), random.nextInt(256));

        // setting the background color
        imageView.setBackgroundColor(color);
    }

    private void addvieW(ImageView imageView, int width, int height) {
        LinearLayout.LayoutParams params = new LinearLayout.LayoutParams(width, height);

        // setting the margin in linearlayout
        params.setMargins(0, 10, 0, 10);
        imageView.setLayoutParams(params);

        // adding the image in layout
        layout.addView(imageView);
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-593370-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210410232854/addiview.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210410232854/addiview.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210410232854/addiview.mp4)</video>