# 如何使用改装库从安卓中的 JSON 数组中提取数据？

> 原文:[https://www . geeksforgeeks . org/如何从安卓阵列中提取数据-使用-改装-库/](https://www.geeksforgeeks.org/how-to-extract-data-from-json-array-in-android-using-retrofit-library/)

在上一篇关于[使用改装库](https://www.geeksforgeeks.org/json-parsing-in-android-using-retrofit-library/)在安卓中解析 JSON 的文章中，我们已经看到了如何在我们的安卓应用程序中从 JSON Object 获取数据，并在我们的应用程序中显示该 JSON Object。在本文中，我们将看看**如何从 JSON 数组中提取数据并在我们的应用程序中显示。**

> ***注:*** *To e* 使用凌空库从安卓 JSON 数组中提取数据请参考 [如何使用凌空库从安卓 JSON 数组中提取数据？](https://www.geeksforgeeks.org/how-to-extract-data-from-json-array-in-android-using-volley-library/)

> **JSON 数组** : JSON 数组是一个集合或称为数据集合，它保存多个具有相似数据类型的 JSON 对象。JSON 数组可以很容易地用“[”大括号开头和“]”大括号结尾来标识。一个 JSON 数组包含多个具有相似数据的 JSON 对象。每个 JSON 对象都以键和值对的形式存储数据。

### **本文我们要构建什么？**

我们将构建一个简单的应用程序，其中我们将显示一个列表[卡片视图](https://www.geeksforgeeks.org/cardview-in-android-with-example/)，其中我们将显示一些在极客上为极客提供的课程。下面给出了一个示例视频，以了解我们将在本文中做什么。请注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-559503-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210217154438/Screenrecorder-2021-01-24-13-21-47-357.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210217154438/Screenrecorder-2021-01-24-13-21-47-357.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210217154438/Screenrecorder-2021-01-24-13-21-47-357.mp4)</video>

下面是我们的 JSON 数组，我们将在我们的安卓应用程序中显示数据。

```
[
   {
      "courseName":"Fork CPP",
      "courseimg":"https://media.geeksforgeeks.org/img-practice/banner/fork-cpp-thumbnail.png",
      "courseMode":"Online Batch",
      "courseTracks":"6 Tracks"
   },
   {
      "courseName":"Linux & Shell Scripting Foundation",
      "courseimg":"https://media.geeksforgeeks.org/img-practice/banner/linux-shell-scripting-thumbnail.png",
      "courseMode":"Online Batch",
      "courseTracks":"8 Tracks"
   },
   {
      "courseName":"11 Weeks Workshop on Data Structures and Algorithms",
      "courseimg":"https://media.geeksforgeeks.org/img-practice/banner/Workshop-DSA-thumbnail.png",
      "courseMode":"Online Batch",
      "courseTracks":"47 Tracks"
   },
   {
      "courseName":"Data Structures and Algorithms",
      "courseimg":"https://media.geeksforgeeks.org/img-practice/banner/dsa-self-paced-thumbnail.png",
      "courseMode":"Online Batch",
      "courseTracks":"24 Tracks"
   }
]
```

### **分步实施**

**第一步:创建新项目**

在安卓工作室创建新项目请参考 [<u>【如何在安卓工作室创建/启动新项目】</u>](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/) 。注意选择 **Java** 作为编程语言。

**第二步:在你的 build.gradle 文件**中添加下面的依赖项

下面是凌空的依赖，我们将使用它从应用编程接口获取数据。要添加此依赖项，请导航至**应用程序>渐变脚本> build.gradle(应用程序)**，并在依赖项部分添加以下依赖项。我们已经使用了[毕加索](https://www.geeksforgeeks.org/how-to-use-picasso-image-loader-library-in-android/)依赖从网址加载图像。

> *//下方依赖关系为使用改装。*
> 
> *实现‘com . squareup . retro fit 2:改装:2 . 9 . 0’*
> 
> *实现‘com . squareup . retro fit 2:converter-gson:2 . 5 . 0’*
> 
> *//下面的依赖关系为使用毕加索图像加载库*
> 
> *实现‘com . squareup . Picasso:Picasso:2.71828’*

添加这个依赖项后，同步你的项目，现在进入 **AndroidManifest.xml** 部分。

**第三步:在 AndroidManifest.xml 文件**中添加互联网权限

导航到**应用程序> AndroidManifest.xml** ，并添加以下代码。

## 可扩展标记语言

```
<!--permissions for INTERNET-->
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
    android:layout_gravity="center"
    android:gravity="center"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <!--progress bar for loading indicator-->
    <ProgressBar
        android:id="@+id/idPBLoading"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true" />

    <!--creating a recycler view for displaying
        our list of courses-->
    <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/idRVCourse"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />

</RelativeLayout>
```

**第五步:创建一个模态类来存储我们的数据**

导航到**应用程序> java >你的应用程序的包名>右键点击它>新建> Java 类**并将其命名为 **RecyclerData** 并添加下面的代码。在代码中添加注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
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

**第 6 步:为我们的回收视图**的每个项目创建一个布局文件

导航至 **app > res >布局>右键点击>新建>布局资源文件**，文件名为 **card_layout** ，并添加以下代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.cardview.widget.CardView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="8dp"
    android:elevation="8dp"
    app:cardCornerRadius="8dp">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical">

        <!--image view to display our course image-->
        <ImageView
            android:id="@+id/idIVCourse"
            android:layout_width="match_parent"
            android:layout_height="300dp"
            android:layout_margin="5dp" />

        <!--text view for our course name-->
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

            <!--text view for our batch name-->
            <TextView
                android:id="@+id/idTVBatch"
                android:layout_width="0dp"
                android:layout_height="wrap_content"
                android:layout_weight="1"
                android:padding="5dp"
                android:text="Batch"
                android:textColor="@color/black" />

            <!--text view to display course tracks-->
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
```

**第 7 步:创建一个适配器类，用于将数据设置到我们的回收视图项目**

要创建一个新的适配器类，导航到**应用程序> java >你的应用程序的包名>右键单击它>新建> Java 类**并将其命名为**recycleriviewadapter**并添加下面的代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.Context;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.ImageView;
import android.widget.TextView;

import androidx.annotation.NonNull;
import androidx.recyclerview.widget.RecyclerView;

import com.squareup.picasso.Picasso;

import java.util.ArrayList;

public class RecyclerViewAdapter extends RecyclerView.Adapter<RecyclerViewAdapter.RecyclerViewHolder> {

    // creating a variable for our array list and context.
    private ArrayList<RecyclerData> courseDataArrayList;
    private Context mcontext;

    // creating a constructor class.
    public RecyclerViewAdapter(ArrayList<RecyclerData> recyclerDataArrayList, Context mcontext) {
        this.courseDataArrayList = recyclerDataArrayList;
        this.mcontext = mcontext;
    }

    @NonNull
    @Override
    public RecyclerViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType) {
        // Inflate Layout
        View view = LayoutInflater.from(parent.getContext()).inflate(R.layout.card_layout, parent, false);
        return new RecyclerViewHolder(view);
    }

    @Override
    public void onBindViewHolder(@NonNull RecyclerViewHolder holder, int position) {
        // Set the data to textview from our modal class.
        RecyclerData modal = courseDataArrayList.get(position);
        holder.courseNameTV.setText(modal.getCourseName());
        holder.courseTracksTV.setText(modal.getCourseTracks());
        holder.courseModeTV.setText(modal.getCourseMode());
        Picasso.get().load(modal.getCourseimg()).into(holder.courseIV);
    }

    @Override
    public int getItemCount() {
        // this method returns the size of recyclerview
        return courseDataArrayList.size();
    }

    // View Holder Class to handle Recycler View.
    public class RecyclerViewHolder extends RecyclerView.ViewHolder {
        // creating variables for our views.
        private TextView courseNameTV, courseModeTV, courseTracksTV;
        private ImageView courseIV;

        public RecyclerViewHolder(@NonNull View itemView) {
            super(itemView);
            // initializing our views with their ids.
            courseNameTV = itemView.findViewById(R.id.idTVCourseName);
            courseModeTV = itemView.findViewById(R.id.idTVBatch);
            courseTracksTV = itemView.findViewById(R.id.idTVTracks);
            courseIV = itemView.findViewById(R.id.idIVCourse);
        }
    }
}
```

**第 8 步:创建一个接口类来编写我们的 API 调用**

导航到 **app > java >你的 app 的包名>右键点击它>新建> Java 类** 选择它为 **界面** 并将文件命名为**retracifitapi**并给它添加下面的代码。 在代码内部增加注释，更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.ArrayList;

import retrofit2.Call;
import retrofit2.http.GET;

public interface RetrofitAPI {

    // as we are making get request so we are displaying
    // GET as annotation.
    // and inside we are passing last parameter for our url.
    @GET("WO6S")

    // as we are calling data from array so we are calling
    // it with array list and naming that method as getAllCourses();
    Call<ArrayList<RecyclerData>> getAllCourses();
}
```

**第九步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.os.Bundle;
import android.view.View;
import android.widget.ProgressBar;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;
import androidx.recyclerview.widget.LinearLayoutManager;
import androidx.recyclerview.widget.RecyclerView;

import java.util.ArrayList;

import retrofit2.Call;
import retrofit2.Callback;
import retrofit2.Response;
import retrofit2.Retrofit;
import retrofit2.converter.gson.GsonConverterFactory;

public class MainActivity extends AppCompatActivity {

    // creating a variable for recycler view,
    // array list and adapter class.
    private RecyclerView courseRV;
    private ArrayList<RecyclerData> recyclerDataArrayList;
    private RecyclerViewAdapter recyclerViewAdapter;
    private ProgressBar progressBar;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initializing our variables.
        courseRV = findViewById(R.id.idRVCourse);
        progressBar = findViewById(R.id.idPBLoading);

        // creating new array list.
        recyclerDataArrayList = new ArrayList<>();

        // calling a method to
        // get all the courses.
        getAllCourses();
    }

    private void getAllCourses() {
        // on below line we are creating a retrofit
        // builder and passing our base url
        Retrofit retrofit = new Retrofit.Builder()
                .baseUrl("https://jsonkeeper.com/b/")
                // on below line we are calling add
                // Converter factory as Gson converter factory.
                .addConverterFactory(GsonConverterFactory.create())
                // at last we are building our retrofit builder.
                .build();
        // below line is to create an instance for our retrofit api class.
        RetrofitAPI retrofitAPI = retrofit.create(RetrofitAPI.class);

        // on below line we are calling a method to get all the courses from API.
        Call<ArrayList<RecyclerData>> call = retrofitAPI.getAllCourses();

        // on below line we are calling method to enqueue and calling
        // all the data from array list.
        call.enqueue(new Callback<ArrayList<RecyclerData>>() {
            @Override
            public void onResponse(Call<ArrayList<RecyclerData>> call, Response<ArrayList<RecyclerData>> response) {
                // inside on response method we are checking
                // if the response is success or not.
                if (response.isSuccessful()) {

                    // on successful we are hiding our progressbar.
                    progressBar.setVisibility(View.GONE);

                    // below line is to add our data from api to our array list.
                    recyclerDataArrayList = response.body();

                    // below line we are running a loop to add data to our adapter class.
                    for (int i = 0; i < recyclerDataArrayList.size(); i++) {
                        recyclerViewAdapter = new RecyclerViewAdapter(recyclerDataArrayList, MainActivity.this);

                        // below line is to set layout manager for our recycler view.
                        LinearLayoutManager manager = new LinearLayoutManager(MainActivity.this);

                        // setting layout manager for our recycler view.
                        courseRV.setLayoutManager(manager);

                        // below line is to set adapter to our recycler view.
                        courseRV.setAdapter(recyclerViewAdapter);
                    }
                }
            }

            @Override
            public void onFailure(Call<ArrayList<RecyclerData>> call, Throwable t) {
                // in the method of on failure we are displaying a
                // toast message for fail to get data.
                Toast.makeText(MainActivity.this, "Fail to get data", Toast.LENGTH_SHORT).show();
            }
        });
    }
}
```

现在运行您的应用程序，并查看应用程序的输出。

### **输出:**

<video class="wp-video-shortcode" id="video-559503-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210217154438/Screenrecorder-2021-01-24-13-21-47-357.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210217154438/Screenrecorder-2021-01-24-13-21-47-357.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210217154438/Screenrecorder-2021-01-24-13-21-47-357.mp4)</video>