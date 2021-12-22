# 安卓中使用微光的内容占位符动画

> 原文:[https://www . geesforgeks . org/content-placeholder-animation-using-shimmer-in-Android/](https://www.geeksforgeeks.org/content-placeholder-animation-using-shimmer-in-android/)

我们看到了一个独特的加载屏幕设计，在脸书可以看到它用于加载目的，它也用于显示加载目的的内容占位符。GitHub 提供了这种类型的加载占位符，它看起来比普通的进度条还要漂亮。在本文中，我们将看一下**内容占位符在 Android 中使用 Shimmer 动画**的实现。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将以 JSON 格式从网址加载数据，在加载过程中，我们将显示一个用于加载的微光布局。下面给出一个视频样本，了解一下在本文中我们要做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-561180-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210218132459/Screenrecorder-2021-02-18-13-24-13-712.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210218132459/Screenrecorder-2021-02-18-13-24-13-712.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210218132459/Screenrecorder-2021-02-18-13-24-13-712.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:添加使用脸书微光布局的依赖关系**

导航到**应用程序>梯度脚本>构建.梯度**文件，并添加以下依赖项。

> //下方线用于截击库
> 
> 实现‘com . Android .凌空:凌空:1 . 1 . 1’
> 
> //下面一行用于图像加载库
> 
> 实现' com.squareup .毕加索:毕加索:2.71828 '
> 
> //使用 facebook 微光布局的依赖。
> 
> 实现' com . Facebook . shimmer:shimmer:0 . 5 . 0 '

现在，同步您的项目并移向您的 XML 文件。

**第三步:在安卓中添加互联网权限**

导航到**应用程序> AndroidManifest.xml** ，并在我们从互联网加载数据时为其添加互联网权限。

## 可扩展标记语言

```java
<uses-permission android:name="android.permission.INTERNET"/>
```

**第 4 步:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!-- Card view for displaying our card-->
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

            <!--Image view for displaying our image-->
            <ImageView
                android:id="@+id/idIVCourse"
                android:layout_width="match_parent"
                android:layout_height="300dp"
                android:layout_margin="5dp" />

            <!--Text view for displaying our course name-->
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

                <!--Text view for displaying our batch-->
                <TextView
                    android:id="@+id/idTVBatch"
                    android:layout_width="0dp"
                    android:layout_height="wrap_content"
                    android:layout_weight="1"
                    android:padding="5dp"
                    android:text="Batch"
                    android:textColor="@color/black" />

                <!--Text view for displaying our tracks.-->
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

    <!--below is the view for our shimmer-->
    <com.facebook.shimmer.ShimmerFrameLayout
        android:id="@+id/shimmerLayout"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:animateLayoutChanges="true"
        android:animationCache="true"
        app:shimmer_repeat_mode="restart"
        app:shimmer_shape="radial">

        <!--For shimmer we are creating a same layout 
            but setting its background as a gray colour and
            not providing any view inside it-->
        <androidx.cardview.widget.CardView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_margin="10dp"
            android:elevation="10dp"
            android:visibility="visible"
            app:cardCornerRadius="8dp">

            <LinearLayout
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:orientation="vertical">

                <!--Image view for displaying our image-->
                <ImageView
                    android:layout_width="match_parent"
                    android:layout_height="300dp"
                    android:layout_margin="5dp"
                    android:background="#B3B3B3" />

                <!--Text view for displaying our course name-->
                <TextView
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:layout_margin="5dp"
                    android:background="#B3B3B3"
                    android:padding="5dp"
                    android:textColor="@color/black"
                    android:textSize="18sp"
                    android:textStyle="bold" />

                <LinearLayout
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:layout_margin="5dp"
                    android:orientation="horizontal"
                    android:weightSum="2">

                    <!--Text view for displaying our batch-->
                    <TextView
                        android:layout_width="0dp"
                        android:layout_height="wrap_content"
                        android:layout_weight="1"
                        android:background="#B3B3B3"
                        android:padding="5dp"
                        android:textColor="@color/black" />

                    <!--Text view for displaying our tracks.-->
                    <TextView
                        android:layout_width="0dp"
                        android:layout_height="wrap_content"
                        android:layout_weight="1"
                        android:background="#B3B3B3"
                        android:padding="5dp"
                        android:textColor="@color/black" />

                </LinearLayout>

            </LinearLayout>

        </androidx.cardview.widget.CardView>

    </com.facebook.shimmer.ShimmerFrameLayout>

</RelativeLayout>
```

**第五步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.os.Bundle;
import android.view.View;
import android.widget.ImageView;
import android.widget.TextView;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;
import androidx.cardview.widget.CardView;

import com.android.volley.Request;
import com.android.volley.RequestQueue;
import com.android.volley.Response;
import com.android.volley.VolleyError;
import com.android.volley.toolbox.JsonObjectRequest;
import com.android.volley.toolbox.Volley;
import com.facebook.shimmer.ShimmerFrameLayout;
import com.squareup.picasso.Picasso;

import org.json.JSONException;
import org.json.JSONObject;

public class MainActivity extends AppCompatActivity {

    // creating variables for our textview,
    // imageview, cardview and progressbar.
    private TextView courseNameTV, courseTracksTV, courseBatchTV;
    private ImageView courseIV;
    private CardView courseCV;

    // variable for our shimmer frame layout
    private ShimmerFrameLayout shimmerFrameLayout;

    // below line is the variable for url from
    // where we will be querying our data.
    String url = "https://jsonkeeper.com/b/63OH";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initializing our shimmer layout.
        shimmerFrameLayout = findViewById(R.id.shimmerLayout);

        // on below line we are 
        // starting our shimmer layout.
        shimmerFrameLayout.startShimmer();

        // in below line we are 
        // initializing our all views.
        courseCV = findViewById(R.id.idCVCourse);
        courseNameTV = findViewById(R.id.idTVCourseName);
        courseTracksTV = findViewById(R.id.idTVTracks);
        courseBatchTV = findViewById(R.id.idTVBatch);
        courseIV = findViewById(R.id.idIVCourse);

        // creating a new variable for our request queue
        RequestQueue queue = Volley.newRequestQueue(MainActivity.this);
        JsonObjectRequest jsonObjectRequest = new JsonObjectRequest(Request.Method.GET, url, null, new Response.Listener<JSONObject>() {
            @Override
            public void onResponse(JSONObject response) {
                // inside the on response method.
                // in below line we are making our card
                // view visible after we get all the data.
                // on below line we are making our shimmer
                // layout visibility to gone.
                // on below line we are stopping our shimmer.
                shimmerFrameLayout.stopShimmer();
                courseCV.setVisibility(View.VISIBLE);
                try {
                    // now we get our response from API in json object format.
                    // in below line we are extracting a string with its key
                    // value from our json object.
                    // similarly we are extracting all the strings from our json object.
                    String courseName = response.getString("courseName");
                    String courseTracks = response.getString("courseTracks");
                    String courseMode = response.getString("courseMode");
                    String courseImageURL = response.getString("courseimg");

                    // after extracting all the data we are
                    // setting that data to all our views.
                    courseNameTV.setText(courseName);
                    courseTracksTV.setText(courseTracks);
                    courseBatchTV.setText(courseMode);

                    // we are using picasso to load the image from url.
                    Picasso.get().load(courseImageURL).into(courseIV);
                } catch (JSONException e) {
                    // if we do not extract data from json object properly.
                    // below line of code is use to handle json exception
                    e.printStackTrace();
                }
            }
        }, new Response.ErrorListener() {
            // this is the error listener method which
            // we will call if we get any error from API.
            @Override
            public void onErrorResponse(VolleyError error) {
                // below line is use to display a toast message along with our error.
                Toast.makeText(MainActivity.this, "Fail to get data..", Toast.LENGTH_SHORT).show();
            }
        });
        // at last we are adding our json
        // object request to our request
        // queue to fetch all the json data.
        queue.add(jsonObjectRequest);
    }
}
```

现在运行您的应用程序，并查看应用程序的输出。

### **输出:**

<video class="wp-video-shortcode" id="video-561180-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210218132459/Screenrecorder-2021-02-18-13-24-13-712.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210218132459/Screenrecorder-2021-02-18-13-24-13-712.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210218132459/Screenrecorder-2021-02-18-13-24-13-712.mp4)</video>