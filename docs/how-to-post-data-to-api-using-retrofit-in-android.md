# 如何在安卓中使用改装将数据发布到 API？

> 原文:[https://www . geeksforgeeks . org/如何在安卓中使用改装将数据发布到 API/](https://www.geeksforgeeks.org/how-to-post-data-to-api-using-retrofit-in-android/)

我们已经在安卓工作室看到了从我们的安卓应用中的应用编程接口读取数据。为了从应用编程接口读取数据，我们使用 **GET** 请求来读取我们的数据，该数据为 **JSON 格式**。在本文中，我们将了解如何在安卓工作室的安卓应用中向 REST 应用编程接口添加数据。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将使用[改装库](https://www.geeksforgeeks.org/introduction-retofit-2-android-set-1/)和 **POST** 请求向我们的 REST API 添加数据。我们将通过编辑文本字段添加数据，并通过响应代码验证我们的数据是否已添加到应用编程接口中。当我们将数据添加到我们的 API 中时，我们将看到 201 是一个响应代码。201 响应代码意味着数据已经添加到我们的 API 中。下面给出了一个示例视频，以了解我们将在本文中做什么。请注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-561060-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210213232908/Screenrecorder-2021-02-13-22-55-39-932.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210213232908/Screenrecorder-2021-02-13-22-55-39-932.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210213232908/Screenrecorder-2021-02-13-22-55-39-932.mp4)</video>

数据可以通过 [XML](https://www.geeksforgeeks.org/xml-basics/) 表单、 [JSON](https://www.geeksforgeeks.org/javascript-json/) 等不同格式添加到 API 中。大多数应用编程接口都以 JSON 格式发布数据。因此，我们也将以 JSON 对象的形式将数据发布到我们的应用编程接口。

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在你的 build.gradle 文件**中添加下面的依赖项

导航到**渐变脚本>构建.渐变(模块:应用)**，并在依赖项部分添加以下依赖项。

> //下面是使用改装的依赖关系
> 
> 实现“com.squareup.retrofit2:改装:2.9.0”
> 
> 实现' com . squareup . retro fit 2:converter-gson:2 . 5 . 0 '

添加这个依赖项后，同步你的项目，现在进入 **AndroidManifest.xml** 部分。

**第三步:在 AndroidManifest.xml 文件**中添加互联网权限

导航到**应用程序> AndroidManifest.xml** ，并添加以下代码。

## 可扩展标记语言

```
<!--permissions for INTERNET-->
<uses-permission android:name="android.permission.INTERNET"/>
```

**第 4 步:使用 activity_main.xml 文件**

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

    <!--edit text field for adding name-->
    <EditText
        android:id="@+id/idEdtName"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:layout_marginTop="40dp"
        android:hint="Enter your name" />

    <!--edit text for adding job-->
    <EditText
        android:id="@+id/idEdtJob"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:hint="Enter your job" />

    <!--button for adding data-->
    <Button
        android:id="@+id/idBtnPost"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="20dp"
        android:text="Send Data to API"
        android:textAllCaps="false" />

    <!--text view for displaying our API response-->
    <TextView
        android:id="@+id/idTVResponse"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:gravity="center_horizontal"
        android:text="Response"
        android:textAlignment="center"
        android:textSize="15sp" />

    <!--progress bar for loading -->
    <ProgressBar
        android:id="@+id/idLoadingPB"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:visibility="gone" />

</LinearLayout>
```

**第五步:创建一个模态类来存储我们的数据**

导航到**应用> java >你的应用的包名>右键点击它>新建> Java 类**并将其命名为 **DataModal** 并添加下面的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class DataModal {

    // string variables for our name and job
    private String name;
    private String job;

    public DataModal(String name, String job) {
        this.name = name;
        this.job = job;
    }

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

导航到**应用> java >你的应用的包名>右键点击>新建> Java 类**选择为**界面**并将文件命名为**retriefitapi**并添加下面的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import retrofit2.Call;
import retrofit2.http.Body;
import retrofit2.http.POST;

public interface RetrofitAPI {

    // as we are making a post request to post a data
    // so we are annotating it with post
    // and along with that we are passing a parameter as users
    @POST("users")

    //on below line we are creating a method to post our data.
    Call<DataModal> createPost(@Body DataModal dataModal);
}
```

**第 7 步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.os.Bundle;
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

    // creating variables for our edittext, 
    // button, textview and progressbar.
    private EditText nameEdt, jobEdt;
    private Button postDataBtn;
    private TextView responseTV;
    private ProgressBar loadingPB;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initializing our views
        nameEdt = findViewById(R.id.idEdtName);
        jobEdt = findViewById(R.id.idEdtJob);
        postDataBtn = findViewById(R.id.idBtnPost);
        responseTV = findViewById(R.id.idTVResponse);
        loadingPB = findViewById(R.id.idLoadingPB);

        // adding on click listener to our button.
        postDataBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // validating if the text field is empty or not.
                if (nameEdt.getText().toString().isEmpty() && jobEdt.getText().toString().isEmpty()) {
                    Toast.makeText(MainActivity.this, "Please enter both the values", Toast.LENGTH_SHORT).show();
                    return;
                }
                // calling a method to post the data and passing our name and job.
                postData(nameEdt.getText().toString(), jobEdt.getText().toString());
            }
        });
    }

    private void postData(String name, String job) {

        // below line is for displaying our progress bar.
        loadingPB.setVisibility(View.VISIBLE);

        // on below line we are creating a retrofit 
        // builder and passing our base url
        Retrofit retrofit = new Retrofit.Builder()
                .baseUrl("https://reqres.in/api/")
                // as we are sending data in json format so 
                // we have to add Gson converter factory
                .addConverterFactory(GsonConverterFactory.create())
                // at last we are building our retrofit builder.
                .build();
        // below line is to create an instance for our retrofit api class.
        RetrofitAPI retrofitAPI = retrofit.create(RetrofitAPI.class);

        // passing data from our text fields to our modal class.
        DataModal modal = new DataModal(name, job);

        // calling a method to create a post and passing our modal class.
        Call<DataModal> call = retrofitAPI.createPost(modal);

        // on below line we are executing our method.
        call.enqueue(new Callback<DataModal>() {
            @Override
            public void onResponse(Call<DataModal> call, Response<DataModal> response) {
                // this method is called when we get response from our api.
                Toast.makeText(MainActivity.this, "Data added to API", Toast.LENGTH_SHORT).show();

                // below line is for hiding our progress bar.
                loadingPB.setVisibility(View.GONE);

                // on below line we are setting empty text
                // to our both edit text.
                jobEdt.setText("");
                nameEdt.setText("");

                // we are getting response from our body 
                // and passing it to our modal class.
                DataModal responseFromAPI = response.body();

                // on below line we are getting our data from modal class and adding it to our string.
                String responseString = "Response Code : " + response.code() + "\nName : " + responseFromAPI.getName() + "\n" + "Job : " + responseFromAPI.getJob();

                // below line we are setting our 
                // string to our text view.
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

### **输出:**

<video class="wp-video-shortcode" id="video-561060-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210213232908/Screenrecorder-2021-02-13-22-55-39-932.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210213232908/Screenrecorder-2021-02-13-22-55-39-932.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210213232908/Screenrecorder-2021-02-13-22-55-39-932.mp4)</video>