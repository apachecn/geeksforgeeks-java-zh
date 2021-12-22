# 如何在安卓系统的房间数据库中进行 CRUD 操作？

> 原文:[https://www . geeksforgeeks . org/如何执行-crud-operations-in-room-database-in-Android/](https://www.geeksforgeeks.org/how-to-perform-crud-operations-in-room-database-in-android/)

应用程序中的数据可以通过不同的方式保存在用户的设备上。我们可以通过 SQLite 表、共享首选项等多种方式将数据存储在用户的设备中。在本文中，我们将了解一下**在 Android 上保存数据、读取、更新和删除房间数据库**中的数据。我们将在安卓系统上使用房间数据库执行 CRUD 操作。在本文中，我们将了解如何在安卓的房间数据库中执行 CRUD 操作。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将添加不同类型的课程，可在极客为极客。我们将把所有这些数据存储在房间数据库中，并对这些课程进行 CRUD 操作。下面给出了一个示例视频，让我们了解一下在本文中要做什么。请注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-553520-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210130193831/Screenrecorder-2021-01-30-19-31-33-197.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210130193831/Screenrecorder-2021-01-30-19-31-33-197.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210130193831/Screenrecorder-2021-01-30-19-31-33-197.mp4)</video>

### 什么是房间？

Room 是一个持久性库，它在 SQLite 数据库上提供了一个抽象层，以允许更健壮的数据库。在 room 的帮助下，我们可以很容易地创建数据库并执行 CRUD 操作。

### 房间的组成

房间的三个主要组件是**实体、数据库和 DAO** 。

*   **实体**:实体是用@Entity 标注的模态类。这个类的变量将成为我们的列，这个类就是我们的表。
*   **数据库**:这是一个抽象类，我们将在其中存储我们所有的数据库条目，我们可以称之为实体。
*   **DAO**:DAO 的完整形式是一个**数据库访问对象**，它是一个接口类，在它的帮助下我们可以在我们的数据库中执行不同的操作。

现在，让我们转向在安卓系统中实现房间数据库。

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在 build.gradle 文件中添加使用 Room 的依赖关系**

导航到**应用程序>渐变脚本>构建.渐变**文件，并在依赖项部分添加以下依赖项。

> //在下面添加使用房间的依赖项。
> 
> 实现' androidx . room:room-runtime:2 . 2 . 5 '
> 
> 注释处理器' androidx . room:room-编译器:2.2.5 '
> 
> //在下面添加使用房间生命周期扩展的依赖项。
> 
> 实现“androidx . life cycle:life cycle-extensions:2 . 2 . 0”
> 
> 注释处理器“androidx . life cycle:life cycle-编译器:2.2.0”

添加上述依赖项部分后。现在同步您的项目，我们将转向我们的 XML 文件。

**步骤 3:使用 activity_main.xml 文件**

导航到 **app > res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是**activity _ main . XML**文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <!--recycler view to display our data-->
    <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/idRVCourses"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />

    <!--fab to add new courses-->
    <com.google.android.material.floatingactionbutton.FloatingActionButton
        android:id="@+id/idFABAdd"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentEnd="true"
        android:layout_alignParentBottom="true"
        android:layout_marginStart="18dp"
        android:layout_marginTop="18dp"
        android:layout_marginEnd="18dp"
        android:layout_marginBottom="18dp"
        android:src="@android:drawable/ic_input_add"
        app:tint="@color/white" />

</RelativeLayout>
```

**第 4 步:创建一个模态类来存储我们的数据**

导航到**应用程序> java >你的应用程序包名称>右键单击它>新建> Java 类**并将该类命名为 **CourseModal** ，并在其中添加下面的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import androidx.room.Entity;
import androidx.room.PrimaryKey;

// below line is for setting table name.
@Entity(tableName = "course_table")
public class CourseModal {

    // below line is to auto increment
    // id for each course.
    @PrimaryKey(autoGenerate = true)

    // variable for our id.
    private int id;

    // below line is a variable 
    // for course name.
    private String courseName;

    // below line is use for 
    // course description.
    private String courseDescription;

    // below line is use 
    // for course duration.
    private String courseDuration;

    // below line we are creating constructor class.
    // inside constructor class we are not passing 
    // our id because it is incrementing automatically
    public CourseModal(String courseName, String courseDescription, String courseDuration) {
        this.courseName = courseName;
        this.courseDescription = courseDescription;
        this.courseDuration = courseDuration;
    }

    // on below line we are creating
    // getter and setter methods.
    public String getCourseName() {
        return courseName;
    }

    public void setCourseName(String courseName) {
        this.courseName = courseName;
    }

    public String getCourseDescription() {
        return courseDescription;
    }

    public void setCourseDescription(String courseDescription) {
        this.courseDescription = courseDescription;
    }

    public String getCourseDuration() {
        return courseDuration;
    }

    public void setCourseDuration(String courseDuration) {
        this.courseDuration = courseDuration;
    }

    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }
}
```