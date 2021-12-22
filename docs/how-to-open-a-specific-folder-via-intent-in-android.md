# 如何在安卓中通过意向打开特定文件夹？

> 原文:[https://www . geeksforgeeks . org/如何通过安卓意图打开特定文件夹/](https://www.geeksforgeeks.org/how-to-open-a-specific-folder-via-intent-in-android/)

在本文中，我们将从我们的应用程序中打开一个特定的文件夹。这个特性在很多情况下都很有用。大多数时候，当我们想要上传任何文件时，应用程序只需打开文件管理器。但是我们可以实现这个功能来有效地使用，就像每当任何用户想要上传任何文件时，用户只需选择文件夹名称，如 WhatsApp、下载等。那么用户将只被引导到该文件夹。让我们看看这个特性的实现。

> **参考文章:** [安卓意图](https://www.geeksforgeeks.org/android-tutorial/#Intent%20and%20Intent%20Filters)

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    android:padding="16dp"
    tools:context=".MainActivity">

    <Button
        android:id="@+id/download"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Download Folder" />

    <Button
        android:id="@+id/movies"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Movies Folder" />

    <Button
        android:id="@+id/pic"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Pictures Folder" />

    <Button
        android:id="@+id/whtsapp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Whatsapp Content" />

    <Button
        android:id="@+id/music"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Music Folder" />

</LinearLayout>
```

**第三步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.os.Environment;
import android.view.View;
import android.widget.Button;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    Button movie, download, pic, music, whatsapp;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        movie = findViewById(R.id.movies);
        download = findViewById(R.id.download);
        whatsapp = findViewById(R.id.whtsapp);
        pic = findViewById(R.id.pic);
        music = findViewById(R.id.music);
        movie.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                String path = Environment.getExternalStorageDirectory() + "/" + "Movies" + "/";
                Uri uri = Uri.parse(path);
                Intent intent = new Intent(Intent.ACTION_PICK);
                intent.setDataAndType(uri, "*/*");
                startActivity(intent);
            }
        });
        whatsapp.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                String path = Environment.getExternalStorageDirectory() + "/" + "WhatsApp" + "/";
                Uri uri = Uri.parse(path);
                Intent intent = new Intent(Intent.ACTION_PICK);
                intent.setDataAndType(uri, "*/*");
                startActivity(intent);
            }
        });
        download.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                String path = Environment.getExternalStorageDirectory() + "/" + "Downloads" + "/";
                Uri uri = Uri.parse(path);
                Intent intent = new Intent(Intent.ACTION_PICK);
                intent.setDataAndType(uri, "*/*");
                startActivity(intent);
            }
        });
        music.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                String path = Environment.getExternalStorageDirectory() + "/" + "Music" + "/";
                Uri uri = Uri.parse(path);
                Intent intent = new Intent(Intent.ACTION_PICK);
                intent.setDataAndType(uri, "*/*");
                startActivity(intent);
            }
        });
        pic.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                String path = Environment.getExternalStorageDirectory() + "/" + "Pictures" + "/";
                Uri uri = Uri.parse(path);
                Intent intent = new Intent(Intent.ACTION_PICK);
                intent.setDataAndType(uri, "*/*");
                startActivity(intent);
            }
        });
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-612660-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210517135455/content.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210517135455/content.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210517135455/content.mp4)</video>