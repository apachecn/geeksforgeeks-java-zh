# 安卓系统如何对 Base64 中的图像进行编码和解码？

> 原文:[https://www . geesforgeks . org/如何编码和解码 android 中的 base64 图像/](https://www.geeksforgeeks.org/how-to-encode-and-decode-image-in-base64-in-android/)

在这里，我们将应用图像的“编码-解码”。通过制作这个应用程序，我们将能够了解如何用 Base64 编码图像。我们也将在一个按钮的帮助下解码我们的图像。

**先决条件:**

在继续这个应用程序之前，您应该了解 java 中的 Base64。如果您不知道，请使用 Java 中的[基本类型 Base64 编码和解码](https://www.geeksforgeeks.org/basic-type-base64-encoding-and-decoding-in-java/)。

### 我们将在本文中构建什么？

在本应用程序中，我们将使用两个按钮“编码”和“解码”来执行各自的操作。此外，我们将使用文本视图显示编码文本，最后使用图像视图显示解码图像。注意，我们将使用 **Java** 语言来实现这个应用程序。下面给出了一个示例视频，以了解我们将在本文中做什么。

<video class="wp-video-shortcode" id="video-640553-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210705113603/WhatsApp-Video-2021-07-05-at-11.33.17.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210705113603/WhatsApp-Video-2021-07-05-at-11.33.17.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210705113603/WhatsApp-Video-2021-07-05-at-11.33.17.mp4)</video>

### 逐步实施

**第一步:创建新项目**

*   打开一个新项目。
*   我们将使用 Java 语言来处理空活动。保持所有其他选项不变。
*   您可以在方便的时候更改项目的名称。
*   将有两个名为 **activity_main.xml 和 MainActivity.java**的默认文件。

如果你不知道如何在安卓工作室创建新项目，那么你可以参考[如何在安卓工作室创建/启动新项目？](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)

**第 2 步:导航至应用>清单>和安卓清单. xml 文件，并向其添加以下权限**

```java
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE"/>
```

**步骤 3:使用 activity_main.xml 文件**

在这里，我们将设计应用程序的用户界面。我们将在他们各自的作品中使用以下组件:

*   [文本视图](https://www.geeksforgeeks.org/textview-widget-in-android-using-java-with-examples/)–显示编码文本
*   [图像视图](https://www.geeksforgeeks.org/imageview-in-android-with-example/)–显示解码图像。
*   [按钮](https://www.geeksforgeeks.org/button-in-kotlin/)–点击编码或解码图像。

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<!-- Parent Linear layout -->
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#EFA1A1"
    android:orientation="vertical"
    android:padding="16dp"
    tools:context=".MainActivity">

      <!-- Layout to display buttons
         for encoding and decoding-->
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal">

        <!-- Button for encoding of image-->
        <Button
            android:id="@+id/btn_encode"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_marginEnd="4dp"
            android:layout_marginRight="4dp"
            android:layout_weight="1"
            android:text="Encode Image"
            app:backgroundTint="#511C1C" />

        <!--Button for decoding of image-->
        <Button
            android:id="@+id/btn_decode"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_marginStart="4dp"
            android:layout_marginLeft="4dp"
            android:layout_weight="1"
            android:text="DEcode Image"
            app:backgroundTint="#511C1C" />

    </LinearLayout>

    <!-- Textview to display encoded text-->
    <TextView
        android:id="@+id/textView"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="8dp"
        android:ellipsize="end"
        android:maxLines="5" />

    <!-- Imageview to display decoded image-->
    <ImageView
        android:id="@+id/imageView"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:layout_marginTop="8dp"
        android:adjustViewBounds="true"
        android:scaleType="centerCrop" />

</LinearLayout>
```

实现上述代码后， **activity_main.xml** 文件的设计如下。

![](img/bd0ccbe3ac68b11b5aa3a55f955a248c.png)

**第四步:使用 MainActivity.java 文件**

这里我们为编码和解码按钮的 onClickListeners 编写代码，这样它们就可以执行它们的功能。在**MainActvity.java**文件中使用以下代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import androidx.annotation.NonNull;
import androidx.annotation.Nullable;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.app.ActivityCompat;
import androidx.core.content.ContextCompat;

import android.Manifest;
import android.content.Intent;
import android.content.pm.PackageManager;
import android.graphics.Bitmap;
import android.graphics.BitmapFactory;
import android.net.Uri;
import android.os.Bundle;
import android.provider.MediaStore;
import android.util.Base64;
import android.view.View;
import android.widget.Button;
import android.widget.ImageView;
import android.widget.TextView;
import android.widget.Toast;

import java.io.ByteArrayOutputStream;
import java.io.IOException;

public class MainActivity extends AppCompatActivity {

    // Initialize variable
    Button btnEncode,btnDecode;
    TextView textView;
    ImageView imageView;
    String sImage;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        btnEncode=findViewById(R.id.btn_encode);
        btnDecode=findViewById(R.id.btn_decode);
        textView=findViewById(R.id.textView);
        imageView= findViewById(R.id.imageView);

        // Code for Encode button
        btnEncode.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

                // check condition
                if (ContextCompat.checkSelfPermission(MainActivity.this,
                        Manifest.permission.READ_EXTERNAL_STORAGE)!= PackageManager.PERMISSION_GRANTED)
                {
                    // when permission is nor granted
                    // request permission
                    ActivityCompat.requestPermissions(MainActivity.this
                    , new String[]{Manifest.permission.READ_EXTERNAL_STORAGE},100);

                }
                else
                {
                    // when permission
                      // is granted
                    // create method
                    selectImage();
                }
            }

        });

         // Code for Decode button
        btnDecode.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                // decode base64 string
                byte[] bytes=Base64.decode(sImage,Base64.DEFAULT);
                // Initialize bitmap
                Bitmap bitmap= BitmapFactory.decodeByteArray(bytes,0,bytes.length);
                // set bitmap on imageView
                imageView.setImageBitmap(bitmap);
            }
        });
    }
    private void selectImage() {
        // clear previous data
        textView.setText("");
        imageView.setImageBitmap(null);
        // Initialize intent
        Intent intent=new Intent(Intent.ACTION_PICK);
        // set type
        intent.setType("image/*");
        // start activity result
        startActivityForResult(Intent.createChooser(intent,"Select Image"),100);
    }

    @Override
    public void onRequestPermissionsResult(int requestCode, @NonNull  String[] permissions, @NonNull  int[] grantResults) {
        super.onRequestPermissionsResult(requestCode, permissions, grantResults);

        // check condition
        if (requestCode==100 && grantResults[0]==PackageManager.PERMISSION_GRANTED)
        {
            // when permission
              // is granted
            // call method
            selectImage();
        }
        else
        {
            // when permission is denied
            Toast.makeText(this, "Permission Denied", Toast.LENGTH_SHORT).show();
        }
    }

    @Override
    protected void onActivityResult(int requestCode, int resultCode, @Nullable  Intent data) {
        super.onActivityResult(requestCode, resultCode, data);
        // check condition
        if (requestCode==100 && resultCode==RESULT_OK && data!=null)
        {
            // when result is ok
            // initialize uri
            Uri uri=data.getData();
            // Initialize bitmap
            try {
                Bitmap bitmap= MediaStore.Images.Media.getBitmap(getContentResolver(),uri);
                // initialize byte stream
                ByteArrayOutputStream stream=new ByteArrayOutputStream();
                // compress Bitmap
                bitmap.compress(Bitmap.CompressFormat.JPEG,100,stream);
                // Initialize byte array
                byte[] bytes=stream.toByteArray();
                // get base64 encoded string
                sImage= Base64.encodeToString(bytes,Base64.DEFAULT);
                // set encoded text on textview
                textView.setText(sImage);

            } catch (IOException e) {
                e.printStackTrace();
            }
        }
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-640553-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210705113603/WhatsApp-Video-2021-07-05-at-11.33.17.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210705113603/WhatsApp-Video-2021-07-05-at-11.33.17.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210705113603/WhatsApp-Video-2021-07-05-at-11.33.17.mp4)</video>