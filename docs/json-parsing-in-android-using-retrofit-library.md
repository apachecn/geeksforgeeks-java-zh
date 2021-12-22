# 使用改装库

解析安卓系统中的 JSON

> 原文:[https://www . geesforgeks . org/JSON-Android 中解析-使用-改装-库/](https://www.geeksforgeeks.org/json-parsing-in-android-using-retrofit-library/)

[JSON 也称为(JavaScript 对象符号)](https://www.geeksforgeeks.org/javascript-json/)是一种从服务器交换数据的格式。以 JSON 格式存储的数据是轻量级的，易于处理。在 JSON 的帮助下，我们可以以 JsonArray、JsonObject 和 JsonStringer 的形式访问数据。在本文中，我们将具体研究一下在安卓系统中使用[改装库](https://www.geeksforgeeks.org/introduction-retofit-2-android-set-1/)实现 JsonObject。

> **注意:**使用 **Voley** 库解析安卓系统中的 JSON 对象请参考[使用凌空库](https://www.geeksforgeeks.org/json-parsing-in-android-using-volley-library/)解析安卓系统中的 JSON

> **JSON 对象**:用“{”大括号开头，用“}”大括号结尾，可以很容易的识别出 JSON 对象。我们可以从带有键值的 JSON 对象中获取数据。从那个键，我们可以访问那个键的值。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，在其中我们将显示一个简单的[卡片视图](https://www.geeksforgeeks.org/cardview-in-android-with-example/)，在其中我们将显示一个在极客上为极客提供的单一课程。下面给出了一个示例视频，以了解我们将在本文中做什么。请注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-559412-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210217150427/Screenrecorder-2021-01-21-21-39-44-445.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210217150427/Screenrecorder-2021-01-21-21-39-44-445.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210217150427/Screenrecorder-2021-01-21-21-39-44-445.mp4)</video>

下面是 JSON 对象，我们将从该对象在我们的安卓应用程序中显示数据。

> {
> 
> "库尔塞纳姆":" Fork CPP "，
> 
> “course img”:“https://media . geeksforgeeks . org/img-practice/banner/fork-CPP-thumbnail . png”，
> 
> “课程模式”:“在线批处理”，
> 
> “课程曲目”:“6 首曲目”
> 
> }

### **分步实施**

**第一步:创建新项目**

在安卓工作室创建新项目请参考 [<u>【如何在安卓工作室创建/启动新项目】</u>](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/) 。注意选择 **Java** 作为编程语言。

**第二步:在你的 build.gradle 文件**中添加下面的依赖项

下面是凌空的依赖，我们将使用它从应用编程接口获取数据。要添加此依赖项，请导航至**应用程序>渐变脚本> build.gradle(应用程序)**，并在依赖项部分添加以下依赖项。我们已经使用了[毕加索](https://www.geeksforgeeks.org/how-to-use-picasso-image-loader-library-in-android/)依赖从网址加载图像。

> //下面是使用改装的依赖项。
> 
> 实现“com.squareup.retrofit2:改装:2.9.0”
> 
> 实现' com . squareup . retro fit 2:converter-gson:2 . 5 . 0 '
> 
> //下面是使用毕加索图像加载库的依赖项
> 
> 实现' com.squareup .毕加索:毕加索:2.71828 '

添加这个依赖项后，同步你的项目，现在进入 **AndroidManifest.xml** 部分。

**第三步:在 AndroidManifest.xml 文件**中添加互联网权限

导航到**应用程序> AndroidManifest.xml** ，并添加以下代码。

## 可扩展标记语言

```java
<!--permissions for INTERNET-->
<uses-permission android:name="android.permission.INTERNET"/>
```

**第 4 步:使用 activity_main.xml 文件**

导航到 **app > res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是**activity _ main . XML**文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:layout_gravity="center"
    android:gravity="center"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <androidx.cardview.widget.CardView
        android:id="@+id/idCVCourse"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:elevation="10dp"
        android:visibility="gone"
        app:cardCornerRadius="8dp">

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="vertical">

            <ImageView
                android:id="@+id/idIVCourse"
                android:layout_width="match_parent"
                android:layout_height="300dp"
                android:layout_margin="5dp" />

            <TextView
                android:id="@+id/idTVCourseName"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_margin="5dp"
                android:padding="5dp"
                android:text="Course Name "
                android:textColor="@color/black"
                android:textSize="18sp"
                android:textStyle="bold" />

            <LinearLayout
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:layout_margin="5dp"
                android:orientation="horizontal"
                android:weightSum="2">

                <TextView
                    android:id="@+id/idTVBatch"
                    android:layout_width="0dp"
                    android:layout_height="wrap_content"
                    android:layout_weight="1"
                    android:padding="5dp"
                    android:text="Batch"
                    android:textColor="@color/black" />

                <TextView
                    android:id="@+id/idTVTracks"
                    android:layout_width="0dp"
                    android:layout_height="wrap_content"
                    android:layout_weight="1"
                    android:padding="5dp"
                    android:text="Tracks"
                    android:textColor="@color/black" />

            </LinearLayout>

        </LinearLayout>

    </androidx.cardview.widget.CardView>

    <ProgressBar
        android:id="@+id/idLoadingPB"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:visibility="visible" />

</RelativeLayout>
```

**第五步:创建一个模态类来存储我们的数据**

导航到**应用程序> java >你的应用程序的包名>右键点击它>新建> Java 类**并将其命名为 **RecyclerData** 并添加下面的代码。在代码中添加注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
public class RecyclerData {
    // string variables for our data
    // make sure that the variable name 
    // must be similar to that of key value 
    // which we are getting from our json file.
    private String courseName;
    private String courseimg;
    private String courseMode;
    private String courseTracks;

    public String getCourseName() {
        return courseName;
    }

    public void setCourseName(String courseName) {
        this.courseName = courseName;
    }

    public String getCourseimg() {
        return courseimg;
    }

    public void setCourseimg(String courseimg) {
        this.courseimg = courseimg;
    }

    public String getCourseMode() {
        return courseMode;
    }

    public void setCourseMode(String courseMode) {
        this.courseMode = courseMode;
    }

    public String getCourseTracks() {
        return courseTracks;
    }

    public void setCourseTracks(String courseTracks) {
        this.courseTracks = courseTracks;
    }

    public RecyclerData(String courseName, String courseimg, String courseMode, String courseTracks) {
        this.courseName = courseName;
        this.courseimg = courseimg;
        this.courseMode = courseMode;
        this.courseTracks = courseTracks;
    }
}
```

**第 6 步:为我们的 API 调用创建一个接口类**

导航到**应用> java >你的应用的包名>右键点击>新建> Java 类**选择为**界面**并将文件命名为**retriefitapi**并添加下面的代码。在代码内部添加注释，更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import retrofit2.Call;
import retrofit2.http.GET;

public interface RetrofitAPI {

    // as we are making get request 
    // so we are displaying GET as annotation.
    // and inside we are passing 
    // last parameter for our url.
    @GET("63OH")

    // as we are calling data from array
    // so we are calling it with json object
    // and naming that method as getCourse();
    Call<RecyclerData> getCourse();
}
```

**第 7 步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.os.Bundle;
import android.view.View;
import android.widget.ImageView;
import android.widget.ProgressBar;
import android.widget.TextView;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;
import androidx.cardview.widget.CardView;

import com.squareup.picasso.Picasso;

import retrofit2.Call;
import retrofit2.Callback;
import retrofit2.Response;
import retrofit2.Retrofit;
import retrofit2.converter.gson.GsonConverterFactory;

public class MainActivity extends AppCompatActivity {
    // creating variables for our textview,
    // imageview,cardview and progressbar.
    private TextView courseNameTV, courseTracksTV, courseBatchTV;
    private ImageView courseIV;
    private ProgressBar loadingPB;
    private CardView courseCV;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initializing our variables.
        loadingPB = findViewById(R.id.idLoadingPB);
        courseCV = findViewById(R.id.idCVCourse);
        courseNameTV = findViewById(R.id.idTVCourseName);
        courseTracksTV = findViewById(R.id.idTVTracks);
        courseBatchTV = findViewById(R.id.idTVBatch);
        courseIV = findViewById(R.id.idIVCourse);
        getCourse();
    }

    private void getCourse() {

        // on below line we are creating a retrofit
        // builder and passing our base url
        Retrofit retrofit = new Retrofit.Builder()
                .baseUrl("https://jsonkeeper.com/b/")
                // on below line we are calling add Converter
                // factory as GSON converter factory.
                .addConverterFactory(GsonConverterFactory.create())
                // at last we are building our retrofit builder.
                .build();
        // below line is to create an instance for our retrofit api class.
        RetrofitAPI retrofitAPI = retrofit.create(RetrofitAPI.class);
        Call<RecyclerData> call = retrofitAPI.getCourse();
        call.enqueue(new Callback<RecyclerData>() {
            @Override
            public void onResponse(Call<RecyclerData> call, Response<RecyclerData> response) {
                if (response.isSuccessful()) {
                    // inside the on response method.
                    // we are hiding our progress bar.
                    loadingPB.setVisibility(View.GONE);
                    // in below line we are making our card
                    // view visible after we get all the data.
                    courseCV.setVisibility(View.VISIBLE);
                    RecyclerData modal = response.body();
                    // after extracting all the data we are
                    // setting that data to all our views.
                    courseNameTV.setText(modal.getCourseName());
                    courseTracksTV.setText(modal.getCourseTracks());
                    courseBatchTV.setText(modal.getCourseMode());
                    // we are using picasso to load the image from url.
                    Picasso.get().load(modal.getCourseimg()).into(courseIV);
                }
            }

            @Override
            public void onFailure(Call<RecyclerData> call, Throwable t) {
                // displaying an error message in toast
                Toast.makeText(MainActivity.this, "Fail to get the data..", Toast.LENGTH_SHORT).show();
            }
        });
    }
}
```

现在运行您的应用程序，并查看应用程序的输出。

### **输出:**

<video class="wp-video-shortcode" id="video-559412-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210217150427/Screenrecorder-2021-01-21-21-39-44-445.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210217150427/Screenrecorder-2021-01-21-21-39-44-445.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210217150427/Screenrecorder-2021-01-21-21-39-44-445.mp4)</video>