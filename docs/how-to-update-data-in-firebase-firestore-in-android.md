# 如何在安卓中更新 Firebase Firestore 中的数据？

> 原文:[https://www . geeksforgeeks . org/如何更新数据-in-firebase-firestore-in-Android/](https://www.geeksforgeeks.org/how-to-update-data-in-firebase-firestore-in-android/)

在前一篇文章中，我们已经在[上看到了如何在安卓](https://www.geeksforgeeks.org/create-and-add-data-to-firebase-firestore-in-android/)中向 Firebase Firestore 添加数据，[如何在安卓](https://www.geeksforgeeks.org/how-to-read-data-from-firebase-firestore-in-android/)中从 Firebase Firestore 读取数据。现在我们将看到**如何在我们的 Firebase Firestore** 中更新这些添加的数据。现在我们将在 Android Firebase 中实现这种更新数据。

### 我们将在本文中构建什么？

我们将创建一个类似于我们为添加数据而创建的屏幕，在这个屏幕中，我们将更新 Firebase Firestore 中的数据，这些数据也将在我们的应用程序中更新。

### **分步实施**

**步骤 1:创建一个新的活动来更新数据**

要创建新活动，请导航至**应用程序> res >布局>右键单击并单击新建>，然后单击空活动创建新活动**，我们将其命名为**更新课程**。创建新活动后，导航至**应用程序> res >布局>Activity _ update _ course . XML**，并添加以下代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".UpdateCourse">

    <!--Edittext for getting course Name-->
    <EditText
        android:id="@+id/idEdtCourseName"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="10dp"
        android:hint="Course Name"
        android:importantForAutofill="no"
        android:inputType="text" />

    <!--Edittext for getting course Duration-->
    <EditText
        android:id="@+id/idEdtCourseDuration"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="10dp"
        android:hint="Course Duration in min"
        android:importantForAutofill="no"
        android:inputType="time" />

    <!--Edittext for getting course Description-->
    <EditText
        android:id="@+id/idEdtCourseDescription"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="10dp"
        android:hint="Course Description"
        android:importantForAutofill="no"
        android:inputType="text" />

    <!--Button for updating your course to Firebase-->
    <Button
        android:id="@+id/idBtnUpdateCourse"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:text="Update Course Details"
        android:textAllCaps="false" />

</LinearLayout>
```

**步骤 2:更新我们存储数据的模态类**

在之前的文章中，我们已经看到创建了我们的 Modal 类。在本文中，我们将更新我们的**模态**类，这样我们就可以将我们的对象类从适配器传递给我们的活动进行导航。随着[可序列化](https://www.geeksforgeeks.org/object-serialization-inheritance-java/)的实现，我们必须创建一个新的字符串变量，并为该变量创建一个 getter 和 setter。我们将使用该变量来存储文档的 id。以下是更新后的**Courses.java**级的代码。代码中添加了注释，以便更详细地了解。

## Java

```java
import com.google.firebase.firestore.Exclude;

import java.io.Serializable;

// we have to implement our modal class
// with serializable so that we can pass
// our object class to new activity on
// our item click of recycler view.
public class Courses implements Serializable {

    // getter method for our id
    public String getId() {
        return id;
    }

    // setter method for our id
    public void setId(String id) {
        this.id = id;
    }

    // we are using exclude because
    // we are not saving our id
    @Exclude
    private String id;

    // variables for storing our data.
    private String courseName, courseDescription, courseDuration;

    public Courses() {
        // empty constructor required for Firebase.
    }

    // Constructor for all variables.
    public Courses(String courseName, String courseDescription, String courseDuration) {
        this.courseName = courseName;
        this.courseDescription = courseDescription;
        this.courseDuration = courseDuration;
    }

    // getter methods for all variables.
    public String getCourseName() {
        return courseName;
    }

    public void setCourseName(String courseName) {
        this.courseName = courseName;
    }

    public String getCourseDescription() {
        return courseDescription;
    }

    // setter method for all variables.
    public void setCourseDescription(String courseDescription) {
        this.courseDescription = courseDescription;
    }

    public String getCourseDuration() {
        return courseDuration;
    }

    public void setCourseDuration(String courseDuration) {
        this.courseDuration = courseDuration;
    }
}
```

**第三步:为我们的回收视图**添加 onClickListener()

正如我们在上一篇文章中为在 Recycler 视图中显示课程列表而创建的适配器类。在本文中，我们将在该适配器类中添加 **onClickListener()** 用于 RecyclerView 项目单击侦听器。将以下代码片段添加到**CourseRVAdapter.java**文件中。

## 爪哇

```java
// here we are adding on click listener
// for our item of recycler view.
itemView.setOnClickListener(new View.OnClickListener() {
                @Override
                public void onClick(View v) {

                    // after clicking of the item of recycler view.
                    // we are passing our course object to the new activity.
                    Courses courses = coursesArrayList.get(getAdapterPosition());

                    // below line is creating a new intent.
                    Intent i = new Intent(context, UpdateCourse.class);

                    // below line is for putting our course object to our next activity.
                    i.putExtra("course", courses);

                    // after passing the data we are starting our activity.
                    context.startActivity(i);
           }
    });
```