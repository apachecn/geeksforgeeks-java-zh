# 安卓反浮动动作按钮示例

> 原文:[https://www . geesforgeks . org/counter-floating-action-button-in-Android-with-example/](https://www.geeksforgeeks.org/counter-floating-action-button-in-android-with-example/)

在大多数电子商务应用程序中都可以看到“反浮动操作”按钮，我们使用该功能来显示用户购物车中的商品数量。在本文中，我们将看看如何在安卓工作室的安卓应用程序中实现这个反浮动操作按钮。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将简单地显示一个浮动操作按钮，我们将向它添加一个计数器。点击该按钮后，我们将递增和递减应用于浮动操作按钮的计数器。下面是视频，我们将在其中看到我们将在本文中构建的内容。

<video class="wp-video-shortcode" id="video-594391-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210419194833/20210419_194750.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210419194833/20210419_194750.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210419194833/20210419_194750.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:添加依赖关系**

导航到**渐变脚本>构建.渐变(模块:应用)**，并在依赖项部分添加以下依赖项。

> 实现' com . github . Andre mion:counter fab:1 . 2 . 2 '

添加这个依赖项后，现在同步您的项目，我们将继续使用 XML 文件。

**步骤 3:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/idRLView"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:orientation="horizontal"
        android:weightSum="2">

        <!--creating a counter fab for incrementing a count-->
        <com.andremion.counterfab.CounterFab
            android:id="@+id/fabOne"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_gravity="center"
            android:layout_margin="20dp"
            android:layout_weight="1"
            android:src="@drawable/ic_add"
            android:tint="@color/purple_200"
            app:backgroundTint="@color/white"
            app:badgeBackgroundColor="@color/purple_200"
            app:badgePosition="RightTop"
            app:badgeTextColor="@color/white" />

        <!--creating a counter fab for decrementing a count-->
        <!--in this we are passing badge position as top right
            badge text color as white
            badge back ground color as green -->
        <com.andremion.counterfab.CounterFab
            android:id="@+id/fabTwo"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_gravity="center"
            android:layout_margin="20dp"
            android:layout_weight="1"
            android:src="@drawable/ic_sub_icon"
            android:tint="@color/white"
            app:backgroundTint="@color/white"
            app:badgeBackgroundColor="@color/purple_200"
            app:badgePosition="RightTop"
            app:badgeTextColor="@color/white" />
    </LinearLayout>

</RelativeLayout>
```

**第四步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.os.Bundle;
import android.view.View;

import androidx.appcompat.app.AppCompatActivity;

import com.andremion.counterfab.CounterFab;

public class MainActivity extends AppCompatActivity {

    CounterFab fabOne, fabTwo;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initializing our variables.
        fabOne = findViewById(R.id.fabOne);
        fabTwo = findViewById(R.id.fabTwo);

        // on below line we are setting default
        // count as 10 for both our fab.
        fabOne.setCount(10);
        fabTwo.setCount(10);

        // on below line we are adding click listener for fab one and fab two.
        fabOne.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // on below line we are calling a
                // method to increase the fab count.
                fabOne.increase();
            }
        });
        fabTwo.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // on below line we are calling a 
                // method to decrease the fab count.
                fabTwo.decrease();
            }
        });
    }
}
```

现在运行您的应用程序，并查看应用程序的输出。

**输出:**

<video class="wp-video-shortcode" id="video-594391-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210419194833/20210419_194750.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210419194833/20210419_194750.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210419194833/20210419_194750.mp4)</video>