# 如何在安卓 App 中使用 PRDownloader 库？

> 原文:[https://www . geesforgeks . org/使用方法-prdownloader-Android 中的库-app/](https://www.geeksforgeeks.org/how-to-use-prdownloader-library-in-android-app/)

**PRDownloader 库**是安卓的文件下载器库。下载文件时，它会暂停并恢复支持。该库能够从互联网下载大文件，可以下载任何类型的文件，如图像、视频、pdf、apk 等。它提供了许多功能，可以帮助用户轻松高效地从互联网下载文件。使用该库，您还可以使用下载 id 检查下载状态，并可以使用下载 id 执行许多其他重要操作。这个库包含许多重要的方法，让用户可以完全控制文件的下载状态，如暂停、取消、恢复等。您可以使用此库提出以下请求:

**暂停下载请求:**

```
PRDownloader.pause(downloadId);
```

**取消下载请求:**

```
// Cancel with the download id
PRDownloader.cancel(downloadId);
// The tag can be set to any request and then can be used to cancel the request
PRDownloader.cancel(TAG);
// Cancel all the requests
PRDownloader.cancelAll();
```

**恢复下载请求:**

```
PRDownloader.resume(downloadId);
```

**获取下载请求的状态:**

```
Status status = PRDownloader.getStatus(downloadId);
```

### **本文我们要构建什么？**

下面给出一个视频样本，了解一下在本文中我们要做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-644511-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210710182504/1625920841669.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210710182504/1625920841669.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210710182504/1625920841669.mp4)</video>

### **分步实施**

**第一步:创建新项目**

在安卓工作室创建新项目请参考 [<u>【如何在安卓工作室创建/启动新项目】</u>](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/) 。然后在名称字段中输入您的应用名称，并从语言下拉菜单中选择 Java。

**第二步:添加依赖关系**

要添加依赖项，请导航至**应用程序>渐变脚本>渐变构建(模块:应用)**，并在依赖项部分添加以下依赖项。添加依赖项后，同步您的项目。

```
implementation 'com.mindorks.android:prdownloader:0.6.0'
```

**第三步:添加互联网权限**

导航至 **app >清单> AndroidManifest.xml** 并添加互联网权限。

```
<uses-permission android:name="android.permission.INTERNET"/>
```

**第 4 步:使用 activity_main.xml 文件**

导航到 **app > res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是**activity _ main . XML**文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!-- EditText to take the url from the user -->
    <EditText
        android:id="@+id/url_etText"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:hint="@string/type_or_paste_your_url_here" />

    <!-- Button to start downloading from file -->
    <Button
        android:id="@+id/btn_download"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/url_etText"
        android:layout_centerHorizontal="true"
        android:text="@string/download" />

    <!-- linear layout that contains widgets to show information -->
    <LinearLayout
        android:id="@+id/details_box"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@+id/btn_download"
        android:layout_margin="10dp"
        android:layout_marginTop="20dp"
        android:background="@drawable/box_design_layout"
        android:orientation="vertical"
        android:padding="10dp"
        android:visibility="gone">

        <!-- Textview to show the file name -->
        <TextView
            android:id="@+id/file_name"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="@string/click_on_start_button_to_start_downloading"
            android:textSize="20sp"
            android:textStyle="bold" />

        <!-- progress bar to show the progress of downloading -->
        <ProgressBar
            android:id="@+id/progress_horizontal"
            style="@style/Widget.AppCompat.ProgressBar.Horizontal"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginLeft="4dp"
            android:layout_marginRight="4dp"
            android:progressTint="@color/purple_200"
            tools:ignore="UnusedAttribute" />

        <!-- textview to show the downloading percentage -->
        <TextView
            android:id="@+id/downloading_percentage"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="center_horizontal"
            android:textAlignment="center"
            android:textSize="12sp"
            android:textStyle="bold" />

        <!-- this linear layout contains buttons -->
        <LinearLayout
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_gravity="center_horizontal"
            android:orientation="horizontal"
            android:padding="10dp">

            <!-- button to start the downloading -->
            <Button
                android:id="@+id/btn_start"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="@string/start" />

            <!-- button to cancel or stop the downloading -->
            <Button
                android:id="@+id/btn_stop"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="@string/stop" />

        </LinearLayout>

    </LinearLayout>

    <!-- this textview will show the path where
         the downloaded file is stored -->
    <TextView
        android:id="@+id/txt_url"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@+id/details_box"
        android:layout_marginTop="10dp"
        android:textSize="15sp"
        android:textStyle="bold" />

</RelativeLayout>
```

**下面是 Strings.xml 文件**的代码

## 可扩展标记语言

```
<resources>
    <string name="app_name">GFG PRDownloader Library</string>
    <string name="download">DOWNLOAD</string>
    <string name="type_or_paste_your_url_here">Type or Paste Your URL Here</string>
    <string name="start">START</string>
    <string name="stop">STOP</string>
    <string name="click_on_start_button_to_start_downloading">Click on Start Button to Start Downloading</string>
</resources>
```

**第五步:设计箱体布局**

导航到**应用程序>资源>可绘制>右键单击>新建>可绘制资源文件**，并将该文件命名为 **box_design_layout** ，并将以下代码添加到该文件中。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android"
    android:shape="rectangle">

    <corners
        android:bottomLeftRadius="0dp"
        android:bottomRightRadius="0dp"
        android:topLeftRadius="0dp"
        android:topRightRadius="0dp" />

    <stroke
        android:width="1dp"
        android:color="@android:color/black" />

    <solid android:color="@android:color/transparent" />

</shape>
```

**第 6 步:创建 Util 类**

导航到**应用程序> java >包名>右键单击>新建> Java 类**，并将该文件命名为**Utils.java。**将以下代码添加到**Utils.java。**以下是**Utils.java 的代码。**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.Context;
import android.os.Environment;

import androidx.core.content.ContextCompat;

import java.io.File;
import java.util.Locale;

public final class Utils {

    private Utils() {

    }

    public static String getRootDirPath(Context context) {
        if (Environment.MEDIA_MOUNTED.equals(Environment.getExternalStorageState())) {
            File file = ContextCompat.getExternalFilesDirs(context.getApplicationContext(), null)[0];
            return file.getAbsolutePath();
        } else {
            return context.getApplicationContext().getFilesDir().getAbsolutePath();
        }
    }

    public static String getProgressDisplayLine(long currentBytes, long totalBytes) {
        return getBytesToMBString(currentBytes) + "/" + getBytesToMBString(totalBytes);
    }

    private static String getBytesToMBString(long bytes) {
        return String.format(Locale.ENGLISH, "%.2fMb", bytes / (1024.00 * 1024.00));
    }
}
```

**第七步:与 MainActivity.java 合作**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.annotation.SuppressLint;
import android.os.Bundle;
import android.view.View;
import android.webkit.URLUtil;
import android.widget.Button;
import android.widget.EditText;
import android.widget.LinearLayout;
import android.widget.ProgressBar;
import android.widget.TextView;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

import com.downloader.Error;
import com.downloader.OnCancelListener;
import com.downloader.OnDownloadListener;
import com.downloader.OnPauseListener;
import com.downloader.OnProgressListener;
import com.downloader.OnStartOrResumeListener;
import com.downloader.PRDownloader;
import com.downloader.Progress;
import com.downloader.Status;

public class MainActivity extends AppCompatActivity {

    private EditText editTextUrl;
    private String path;
    private TextView file_downloaded_path, file_name, downloading_percent;
    private ProgressBar progressBar;
    private Button btnStart, btnCancel, buttonDownload;
    private LinearLayout details;
    int downloadID;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Initializing PRDownloader library
        PRDownloader.initialize(this);

        // finding edittext by its id
        editTextUrl = findViewById(R.id.url_etText);

        // finding button by its id
        buttonDownload = findViewById(R.id.btn_download);

        // finding textview by its id
        file_downloaded_path = findViewById(R.id.txt_url);

        // finding textview by its id
        file_name = findViewById(R.id.file_name);

        // finding progressbar by its id
        progressBar = findViewById(R.id.progress_horizontal);

        // finding textview by its id
        downloading_percent = findViewById(R.id.downloading_percentage);

        // finding button by its id
        btnStart = findViewById(R.id.btn_start);

        // finding button by its id
        btnCancel = findViewById(R.id.btn_stop);

        // finding linear layout by its id
        details = findViewById(R.id.details_box);

        //storing the path of the file
        path = Utils.getRootDirPath(this);

        // handling onclick event on button
        buttonDownload.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                // getting the text from edittext
                // and storing it to url variable
                String url = editTextUrl.getText().toString().trim();
                // setting the visibility of linear layout to visible
                details.setVisibility(View.VISIBLE);
                // calling method downloadFile passing url as parameter
                downloadFile(url);
            }
        });
    }

    @SuppressLint("SetTextI18n")
    private void downloadFile(final String url) {

        // handing click event on start button
        // which starts the downloading of the file
        btnStart.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

                // checks if the process is already running
                if (Status.RUNNING == PRDownloader.getStatus(downloadID)) {
                    // pauses the download if 
                    // user click on pause button
                    PRDownloader.pause(downloadID);
                    return;
                }

                // enabling the start button
                btnStart.setEnabled(false);

                // checks if the status is paused
                if (Status.PAUSED == PRDownloader.getStatus(downloadID)) {
                    // resume the download if download is paused
                    PRDownloader.resume(downloadID);
                    return;
                }

                // getting the filename
                String fileName = URLUtil.guessFileName(url, null, null);

                // setting the file name
                file_name.setText("Downloading " + fileName);

                // making the download request
                downloadID = PRDownloader.download(url, path, fileName)
                        .build()
                        .setOnStartOrResumeListener(new OnStartOrResumeListener() {
                            @SuppressLint("SetTextI18n")
                            @Override
                            public void onStartOrResume() {
                                progressBar.setIndeterminate(false);
                                // enables the start button
                                btnStart.setEnabled(true);
                                // setting the text of start button to pause
                                btnStart.setText("Pause");
                                // enabling the stop button
                                btnCancel.setEnabled(true);
                                Toast.makeText(MainActivity.this, "Downloading started", Toast.LENGTH_SHORT).show();
                            }
                        })
                        .setOnPauseListener(new OnPauseListener() {
                            @Override
                            public void onPause() {
                                // setting the text of start button to resume
                                // when the download is in paused state
                                btnStart.setText("Resume");
                                Toast.makeText(MainActivity.this, "Downloading Paused", Toast.LENGTH_SHORT).show();
                            }
                        })
                        .setOnCancelListener(new OnCancelListener() {
                            @Override
                            public void onCancel() {
                                // resetting the downloadId when 
                                // the download is cancelled
                                downloadID = 0;
                                // setting the text of start button to start
                                btnStart.setText("Start");
                                // disabling the cancel button
                                btnCancel.setEnabled(false);
                                // resetting the progress bar
                                progressBar.setProgress(0);
                                // restting the download precent
                                downloading_percent.setText("");
                                progressBar.setIndeterminate(false);
                                Toast.makeText(MainActivity.this, "Downloading Cancelled", Toast.LENGTH_SHORT).show();
                            }
                        })
                        .setOnProgressListener(new OnProgressListener() {
                            @Override
                            public void onProgress(Progress progress) {
                                // getting the progress of download
                                long progressPer = progress.currentBytes * 100 / progress.totalBytes;
                                // setting the progress to progressbar
                                progressBar.setProgress((int) progressPer);
                                // setting the download percent
                                downloading_percent.setText(Utils.getProgressDisplayLine(progress.currentBytes, progress.totalBytes));
                                progressBar.setIndeterminate(false);
                            }
                        })
                        .start(new OnDownloadListener() {

                            @Override
                            public void onDownloadComplete() {
                                // disabling the start button
                                btnStart.setEnabled(false);
                                // disabling the cancel button
                                btnCancel.setEnabled(false);
                                // setting the text completed to start button
                                btnStart.setText("Completed");
                                // will show the path after the file is downloaded
                                file_downloaded_path.setText("File stored at : " + path);
                                Toast.makeText(MainActivity.this, "Downloading Completed", Toast.LENGTH_SHORT).show();
                            }

                            @Override
                            public void onError(Error error) {
                                // setting the text start
                                btnStart.setText("Start");
                                // resetting the download percentage
                                downloading_percent.setText("0");
                                // resetting the progressbar
                                progressBar.setProgress(0);
                                // resetting the downloadID
                                downloadID = 0;
                                // enabling the start button
                                btnStart.setEnabled(true);
                                // disabling the cancel button
                                btnCancel.setEnabled(false);
                                progressBar.setIndeterminate(false);
                                Toast.makeText(MainActivity.this, "Error Occurred", Toast.LENGTH_SHORT).show();
                            }
                        });

                // handling click event on cancel button
                btnCancel.setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View view) {
                        btnStart.setText("Start");
                        // cancels the download
                        PRDownloader.cancel(downloadID);
                    }
                });
            }
        });
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-644511-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210710182504/1625920841669.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210710182504/1625920841669.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210710182504/1625920841669.mp4)</video>