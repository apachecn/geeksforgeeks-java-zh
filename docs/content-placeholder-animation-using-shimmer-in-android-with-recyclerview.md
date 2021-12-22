# 内容占位符动画在 Android 中使用微光与 recycle view

> 原文:[https://www . geesforgeks . org/content-placeholder-animation-using-shimmer-in-Android-with-recycle view/](https://www.geeksforgeeks.org/content-placeholder-animation-using-shimmer-in-android-with-recyclerview/)

我们已经看到了[内容占位符动画在 Android](https://www.geeksforgeeks.org/content-placeholder-animation-using-shimmer-in-android/) 中使用 Shimmer 实现的一个简单视图。在这篇文章中，我们将看看如何在安卓系统中使用 [**实现**内容占位符动画****](https://www.geeksforgeeks.org/android-recyclerview/) 。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，在这个应用程序中，我们将从我们的应用编程接口在我们的安卓回收视图中简单地显示数据。为了加载数据，我们将显示一个内容占位符用于加载。下面给出了一个示例视频，让我们了解一下在本文中要做什么。请注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-562837-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210220191322/Screenrecorder-2021-02-20-19-10-48-930.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210220191322/Screenrecorder-2021-02-20-19-10-48-930.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210220191322/Screenrecorder-2021-02-20-19-10-48-930.mp4)</video>

### **分步实施**

**第一步:创建新项目**

在安卓工作室创建新项目请参考 [<u>【如何在安卓工作室创建/启动新项目】</u>](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/) 。注意选择 **Java** 作为编程语言。

**第二步:添加使用脸书微光布局的依赖关系**

导航到**应用程序>梯度脚本>构建.梯度**文件，并添加以下依赖项。

> *//下方线用于凌空库*
> 
> *实现‘com . Android .凌空:凌空:1 . 1 . 1’*
> 
> *//下图线用于图像加载库*
> 
> *实现‘com . squareup . Picasso:Picasso:2.71828’*
> 
> *//使用 facebook 微光布局的依赖。*
> 
> *实现‘com . Facebook . shimmer:shimmer:0 . 5 . 0’*

现在，同步您的项目并移向您的 XML 文件。

**第三步:在安卓中添加互联网权限**

导航到**应用程序> AndroidManifest.xml** ，并在我们从互联网加载数据时为其添加互联网权限。

## 可扩展标记语言

```
<uses-permission android:name="android.permission.INTERNET"/>
```

**第 4 步:创建一个模态类来存储我们的数据**

导航到**应用> java >你的应用的包名>右键点击它>新建> Java 类**并将其命名为 **CourseModal** 并添加下面的代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class CourseModal {
    // variables for our course
    // name and description.
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

    public CourseModal(String courseName, String courseimg, String courseMode, String courseTracks) {
        this.courseName = courseName;
        this.courseimg = courseimg;
        this.courseMode = courseMode;
        this.courseTracks = courseTracks;
    }
}
```

**第五步:在安卓**中为我们的回收视图的项目创建布局文件

导航至 **app > res >布局>右键点击>新建>布局资源文件**并将其命名为 **course_rv_item** 并添加以下代码。

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

**第 6 步:为我们的微光布局创建布局文件**

导航至 **app > res >布局>右键单击>新建>布局资源文件**并将其命名为 **shimmer_layout** 并添加以下代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.cardview.widget.CardView 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
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
                android:layout_margin="2dp"
                android:layout_weight="1"
                android:background="#B3B3B3"
                android:padding="5dp"
                android:textColor="@color/black" />

            <!--Text view for displaying our tracks.-->
            <TextView
                android:layout_width="0dp"
                android:layout_height="wrap_content"
                android:layout_margin="2dp"
                android:layout_weight="1"
                android:background="#B3B3B3"
                android:padding="5dp"
                android:textColor="@color/black" />

        </LinearLayout>

    </LinearLayout>

</androidx.cardview.widget.CardView>
```

**第 7 步:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--recycler view to display our data-->
    <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/idRVCourses"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:visibility="gone" />

    <!--below is the view for our shimmer-->
    <com.facebook.shimmer.ShimmerFrameLayout
        android:id="@+id/shimmerLayout"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:animateLayoutChanges="true"
        android:animationCache="true"
        app:shimmer_repeat_mode="restart"
        app:shimmer_shape="radial">

        <!--For shimmer we are creating a same 
            layout but setting its background 
            as a gray colour and not providing
            any view inside it-->
        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            android:orientation="vertical">

            <!--below we are displaying multiple
                shimmer layouts using include
                to show them in list format-->
            <include layout="@layout/shimmer_layout" />
            <include layout="@layout/shimmer_layout" />
            <include layout="@layout/shimmer_layout" />
            <include layout="@layout/shimmer_layout" />
            <include layout="@layout/shimmer_layout" />

        </LinearLayout>

    </com.facebook.shimmer.ShimmerFrameLayout>

</RelativeLayout>
```