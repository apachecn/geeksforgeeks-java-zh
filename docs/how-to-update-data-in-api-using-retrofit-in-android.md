# 如何在安卓中使用改装更新 API 中的数据？

> 原文:[https://www . geeksforgeeks . org/如何在安卓系统中使用 api 更新数据/](https://www.geeksforgeeks.org/how-to-update-data-in-api-using-retrofit-in-android/)

我们已经看到从应用编程接口读取数据，以及在应用编程接口的帮助下将数据发布到我们的数据库中。在本文中，我们将看看如何在我们的 API 中更新数据。我们将使用改装库来更新我们的应用编程接口中的数据。

### **本文我们要构建什么？**

我们将构建一个简单的应用程序，在其中我们将显示一个简单的表单，通过该表单，我们将更新我们的数据，并将其传递给我们的应用编程接口来更新该数据。我们将使用 PUT 请求和改装库来更新我们的数据到 API。下面给出了一个示例视频，以了解我们将在本文中做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-604421-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210510111917/20210510_111800.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210510111917/20210510_111800.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210510111917/20210510_111800.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在你的 build.gradle 文件**中添加下面的依赖项

下面是凌空的依赖，我们将使用它从应用编程接口获取数据。要添加此依赖项，请导航至**应用程序>渐变脚本> build.gradle(应用程序)**，并在依赖项部分添加以下依赖项。

```java
// below dependency for using retrofit.
implementation 'com.squareup.retrofit2:retrofit:2.9.0'
implementation 'com.squareup.retrofit2:converter-gson:2.5.0'
```

添加此依赖项后，同步您的项目，现在转到 AndroidManifest.xml 部分。

**第三步:在 AndroidManifest.xml 文件**中添加互联网权限

导航到**应用程序> AndroidManifest.xml** ，并添加以下代码。

## 可扩展标记语言

```java
<!--permissions for INTERNET-->
<uses-permission android:name="android.permission.INTERNET"/>
```

**第 4 步:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

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

    <!--text view to display our response after updating data-->
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

**第五步:创建一个模态类来存储我们的数据**

导航到**应用> java >你的应用的包名>右键点击它>新建> Java 类**并将其命名为 **DataModal** 并添加下面的代码。代码中添加了注释，以便更详细地了解。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
package com.gtappdevelopers.gfg;

public class DataModal {
    // string variables for name and job.
    private String name;
    private String job;

    public DataModal(String name, String job) {
        this.name = name;
        this.job = job;
    }

    // creating getter and setter methods.
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getJob() {
        return job;
    }

    public void setJob(String job) {
        this.job = job;
    }
}
```

**第 6 步:为我们的 API 调用创建一个接口类**

导航到**应用程序> java >你的应用程序的包名>右键单击它>新建> Java 类**选择它作为**retracfitapi**并添加下面的代码。代码中添加了注释，以便更详细地了解。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
package com.gtappdevelopers.gfg;

import retrofit2.Call;
import retrofit2.http.Body;
import retrofit2.http.PUT;

public interface RetrofitAPI {

    // as we are making a put request to update a data
      // so we are annotating it with put
    // and along with that we are passing a parameter as users
    @PUT("api/users/2")

    // on below line we are creating a method to put our data.
    Call<DataModal> updateData(@Body DataModal dataModal);
}
```

**第七步:使用 MainActivity.java 文件**

导航到**应用程序> java >你的应用程序的包名>MainActivity.java**文件，并添加下面的代码。代码中添加了注释，以便更详细地了解。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
package com.gtappdevelopers.gfg;

import android.os.Bundle;
import android.text.TextUtils;
import android.util.Log;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.ProgressBar;
import android.widget.TextView;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

import retrofit2.Call;
import retrofit2.Callback;
import retrofit2.Response;
import retrofit2.Retrofit;
import retrofit2.converter.gson.GsonConverterFactory;

public class MainActivity extends AppCompatActivity {

    String url = "https://reqres.in/";

    // creating our variables for our views such
    // as text view, button and progress
    // bar and response text view.
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

    private void callPUTDataMethod(String userName, String job) {

        // below line is for displaying our progress bar.
        loadingPB.setVisibility(View.VISIBLE);

        // on below line we are creating a retrofit
        // builder and passing our base url
        Retrofit retrofit = new Retrofit.Builder()
                .baseUrl(url)

                // as we are sending data in json format so
                // we have to add Gson converter factory
                .addConverterFactory(GsonConverterFactory.create())

                 // at last we are building our retrofit builder.
                .build();

        // below the line is to create an instance for our retrofit api class.
        RetrofitAPI retrofitAPI = retrofit.create(RetrofitAPI.class);

        // passing data from our text fields to our modal class.
        DataModal modal = new DataModal(userName, job);

        // calling a method to create an update and passing our modal class.
        Call<DataModal> call = retrofitAPI.updateData(modal);

        // on below line we are executing our method.
        call.enqueue(new Callback<DataModal>() {
            @Override
            public void onResponse(Call<DataModal> call, Response<DataModal> response) {
                // this method is called when we get response from our api.
                Toast.makeText(MainActivity.this, "Data updated to API", Toast.LENGTH_SHORT).show();

                // below line is for hiding our progress bar.
                loadingPB.setVisibility(View.GONE);

                // on below line we are setting empty
                // text to our both edit text.
                jobEdt.setText("");
                userNameEdt.setText("");

                // we are getting a response from our body and
                // passing it to our modal class.
                DataModal responseFromAPI = response.body();

                // on below line we are getting our data from modal class
                // and adding it to our string.
                String responseString = "Response Code : " + response.code() + "\nName : " + responseFromAPI.getName() + "\n" + "Job : " + responseFromAPI.getJob();

                // below line we are setting our string to our text view.
                responseTV.setText(responseString);
            }

            @Override
            public void onFailure(Call<DataModal> call, Throwable t) {

                // setting text to our text view when
                // we get error response from API.
                responseTV.setText("Error found is : " + t.getMessage());
            }
        });
    }
}
```

现在运行您的应用程序，并查看应用程序的输出。

**输出:**

<video class="wp-video-shortcode" id="video-604421-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210510111917/20210510_111800.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210510111917/20210510_111800.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210510111917/20210510_111800.mp4)</video>