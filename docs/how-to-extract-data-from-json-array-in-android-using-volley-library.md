# 如何使用凌空库从安卓中的 JSON 数组中提取数据？

> 原文:[https://www . geeksforgeeks . org/如何使用凌空库从安卓 json 阵列中提取数据/](https://www.geeksforgeeks.org/how-to-extract-data-from-json-array-in-android-using-volley-library/)

在上一篇关于[使用凌空库](https://www.geeksforgeeks.org/json-parsing-in-android-using-volley-library/)在安卓中解析 JSON 的文章中，我们已经看到了如何在我们的安卓应用程序中从 JSON Object 获取数据，并在我们的应用程序中显示该 JSON Object。在本文中，我们将了解如何从 **JSON 数组**中提取数据并在我们的应用程序中显示。

> **JSON 数组** : JSON 数组是一个集合或称为数据集合，它保存多个具有相似数据类型的 JSON 对象。JSON 数组可以很容易地用“[”大括号开头和“]”大括号结尾来标识。一个 JSON 数组包含多个具有相似数据的 JSON 对象。每个 JSON 对象都以键和值对的形式存储数据。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将显示一个列表[卡片视图](https://www.geeksforgeeks.org/cardview-in-android-with-example/)，其中我们将显示一些在极客上为极客提供的课程。下面给出了一个 GIF 示例，来了解一下我们将在本文中做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-548254-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210124132302/Screenrecorder-2021-01-24-13-21-47-357.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210124132302/Screenrecorder-2021-01-24-13-21-47-357.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210124132302/Screenrecorder-2021-01-24-13-21-47-357.mp4)</video>

下面是我们的 JSON 数组，我们将在我们的安卓应用程序中显示数据。

> [
> 
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
> },
> 
> {
> 
> “课程名称”:“Linux & Shell 脚本基础”，
> 
> “course img”:“https://media . geeksforgeeks . org/img-practice/banner/Linux-shell-scripting-thumbnail . png”，
> 
> “课程模式”:“在线批处理”，
> 
> “课程曲目”:“8 首曲目”
> 
> },
> 
> {
> 
> “课程名称”:“11 周数据结构和算法研讨会”，
> 
> “course img”:“https://media . geeksforgeeks . org/img-practice/banner/Workshop-DSA-thumbnail . png”，
> 
> “课程模式”:“在线批处理”，
> 
> “课程曲目”:“47 首曲目”
> 
> },
> 
> {
> 
> “课程名称”:“数据结构和算法”，
> 
> “course img”:“https://media . geeksforgeeks . org/img-practice/banner/DSA-自定进度-thumbnail.png”，
> 
> “课程模式”:“在线批处理”，
> 
> “课程曲目”:“24 首曲目”
> 
> }
> 
> ]

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在你的 build.gradle 文件**中添加下面的依赖项

下面是凌空的依赖，我们将使用它从应用编程接口获取数据。要添加此依赖项，请导航至**应用程序>渐变脚本>** [**构建.渐变(应用程序)**](https://www.geeksforgeeks.org/android-build-gradle/) ，并在依赖项部分添加以下依赖项。我们使用了[毕加索](https://www.geeksforgeeks.org/how-to-use-picasso-image-loader-library-in-android/)依赖从网址加载图像。

> *//下方线用于凌空库*
> 
> *实现‘com . Android .凌空:凌空:1 . 1 . 1’*
> 
> *//下图线用于图像加载库*
> 
> *实现‘com . squareup . Picasso:Picasso:2.71828’*

添加这个依赖项后，同步你的项目，现在进入 **AndroidManifest.xml** 部分。

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
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--progress bar for loading indicator-->
    <ProgressBar
        android:id="@+id/idPB"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true" />

    <!--recycler view to display our data-->
    <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/idRVCourses"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:visibility="gone" />

</RelativeLayout>
```

**第 5 步:创建一个模态类来存储我们的数据**

为了存储数据，我们必须创建一个新的 java 类。要创建一个新的 java 类，导航到**应用程序> java >你的应用程序的包名>右键单击它>新建> Java 类**并将其命名为 **CourseModal** 并添加下面的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
public class CourseModal {

    // variables for our course 
    // name and description.
    private String courseName;
    private String courseimg;
    private String courseMode;
    private String courseTracks;

    // creating constructor for our variables.
    public CourseModal(String courseName, String courseimg, String courseMode, String courseTracks) {
        this.courseName = courseName;
        this.courseimg = courseimg;
        this.courseMode = courseMode;
        this.courseTracks = courseTracks;
    }

    // creating getter and setter methods.
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
}
```

**第 6 步:为我们的回收视图**的每个项目创建一个布局文件

导航至 **app > res >布局>右键单击>新建>布局资源文件**并将文件名命名为 **course_rv_item** 并添加以下代码。代码中添加了注释，以便更详细地了解。

## 可扩展标记语言

```java
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

        <!--ImageView to display our course image-->
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

**第 7 步:创建一个适配器类，用于将数据设置到我们的回收视图项**

要创建一个新的适配器类，导航到**应用程序> java >你的应用程序的包名>右键单击它>新建> Java 类**并将其命名为 **CourseAdapter** 并添加下面的代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
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

public class CourseAdapter extends RecyclerView.Adapter<CourseAdapter.ViewHolder> {

    // creating a variable for array list and context.
    private ArrayList<CourseModal> courseModalArrayList;
    private Context context;

    // creating a constructor for our variables.
    public CourseAdapter(ArrayList<CourseModal> courseModalArrayList, Context context) {
        this.courseModalArrayList = courseModalArrayList;
        this.context = context;
    }

    @NonNull
    @Override
    public CourseAdapter.ViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType) {
        // below line is to inflate our layout.
        View view = LayoutInflater.from(parent.getContext()).inflate(R.layout.course_rv_item, parent, false);
        return new ViewHolder(view);
    }

    @Override
    public void onBindViewHolder(@NonNull CourseAdapter.ViewHolder holder, int position) {
        // setting data to our views of recycler view.
        CourseModal modal = courseModalArrayList.get(position);
        holder.courseNameTV.setText(modal.getCourseName());
        holder.courseTracksTV.setText(modal.getCourseTracks());
        holder.courseModeTV.setText(modal.getCourseMode());
        Picasso.get().load(modal.getCourseimg()).into(holder.courseIV);
    }

    @Override
    public int getItemCount() {
        // returning the size of array list.
        return courseModalArrayList.size();
    }

    public class ViewHolder extends RecyclerView.ViewHolder {
        // creating variables for our views.
        private TextView courseNameTV, courseModeTV, courseTracksTV;
        private ImageView courseIV;

        public ViewHolder(@NonNull View itemView) {
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

**第 8 步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.os.Bundle;
import android.view.View;
import android.widget.ProgressBar;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;
import androidx.recyclerview.widget.LinearLayoutManager;
import androidx.recyclerview.widget.RecyclerView;

import com.android.volley.Request;
import com.android.volley.RequestQueue;
import com.android.volley.Response;
import com.android.volley.VolleyError;
import com.android.volley.toolbox.JsonArrayRequest;
import com.android.volley.toolbox.Volley;

import org.json.JSONArray;
import org.json.JSONException;
import org.json.JSONObject;

import java.util.ArrayList;

public class MainActivity extends AppCompatActivity {

    // creating variables for 
    // our ui components.
    private RecyclerView courseRV;

    // variable for our adapter 
    // class and array list
    private CourseAdapter adapter;
    private ArrayList<CourseModal> courseModalArrayList;

    // below line is the variable for url from
    // where we will be querying our data.
    String url = "https://jsonkeeper.com/b/WO6S";
    private ProgressBar progressBar;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initializing our variables.
        courseRV = findViewById(R.id.idRVCourses);
        progressBar = findViewById(R.id.idPB);

        // below line we are creating a new array list
        courseModalArrayList = new ArrayList<>();
        getData();

        // calling method to 
        // build recycler view.
        buildRecyclerView();
    }

    private void getData() {
        // creating a new variable for our request queue
        RequestQueue queue = Volley.newRequestQueue(MainActivity.this);
        // in this case the data we are getting is in the form
        // of array so we are making a json array request.
        // below is the line where we are making an json array 
        // request and then extracting data from each json object.
        JsonArrayRequest jsonArrayRequest = new JsonArrayRequest(Request.Method.GET, url, null, new Response.Listener<JSONArray>() {
            @Override
            public void onResponse(JSONArray response) {
                progressBar.setVisibility(View.GONE);
                courseRV.setVisibility(View.VISIBLE);
                for (int i = 0; i < response.length(); i++) {
                    // creating a new json object and 
                    // getting each object from our json array.
                    try {
                        // we are getting each json object.
                        JSONObject responseObj = response.getJSONObject(i);

                        // now we get our response from API in json object format.
                        // in below line we are extracting a string with
                        // its key value from our json object.
                        // similarly we are extracting all the strings from our json object.
                        String courseName = responseObj.getString("courseName");
                        String courseTracks = responseObj.getString("courseTracks");
                        String courseMode = responseObj.getString("courseMode");
                        String courseImageURL = responseObj.getString("courseimg");
                        courseModalArrayList.add(new CourseModal(courseName, courseImageURL, courseMode, courseTracks));
                        buildRecyclerView();
                    } catch (JSONException e) {
                        e.printStackTrace();
                    }
                }
            }
        }, new Response.ErrorListener() {
            @Override
            public void onErrorResponse(VolleyError error) {
                Toast.makeText(MainActivity.this, "Fail to get the data..", Toast.LENGTH_SHORT).show();
            }
        });
        queue.add(jsonArrayRequest);
    }

    private void buildRecyclerView() {

        // initializing our adapter class.
        adapter = new CourseAdapter(courseModalArrayList, MainActivity.this);

        // adding layout manager 
        // to our recycler view.
        LinearLayoutManager manager = new LinearLayoutManager(this);
        courseRV.setHasFixedSize(true);

        // setting layout manager 
        // to our recycler view.
        courseRV.setLayoutManager(manager);

        // setting adapter to 
        // our recycler view.
        courseRV.setAdapter(adapter);
    }
}
```

现在运行您的应用程序，并查看应用程序的输出。

### **输出:**

<video class="wp-video-shortcode" id="video-548254-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210124132302/Screenrecorder-2021-01-24-13-21-47-357.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210124132302/Screenrecorder-2021-01-24-13-21-47-357.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210124132302/Screenrecorder-2021-01-24-13-21-47-357.mp4)</video>