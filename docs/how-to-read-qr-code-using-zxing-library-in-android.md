# 如何在安卓系统中使用 Zxing 库读取二维码？

> 原文:[https://www . geesforgeks . org/how-read-QR-code-use-zxing-library-in-Android/](https://www.geeksforgeeks.org/how-to-read-qr-code-using-zxing-library-in-android/)

**z 星**代表斑马线，是目前最流行的集成 **QR(快速响应)**代码处理的开源 API 之一。是用 Java 实现的条码图像处理库，有其他语言的端口。它支持 1D 产品、1D 工业和 2D 条形码。谷歌通过网络搜索使用 ZXing，在可索引的网络上获得数百万个条形码。它还创建了安卓条形码扫描仪应用程序的基础，并被合并到谷歌产品和图书搜索中。

> **注:**使用 **CAMView** 库阅读二维码可以参考 [如何在安卓系统中使用 CAMView 库阅读二维码？](https://www.geeksforgeeks.org/how-to-read-qr-code-using-camview-library-in-android/)

### **二维码**

是**快速响应码**的缩写。它是白色和黑色方块的组合，可以用**二维码扫描仪**轻松读取。它通常使用四种编码模式

*   数字的
*   含字母和数字的
*   字节/二进制
*   汉字

它用于身份验证和在线支付。下面给出了一个 GIF 示例，来了解一下在本文中要做什么。请注意，我们将使用 **Java** 语言来实现这个项目。

![Read QR Code using Zxing Library in Android Sample GIF](img/58000c6e74b2b9da7e41eb877ed56c99.png)

### 逐步实施

在这个项目中，我们正在创建一个基本的二维码扫描仪应用程序，用于扫描二维码并在屏幕上显示结果。

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

> **注:**选择 **API 24** 及以后作为**最小 SDK** 。

**第二步:添加依赖关系**

为了在我们的应用程序中使用 **Zxing** 库，我们需要在我们的应用程序的 gradle 文件中添加它的依赖项。要添加依赖项，请转到**梯度脚本>构建.梯度(模块:应用)**并添加以下依赖项。添加依赖项后，您需要立即点击**同步**。

> 依赖项{
> 
> 实现' com . journeyapps:zxing-Android-embedded:4 . 1 . 0 '
> 
> }

在进一步移动之前，让我们添加一些颜色属性，以增强应用程序栏。转到**应用程序> res >值> colors.xml** 并添加以下颜色属性。

## 可扩展标记语言

```java
<resources> 
    <color name="colorPrimary">#0F9D58</color> 
    <color name="colorPrimaryDark">#16E37F</color> 
    <color name="colorAccent">#03DAC5</color> 
</resources>
```

**第三步:创建布局文件 activity_main.xml**

在这一步中，我们将创建应用程序的布局，它有一个用于扫描的按钮和两个文本视图一个用于二维码的消息内容，第二个用于扫描消息的格式。转到 **app > res >布局> activity_main.xml** 并添加以下代码片段。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textContent"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:layout_margin="10dp"
        android:text="messageContent"/>

    <TextView
        android:id="@+id/textFormat"
        android:text="messageFormat"
        android:layout_width="wrap_content"
        android:layout_gravity="center"
        android:layout_margin="10dp"
        android:layout_height="wrap_content" />

    <Button
        android:id="@+id/scanBtn"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:backgroundTint="#0F9D58"
        android:layout_gravity="center"
        android:text="Scan"/>

</LinearLayout>
```

**第四步:使用 MainActivity.java 文件**

在这一步中，我们将使用**MainActivity.java**文件，在这里我们首先初始化按钮和两个 [**文本视图**](https://www.geeksforgeeks.org/textview-widget-in-android-using-java-with-examples/) 。在按钮的 **onClick()** 行为中，我们创建了 IntentIntegrator 类的对象，用于调用**initiate can()**方法进行扫描处理。之后，在**的 onActivityResult()** 方法中，我们将检查扫描的消息是否为空，然后将消息标记为“已取消”，否则我们将在文本视图中设置扫描的消息及其格式。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;
import android.widget.Toast;

import androidx.annotation.Nullable;
import androidx.appcompat.app.AppCompatActivity;

import com.google.zxing.integration.android.IntentIntegrator;
import com.google.zxing.integration.android.IntentResult;

// implements onClickListener for the onclick behaviour of button
public class MainActivity extends AppCompatActivity implements View.OnClickListener {
    Button scanBtn;
    TextView messageText, messageFormat;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // referencing and initializing
        // the button and textviews
        scanBtn = findViewById(R.id.scanBtn);
        messageText = findViewById(R.id.textContent);
        messageFormat = findViewById(R.id.textFormat);

        // adding listener to the button
        scanBtn.setOnClickListener(this);

    }

    @Override
    public void onClick(View v) {
        // we need to create the object 
        // of IntentIntegrator class
        // which is the class of QR library
        IntentIntegrator intentIntegrator = new IntentIntegrator(this);
        intentIntegrator.setPrompt("Scan a barcode or QR Code");
        intentIntegrator.setOrientationLocked(true);
        intentIntegrator.initiateScan();
    }

    @Override
    protected void onActivityResult(int requestCode, int resultCode, @Nullable Intent data) {
        super.onActivityResult(requestCode, resultCode, data);
        IntentResult intentResult = IntentIntegrator.parseActivityResult(requestCode, resultCode, data);
        // if the intentResult is null then
        // toast a message as "cancelled"
        if (intentResult != null) {
            if (intentResult.getContents() == null) {
                Toast.makeText(getBaseContext(), "Cancelled", Toast.LENGTH_SHORT).show();
            } else {
                // if the intentResult is not null we'll set 
                // the content and format of scan message
                messageText.setText(intentResult.getContents());
                messageFormat.setText(intentResult.getFormatName());
            }
        } else {
            super.onActivityResult(requestCode, resultCode, data);
        }
    }
}
```

### **输出:**

<video class="wp-video-shortcode" id="video-540623-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210112104140/gfgzxinglibrary.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210112104140/gfgzxinglibrary.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210112104140/gfgzxinglibrary.mp4)</video>