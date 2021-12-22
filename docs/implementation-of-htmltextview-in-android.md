# 在安卓中实现 html textview

> 原文:[https://www . geesforgeks . org/implementation-of-html textview-in-Android/](https://www.geeksforgeeks.org/implementation-of-htmltextview-in-android/)

**HtmlTextView** 是安卓的扩展 [TextView](https://www.geeksforgeeks.org/working-with-the-textview-in-android/) 组件，可以通过将 HTML 组件转换成安卓 Spannables 进行查看来加载。除了 HTML 标签，该库还允许从本地可绘制文件夹或互联网加载图像，以及从互联网加载网址。在本文中，我们将使用 Html 组件在 Android 中显示文本、图像和 URL。

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:把这个添加到 AndroidManifest.xml 文件**

```
<uses-permission android:name="android.permission.INTERNET"/>
```

将此添加到 **build.gradle** 文件中

```
implementation 'org.sufficientlysecure:html-textview:4.0'
```

**步骤 3:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/text"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

    <org.sufficientlysecure.htmltextview.HtmlTextView
        android:id="@+id/text2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="16sp" />

    <org.sufficientlysecure.htmltextview.HtmlTextView
        android:id="@+id/text3"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="16sp" />

</LinearLayout>
```

**步骤 4:使用 MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码

```
Spanned spanned= HtmlFormatter.formatHtml(new HtmlFormatterBuilder()
                .setHtml("<p><big><bold>GeeksForGeeks</bold></big><p>"));
                // load text using HtmlFormatterBuilder
text2.setHtml("<font color='blue'><a href='https://www.google.com'</a>Go to this link</font>");
        text2.setOnClickATagListener(new OnClickATagListener() {
            @Override
            public boolean onClick(View widget, String spannedText, @Nullable String href) {
                Toast.makeText(getApplicationContext(),href,Toast.LENGTH_LONG).show();
                return false;
            }
        });
// loading image using HtmlAssetsImageGetter
text1.setHtml("Load Image From Asset<br><img src='image.png'/>",new HtmlAssetsImageGetter(text1));
```

下面是**文件的代码。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
import android.os.Bundle;
import android.text.Spanned;
import android.view.View;
import android.widget.TextView;
import android.widget.Toast;

import androidx.annotation.Nullable;
import androidx.appcompat.app.AppCompatActivity;

import org.sufficientlysecure.htmltextview.HtmlAssetsImageGetter;
import org.sufficientlysecure.htmltextview.HtmlFormatter;
import org.sufficientlysecure.htmltextview.HtmlFormatterBuilder;
import org.sufficientlysecure.htmltextview.OnClickATagListener;

public class MainActivity extends AppCompatActivity {

    TextView gtext;
    org.sufficientlysecure.htmltextview.HtmlTextView text1, text2;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        gtext = findViewById(R.id.text);
        text1 = findViewById(R.id.text2);
        text2 = findViewById(R.id.text3);
        Spanned spanned = HtmlFormatter.formatHtml(new HtmlFormatterBuilder().setHtml("
<p><big><bold>GeeksForGeeks</bold></big>
<p>"));
        gtext.setText(spanned);
        text2.setHtml("<font color='blue'><a href='https://www.google.com'</a>Go to this link</font>");
        text2.setOnClickATagListener(new OnClickATagListener() {
            @Override
            public boolean onClick(View widget, String spannedText, @Nullable String href) {
                Toast.makeText(getApplicationContext(), href, Toast.LENGTH_LONG).show();
                return false;
            }
        });
        text1.setHtml("Load Image From Asset<br><img src='image.png'/>", new HtmlAssetsImageGetter(text1));
    }
}
```

****输出:****

**<video class="wp-video-shortcode" id="video-587672-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210403145244/htmlt.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210403145244/htmlt.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210403145244/htmlt.mp4)</video>**