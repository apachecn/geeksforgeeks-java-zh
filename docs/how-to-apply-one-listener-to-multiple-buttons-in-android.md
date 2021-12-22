# 如何在安卓系统中将一个监听器应用到多个按钮？

> 原文:[https://www . geeksforgeeks . org/如何将一个监听器应用于多个安卓按钮/](https://www.geeksforgeeks.org/how-to-apply-one-listener-to-multiple-buttons-in-android/)

在本文中，我们将编写一个短代码，用于在不同的按钮上应用点击事件，而不是为不同的按钮编写不同的方法，我们将只为所有存在的按钮构建一个单一的方法 **onClick()** ，通过使用[开关案例](https://www.geeksforgeeks.org/switch-statement-in-java/)的概念，我们可以在不同的按钮上执行不同的活动。现在，在不浪费更多时间的情况下，让我们看看实现。

### 我们将在本文中构建什么？

在本文中，我们将开发一个包含三个**按钮**的示例应用程序，通过单击这三个按钮，我们可以仅使用一个 **onClick()** 方法来执行不同的操作。下面给出了一个示例视频，以了解我们将在本文中做什么。请注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-614249-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210522101256/WhatsApp-Video-2021-05-22-at-10.03.53-AM.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210522101256/WhatsApp-Video-2021-05-22-at-10.03.53-AM.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210522101256/WhatsApp-Video-2021-05-22-at-10.03.53-AM.mp4)</video>

### 逐步实施

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

现在是时候设计应用程序的布局了。为此，转到**应用程序> res >布局> activity_main.xml** 并将下面编写的代码粘贴到 **activity_main.xml** 文件中。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:id="@+id/root_layout"
    tools:context=".MainActivity">

      <!--add three buttons in layout-->
    <Button
        android:id="@+id/button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="220px"
        android:text="Button 1" />

    <Button
        android:id="@+id/button2"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/button"
        android:layout_centerHorizontal="true"
        android:text="Button 2" />

    <Button
        android:id="@+id/button3"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/button2"
        android:layout_centerHorizontal="true"
        android:text="Button 3" />

</RelativeLayout>
```

**步骤 3:使用 MainActivity.java 文件**

转到 **app > java >包名>MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity implements View.OnClickListener {

    // creating three buttons 
      // by the of btn1, btn2,btn3
    Button btn1, btn2 ,btn3;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // connecting buttons with the 
          // layout using findViewById()
        btn1= findViewById(R.id.button);
        btn2= findViewById(R.id.button2);
        btn3= findViewById(R.id.button3);

        // apply setOnClickListener over buttons
        btn1.setOnClickListener(this);
        btn2.setOnClickListener(this);
        btn3.setOnClickListener(this);

    }

    // common onClick() for all buttons
    @Override
    public void onClick(View v) {

        switch (v.getId()){

            // cases applied over different buttons
            case R.id.button:

                // Toast message appears when button pressed
                Toast.makeText(this, "button1 pressed", Toast.LENGTH_SHORT).show();
                break;

            case R.id.button2:

                Toast.makeText(this, "button2 pressed", Toast.LENGTH_SHORT).show();
                break;

            case R.id.button3:

                Toast.makeText(this, "button3 pressed", Toast.LENGTH_SHORT).show();
                break;
        }
    }
}
```

仅此而已，现在应用程序已准备好安装在设备上。下面是应用程序的输出。

**输出:**

<video class="wp-video-shortcode" id="video-614249-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210522101256/WhatsApp-Video-2021-05-22-at-10.03.53-AM.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210522101256/WhatsApp-Video-2021-05-22-at-10.03.53-AM.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210522101256/WhatsApp-Video-2021-05-22-at-10.03.53-AM.mp4)</video>