# 如何在安卓中添加 YouTube 直播流功能？

> 原文:[https://www . geesforgeks . org/how-add-YouTube-live-stream-in-Android-feature/](https://www.geeksforgeeks.org/how-to-add-youtube-live-stream-feature-in-android/)

YouTube 提供了一项服务，可以在他们的平台上制作直播视频，与您的订阅者联系。在本文中，我们将了解一下 YouTube 视频直播视频在 Android App 中的实现。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将显示一个简单的按钮，点击该按钮，我们将在 YouTube 上进行直播。下面给出一个视频样本，了解一下在本文中我们要做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-569697-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210305175514/Screenrecorder-2021-03-05-17-53-22-618.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210305175514/Screenrecorder-2021-03-05-17-53-22-618.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210305175514/Screenrecorder-2021-03-05-17-53-22-618.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<!--in this we are displaying a nested scroll view-->
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/idNestedSV"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--button for starting youtube livestream video-->
    <Button
        android:id="@+id/idBtnStartLiveStream"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:text="Start Youtube Live Stream"
        android:textAllCaps="false" />

</RelativeLayout>
```

**第三步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.Context;
import android.content.Intent;
import android.content.pm.PackageManager;
import android.net.Uri;
import android.os.Bundle;
import android.text.TextUtils;
import android.view.View;
import android.widget.Button;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

import java.util.List;

public class MainActivity extends AppCompatActivity {
    // creating a variable for button
    // to start youtube live stream
    private Button startBtn;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // adding on click listener to our button.
        startBtn = findViewById(R.id.idBtnStartLiveStream);
        startBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // calling a method to check if the device has
                // support to make youtube live stream or not.
                validateMobileLiveIntent(MainActivity.this);
            }
        });
    }

    private boolean canResolveMobileLiveIntent(Context context) {
        // in this method we are calling a youtube live  intent package name
        // and we are checking if youtube live intent is present or not.
        Intent intent = new Intent("com.google.android.youtube.intent.action.CREATE_LIVE_STREAM").setPackage("com.google.android.youtube");
        PackageManager pm = context.getPackageManager();
        List resolveInfo = pm.queryIntentActivities(intent, PackageManager.MATCH_DEFAULT_ONLY);

        // returning the result after checking
        // the youtube live stream intent.
        return resolveInfo != null && !resolveInfo.isEmpty();
    }

    private void validateMobileLiveIntent(Context context) {
        if (canResolveMobileLiveIntent(context)) {
            // Launch the live stream Activity
            startMobileLive(MainActivity.this);
        } else {
            // on below line displaying a toast message if the intent is not present.
            Toast.makeText(context, "Please Update your Youtube app.", Toast.LENGTH_SHORT).show();
            // Prompt user to install or upgrade the YouTube app
        }
    }

    // method to create our intent for youtube live stream.
    private Intent createMobileLiveIntent(Context context, String description) {

        // on below line we are creating a new intent and we are setting package name to it.
        Intent intent = new Intent("com.google.android.youtube.intent.action.CREATE_LIVE_STREAM").setPackage("com.google.android.youtube");

        // on below line we are creating a new uri and setting
        // a scheme to it and appending our path with our package name.
        Uri referrer = new Uri.Builder()
                .scheme("android-app")
                .appendPath(context.getPackageName())
                .build();
        // on above line we are building our intent.
        // on below line we are adding our referer
        // and subject for our live video.
        intent.putExtra(Intent.EXTRA_REFERRER, referrer);
        if (!TextUtils.isEmpty(description)) {
            intent.putExtra(Intent.EXTRA_SUBJECT, description);
        }
        // at last we are returning intent.
        return intent;
    }

    private void startMobileLive(Context context) {

        // calling a method to create an intent.
        Intent mobileLiveIntent = createMobileLiveIntent(context, "Streaming via ...");

        // on below line we are calling
        // our activity to start stream
        startActivity(mobileLiveIntent);
    }
}
```

现在运行您的应用程序，并查看应用程序的输出。

### **输出:**

<video class="wp-video-shortcode" id="video-569697-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210305175514/Screenrecorder-2021-03-05-17-53-22-618.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210305175514/Screenrecorder-2021-03-05-17-53-22-618.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210305175514/Screenrecorder-2021-03-05-17-53-22-618.mp4)</video>