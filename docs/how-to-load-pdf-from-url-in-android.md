# 如何在安卓系统中从 URL 加载 PDF？

> 原文:[https://www . geeksforgeeks . org/如何从 android 中的 url 加载 pdf/](https://www.geeksforgeeks.org/how-to-load-pdf-from-url-in-android/)

大多数应用程序都要求在其应用程序中包含显示 PDF 文件的支持。因此，如果我们必须在我们的应用程序中使用多个 PDF 文件，实际上不可能在我们的应用程序中添加每个 PDF 文件，因为这种方法可能会导致应用程序的大小增加，并且没有用户愿意下载如此大的应用程序。因此，为了解决这个与大小相关的问题，我们将直接在应用程序中从服务器加载 PDF 文件，而不会实际将这些文件保存在应用程序中。从服务器加载 PDF 文件将有助于我们管理应用程序大小的增加。所以在这篇文章中，我们将看看如何从我们的安卓应用程序中的网址加载 PDF 文件。

## PDFView 的实现

为了添加这个 PDF 视图，我们正在使用一个库，它将帮助我们从网址加载 PDF。注意，我们将使用 **Java** 语言来实现这个项目。

### 逐步实施

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:添加依赖项进行构建. gradle(模块:app)**

导航到**渐变脚本>构建.渐变(模块:应用)**，并在依赖项部分添加以下依赖项。

> 实现' com . github . barteksc:Android-pdf-viewer:2 . 8 . 2 '

现在同步选项将出现在右上角点击立即同步选项。

**第三步:在你的 AndroidManifest.xml 文件**中添加访问互联网的权限

在您的 **AndroidManifest.xml** 文件中添加以下两行。

**第 4 步:使用 activity_main.xml 文件**

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

    <!--PDF Viewer to display our PDF-->
    <com.github.barteksc.pdfviewer.PDFView
        android:id="@+id/idPDFView"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />

</RelativeLayout>
```

**步骤 5:使用 MainActivity.java 文件**

导航到**应用程序> java >您的应用程序包名称>MainActivity.java**文件。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.os.AsyncTask;
import android.os.Bundle;

import androidx.appcompat.app.AppCompatActivity;

import com.github.barteksc.pdfviewer.PDFView;

import java.io.BufferedInputStream;
import java.io.IOException;
import java.io.InputStream;
import java.net.HttpURLConnection;
import java.net.URL;

import javax.net.ssl.HttpsURLConnection;

public class MainActivity extends AppCompatActivity {

    // creating a variable
    // for PDF view.
    PDFView pdfView;

    // url of our PDF file.
    String pdfurl = "https://www.w3.org/WAI/ER/tests/xhtml/testfiles/resources/pdf/dummy.pdf";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        // initializing our pdf view.
        pdfView = findViewById(R.id.idPDFView);
        new RetrivePDFfromUrl().execute(pdfurl);
    }

    // create an async task class for loading pdf file from URL.
    class RetrivePDFfromUrl extends AsyncTask<String, Void, InputStream> {
        @Override
        protected InputStream doInBackground(String... strings) {
            // we are using inputstream 
            // for getting out PDF.
            InputStream inputStream = null;
            try {
                URL url = new URL(strings[0]);
                // below is the step where we are 
                // creating our connection.
                HttpURLConnection urlConnection = (HttpsURLConnection) url.openConnection();
                if (urlConnection.getResponseCode() == 200) {
                    // response is success.
                    // we are getting input stream from url 
                    // and storing it in our variable.
                    inputStream = new BufferedInputStream(urlConnection.getInputStream());
                }

            } catch (IOException e) {
                // this is the method 
                // to handle errors.
                e.printStackTrace();
                return null;
            }
            return inputStream;
        }

        @Override
        protected void onPostExecute(InputStream inputStream) {
            // after the execution of our async 
            // task we are loading our pdf in our pdf view.
            pdfView.fromStream(inputStream).load();
        }
    }
}
```

> **注意:**如果你已经更新到 Android Studio 4.0 或更高版本，那么你可能会面临以下错误
> 
> ```
> Execution failed for task ':app:stripDebugDebugSymbols'.
> NDK at ~/Library/Android/sdk/ndk-bundle did not have a source.properties file
> ```
> 
> 请参考[本](https://stackoverflow.com/questions/64372383/ndk-at-library-android-sdk-ndk-bundle-did-not-have-a-source-properties-file)修复错误。

### 输出:

<video class="wp-video-shortcode" id="video-530139-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201215133531/Screenrecorder-2020-12-15-13-33-42-833.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201215133531/Screenrecorder-2020-12-15-13-33-42-833.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201215133531/Screenrecorder-2020-12-15-13-33-42-833.mp4)</video>

**出库项目:**[https://github . com/chaitanyamunje/gfgimanag leader/tree/pdf viewer](https://github.com/ChaitanyaMunje/GFGImageSlider/tree/PDFViewer)