# 如何将图片文件从一个活动发送到另一个活动？

> 原文:[https://www . geesforgeks . org/如何将图像文件从一个活动发送到另一个活动/](https://www.geeksforgeeks.org/how-to-send-image-file-from-one-activity-to-another-activity/)

在本文中，我们将从一个活动向另一个活动发送图像。我们将使用 **putExtra** 发送图像，我们将使用**捆绑**获取之前活动发送的数据，然后显示接收到的图像。

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
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <Button
        android:id="@+id/sendimagei"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:padding="16dp"
        android:text="Send Image"
        android:textColor="#000"
        android:textSize="32sp" />

</LinearLayout>
```

**第三步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    Button sendimage;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initialise the layout
        sendimage = findViewById(R.id.sendimagei);
        sendimage.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // add the image in putExtra
                // and send the data in next activity
                Intent sendimage = new Intent(MainActivity.this, SecondActivity.class);
                sendimage.putExtra("image", R.drawable.circle);
                startActivity(sendimage);
            }
        });
    }
}
```

**第 4 步:创建另一个新活动**

参考[这篇](https://www.geeksforgeeks.org/how-to-create-constructor-getter-setter-methods-and-new-activity-in-android-studio-using-shortcuts/)文章，将活动命名为**第二活动。**转到 **activity_second.xml** 文件，参考以下代码。下面是 **activity_second.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    tools:context=".SecondActivity">

    <ImageView
        android:id="@+id/images"
        android:layout_width="250dp"
        android:layout_height="250dp" />

</LinearLayout>
```

**第五步:使用****SecondActivity.java 文件**

转到**SecondActivity.java**文件，参考以下代码。以下是**SecondActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.os.Bundle;
import android.widget.ImageView;

import androidx.appcompat.app.AppCompatActivity;

public class SecondActivity extends AppCompatActivity {

    ImageView imageView;
    int imagevalue;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_second);

        // initialise the layout
        imageView = findViewById(R.id.images);

        // check if any value sent from previous activity
        Bundle bundle = getIntent().getExtras();

        // if bundle is not null then get the image value
        if (bundle != null) {
            imagevalue = bundle.getInt("image");
        }
        imageView.setImageResource(imagevalue);
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-594904-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210420234734/sendimage.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210420234734/sendimage.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210420234734/sendimage.mp4)</video>