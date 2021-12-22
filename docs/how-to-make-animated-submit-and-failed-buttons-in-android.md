# 如何在安卓中制作动画提交和失败按钮？

> 原文:[https://www . geeksforgeeks . org/如何在安卓中制作动画提交和失败按钮/](https://www.geeksforgeeks.org/how-to-make-animated-submit-and-failed-buttons-in-android/)

在安卓应用中，[按钮](https://www.geeksforgeeks.org/handling-click-events-button-android/)是一个用户界面，用于在点击或轻击时执行一些动作。它是安卓系统中非常常见的小部件，开发者经常使用。本文演示了如何在安卓工作室中创建动画提交和失败按钮。

### 我们将在本文中构建什么？

在本文中，我们将开发一个示例应用程序，在其主活动中包含一些按钮。使用按钮的点击事件，我们将看到这些按钮上的动画。下面给出了一个示例视频，以了解我们将在本文中做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-586787-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210408001751/gfg_buttons_android.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210408001751/gfg_buttons_android.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210408001751/gfg_buttons_android.mp4)</video>

### 逐步实施

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:添加依赖关系**

现在，导航到**渐变脚本>构建.渐变(模块:应用)**在依赖项部分添加下面的依赖项。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
implementation 'me.spark:submitbutton:1.0.1'
implementation 'com.unstoppable:submitbutton:1.1.3'
```

现在，同步您的项目，现在我们拥有了实施过程中所需的一切，现在，开始实施吧。

**步骤 3:使用 activity_main.xml 文件**

现在是时候设计应用程序的布局了。为此，转到**应用程序> res >布局> activity_main.xml** 并将下面编写的代码粘贴到 **activity_main.xml** 文件中。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:id="@+id/relative_layout"
    tools:context=".MainActivity"
    android:orientation="vertical"
    >

    <!--creation of first type submit button that is 
        unique_check_button which is located at the top-->
    <com.spark.submitbutton.SubmitButton
        android:id="@+id/unique_check_button"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:layout_marginTop="120dp"
        android:layout_centerHorizontal="true"
        android:text="Click Me"
        android:textColor="#131212"
        app:sub_btn_background="@color/white"
        app:sub_btn_duration="3000"
        app:sub_btn_line_color="#0F9D58"
        app:sub_btn_ripple_color="#0F9D58"
        app:sub_btn_tick_color="@color/white" />

    <!--creation of a common loading button which 
        will show two different events submit or failed -->
    <com.unstoppable.submitbuttonview.SubmitButton
        android:id="@+id/sbtn_loading"
        android:layout_width="200dp"
        android:layout_height="50dp"
        android:layout_centerInParent="true"
        app:buttonText="Submit"
        app:buttonTextSize="25sp" />

    <!-- creation of progress button-->
    <com.unstoppable.submitbuttonview.SubmitButton
        android:id="@+id/sbtn_progress"
        android:layout_width="200dp"
        android:layout_height="50dp"
        android:layout_centerInParent="true"
        android:layout_marginTop="30dp"
        android:visibility="gone"
        app:buttonText="Submit"
        app:buttonTextSize="25sp"
        app:progressStyle="progress" />

    <!-- creation of normal succeed button-->
    <Button
        android:id="@+id/btn_succeed"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentBottom="true"
        android:layout_margin="10dp"
        android:text="succeed" />

    <!-- creation of normal failed button-->
    <Button
        android:id="@+id/btn_failed"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentBottom="true"
        android:layout_centerHorizontal="true"
        android:layout_margin="10dp"
        android:text="failed" />

    <!-- creation of normal reset button-->
    <Button
        android:id="@+id/btn_reset"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentBottom="true"
        android:layout_alignParentRight="true"
        android:layout_margin="10dp"
        android:text="reset" />

</RelativeLayout>
```

**步骤 4:使用 MainActivity.java 文件**

转到 **app > java >包名>MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import androidx.appcompat.app.AppCompatActivity;

import android.os.AsyncTask;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.Switch;
import android.widget.Toast;
import com.unstoppable.submitbuttonview.SubmitButton;

public class MainActivity extends AppCompatActivity implements View.OnClickListener {
    private SubmitButton sBtnLoading, sBtnProgress;
    private Button btnSucceed, btnFailed, btnReset;
    private Switch mSwitch;
    private MyTask task;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initialization of all buttons created in activity_main.xml 
          // file using findViewById()
        sBtnLoading = (SubmitButton) findViewById(R.id.sbtn_loading);
        sBtnProgress = (SubmitButton) findViewById(R.id.sbtn_progress);
        btnFailed = (Button) findViewById(R.id.btn_failed);
        btnSucceed = (Button) findViewById(R.id.btn_succeed);
        btnReset = (Button) findViewById(R.id.btn_reset);

        // apply setOnClickListener to all buttons
        sBtnLoading.setOnClickListener(this);
        sBtnProgress.setOnClickListener(this);
        btnSucceed.setOnClickListener(this);
        btnFailed.setOnClickListener(this);
        btnReset.setOnClickListener(this);

        // apply setOnResultEndListener to sBtnLoading button
        sBtnLoading.setOnResultEndListener(new SubmitButton.OnResultEndListener() {
            @Override
            public void onResultEnd() {
                // toast class use makeText method to show short time message in android
                Toast.makeText(MainActivity.this, "ResultEnd", Toast.LENGTH_SHORT).show();
            }
        });

    }

    // set onClick method to all buttons when the buttons 
    // get clicked left to the unique_check_button button
    // of activity_main.xml file
    @Override
    public void onClick(View v) {
        switch (v.getId()) {

            case R.id.sbtn_loading:

                // when btn_loading gets clicked then this section will run
                Toast.makeText(this, "SubmitButton is just clicked", Toast.LENGTH_SHORT).show();
                break;

            case R.id.sbtn_progress:

                // when btn_progress gets clicked then this section will run
                if (task == null || task.isCancelled()) {
                    task = new MyTask();
                    task.execute();
                }
                break;

            case R.id.btn_succeed:

                    // when btn_succeed gets clicked then this section will run
                    sBtnLoading.doResult(true);

                break;
            case R.id.btn_failed:

                    // when btn_failed gets clicked then this section will run
                    sBtnLoading.doResult(false);

                break;
            case R.id.btn_reset:

                    // when btn_reset gets clicked then this section will run
                    if (task != null && !task.isCancelled()) {
                        task.cancel(true);
                        sBtnProgress.reset();
                    }
                 else {
                    sBtnLoading.reset();
                }
                break;
        }
    }

    // creating new private MyTaskClass to perform background functioning
    private class MyTask extends AsyncTask<Void, Integer, Boolean> {

        // creation of method doInBackground()
        @Override
        protected Boolean doInBackground(Void... params) {
            int i = 0;
            while (i <= 100) {
                if (isCancelled()) {
                    return null;
                }
                try {
                    Thread.sleep(30);
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
                i++;
                publishProgress(i);
            }
            return true;
        }

        // creation of onPostExecute()
        @Override
        protected void onPostExecute(Boolean aBoolean) {
            if (aBoolean == null) {
                sBtnProgress.reset();
            }
            sBtnProgress.doResult(aBoolean);
        }

        // creation of onProgressUpdate()
        @Override
        protected void onProgressUpdate(Integer... values) {
            sBtnProgress.setProgress(values[0]);
        }
    }
}
```

仅此而已，现在应用程序已准备好安装在设备上。下面是应用程序的输出。

**输出:**

<video class="wp-video-shortcode" id="video-586787-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210408001751/gfg_buttons_android.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210408001751/gfg_buttons_android.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210408001751/gfg_buttons_android.mp4)</video>