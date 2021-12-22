# 如何在 Android 中使用凌空更新 API 中的数据？

> 原文:[https://www . geeksforgeeks . org/如何使用安卓截击更新 api 中的数据/](https://www.geeksforgeeks.org/how-to-update-data-in-api-using-volley-in-android/)

**先决条件**:

*   [使用凌空库](https://www.geeksforgeeks.org/json-parsing-in-android-using-volley-library/) 解析安卓系统中的 JSON
*   [如何在安卓中使用凌空将数据发布到 API？T3】](https://www.geeksforgeeks.org/how-to-post-data-to-api-using-volley-in-android/)

我们已经看到[从 API 读取](https://www.geeksforgeeks.org/json-parsing-in-android-using-volley-library/)数据，以及[在 API 的帮助下将](https://www.geeksforgeeks.org/how-to-post-data-to-api-using-volley-in-android/)数据发布到我们的数据库。在本文中，我们将看看如何在我们的 API 中更新数据。我们将使用[截击](https://www.geeksforgeeks.org/volley-library-in-android/)库来更新我们的应用编程接口中的数据。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，在其中我们将显示一个简单的表单，通过该表单，我们将更新我们的数据，并将其传递给我们的应用编程接口来更新该数据。我们将使用 **PUT** 请求以及凌空库来更新我们的数据到应用编程接口。下面给出了一个视频样本来了解一下我们将在本文中做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-564264-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210221135113/Screenrecorder-2021-02-21-13-48-49-620.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210221135113/Screenrecorder-2021-02-21-13-48-49-620.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210221135113/Screenrecorder-2021-02-21-13-48-49-620.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在你的 build.gradle 文件**中添加下面的依赖项

下面是凌空的依赖，我们将使用它从应用编程接口获取数据。要添加此依赖项，请导航至**应用程序>渐变脚本> build.gradle(应用程序)**，并在依赖项部分添加以下依赖项。

> //下方线用于截击库
> 
> 实现‘com . Android .凌空:凌空:1 . 1 . 1’

添加此依赖项后，同步您的项目，现在转到 AndroidManifest.xml 部分。

**第三步:在 AndroidManifest.xml 文件**中添加互联网权限

导航到**应用程序> AndroidManifest.xml** ，并添加以下代码。

## 可扩展标记语言

```
<uses-permission android:name="android.permission.INTERNET"/>
```

**第 4 步:使用 activity_main.xml 文件**

导航到 **app > res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是**activity _ main . XML**文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<!--in this we are displaying a nested scroll view-->
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <!--edit text for our user name-->
    <EditText
        android:id="@+id/idEdtUserName"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="30dp"
        android:layout_marginEnd="10dp"
        android:hint="User Name" />

    <!--edit text for our job-->
    <EditText
        android:id="@+id/idEdtJob"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:hint="Job" />

    <!--button to update our data-->
    <Button
        android:id="@+id/idBtnUpdate"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="20dp"
        android:text="Update Data"
        android:textAllCaps="false" />

    <!--progress bar for the purpose of loading-->
    <ProgressBar
        android:id="@+id/idPBLoading"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:visibility="gone" />

    <!--text view to display our 
        response after updating data-->
    <TextView
        android:id="@+id/idTVResponse"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:gravity="center_horizontal"
        android:text="Response"
        android:textAlignment="center"
        android:textColor="@color/black"
        android:textSize="15sp" />

</LinearLayout>
```

**第五步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.os.Bundle;
import android.text.TextUtils;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.ProgressBar;
import android.widget.TextView;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

import com.android.volley.Request;
import com.android.volley.RequestQueue;
import com.android.volley.Response;
import com.android.volley.VolleyError;
import com.android.volley.toolbox.StringRequest;
import com.android.volley.toolbox.Volley;

import org.json.JSONException;
import org.json.JSONObject;

import java.util.HashMap;
import java.util.Map;

public class MainActivity extends AppCompatActivity {

    // creating our variables for our views such as
    // text view, button and progress bar
    // and response text view.
    private EditText userNameEdt, jobEdt;
    private Button updateBtn;
    private ProgressBar loadingPB;
    private TextView responseTV;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initializing our views with their ids.
        userNameEdt = findViewById(R.id.idEdtUserName);
        jobEdt = findViewById(R.id.idEdtJob);
        updateBtn = findViewById(R.id.idBtnUpdate);
        loadingPB = findViewById(R.id.idPBLoading);
        responseTV = findViewById(R.id.idTVResponse);

        // adding on click listener for our button.
        updateBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // checking if the edit text is empty or not.
                if (TextUtils.isEmpty(userNameEdt.getText().toString()) && TextUtils.isEmpty(jobEdt.getText().toString())) {
                    // displaying a toast message if the edit text is empty.
                    Toast.makeText(MainActivity.this, "Please enter your data..", Toast.LENGTH_SHORT).show();
                    return;
                }
                // calling a method to update data in our API.
                callPUTDataMethod(userNameEdt.getText().toString(), jobEdt.getText().toString());
            }
        });
    }

    private void callPUTDataMethod(String name, String job) {

        // making our progress bar visible.
        loadingPB.setVisibility(View.VISIBLE);

        // url for updating our data
        // in below url 2 is the identity at which 
        // we will be updating our data.
        String url = "https://reqres.in/api/users/2";

        // creating a new variable for our request queue
        RequestQueue queue = Volley.newRequestQueue(MainActivity.this);

        // making a string request to update our data and 
        // passing method as PUT. to update our data.
        StringRequest request = new StringRequest(Request.Method.PUT, url, new Response.Listener<String>() {
            @Override
            public void onResponse(String response) {

                // hiding our progress bar.
                loadingPB.setVisibility(View.GONE);

                // inside on response method we are
                // setting our edit text to empty.
                jobEdt.setText("");
                userNameEdt.setText("");

                // on below line we are displaying a toast message as data updated.
                Toast.makeText(MainActivity.this, "Data Updated..", Toast.LENGTH_SHORT).show();
                try {
                    // on below line we are extracting data from our json object
                    // and passing our response to our json object.
                    JSONObject jsonObject = new JSONObject(response);

                    // creating a string for our output.
                    String output = jsonObject.getString("name") + "\n" + jsonObject.getString("job") + "\n" + jsonObject.getString("updatedAt");

                    // on below line we are setting 
                    // our string to our text view.
                    responseTV.setText(output);
                } catch (JSONException e) {
                    e.printStackTrace();
                }
            }
        }, new Response.ErrorListener() {
            @Override
            public void onErrorResponse(VolleyError error) {
                // displaying toast message on response failure.
                Toast.makeText(MainActivity.this, "Fail to update data..", Toast.LENGTH_SHORT).show();
            }
        }) {
            @Override
            protected Map<String, String> getParams() {

                // below line we are creating a map for storing
                // our values in key and value pair.
                Map<String, String> params = new HashMap<String, String>();

                // on below line we are passing our key
                // and value pair to our parameters.
                params.put("name", name);
                params.put("job", job);

                // at last we are 
                // returning our params.
                return params;
            }
        };
        // below line is to make 
        // a json object request.
        queue.add(request);
    }
}
```

现在运行您的应用程序，并查看应用程序的输出。

### **输出:**

<video class="wp-video-shortcode" id="video-564264-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210221135113/Screenrecorder-2021-02-21-13-48-49-620.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210221135113/Screenrecorder-2021-02-21-13-48-49-620.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210221135113/Screenrecorder-2021-02-21-13-48-49-620.mp4)</video>