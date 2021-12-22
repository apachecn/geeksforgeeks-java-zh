# 安卓如何更新 Back4App 数据库中的数据？

> 原文:[https://www . geesforgeks . org/如何更新数据备份 4 app-数据库 in-android/](https://www.geeksforgeeks.org/how-to-update-data-in-back4app-database-in-android/)

在之前的文章中，我们已经看到[添加](https://www.geeksforgeeks.org/how-to-add-data-to-back4app-database-in-android/)以及[在安卓应用中从我们的 Bac4App 数据库](https://www.geeksforgeeks.org/how-to-read-data-from-back4app-database-in-android/)读取数据。在本文中，我们将看一下**在您的数据库**中更新这些数据。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将更新我们的 Back4App 数据库中以前添加的数据。

### **分步实施**

**步骤 1:创建一个新的活动来更新数据**

要创建新活动，请导航至**应用程序> res >布局>右键单击它，然后单击新建>然后单击空活动创建新活动**，我们将它命名为**更新课程活动**。

**第 2 步:更新我们的适配器类，通过点击 RecyclerView 项**来打开一个新的活动

正如我们在上一篇文章中为在 Recycler 视图中显示课程列表而创建的适配器类。在本文中，我们将在该适配器类中添加 **onClickListener()** 用于 RecyclerView 项目单击侦听器。将以下代码片段添加到**CourseRVAdapter.java**文件中。

## Java

```java
// adding on click listener for our item of recycler view.
holder.itemView.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                // calling a intent to open new activity.
                Intent i = new Intent(context, UpdateCourseActivity.class);

                // on below line we are passing data to our intent on below line.
                i.putExtra("courseName", courses.getCourseName());
                i.putExtra("courseDescription", courses.getCourseDescription());
                i.putExtra("courseDuration", courses.getCourseDuration());

                // starting our activity on below line.
                context.startActivity(i);
            }
     });
}
```

以下是**CourseRVAdapter.java**文件的更新代码。

## 爪哇

```java
import android.content.Context;
import android.content.Intent;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.TextView;

import androidx.annotation.NonNull;
import androidx.recyclerview.widget.RecyclerView;

import java.util.ArrayList;

public class CourseRVAdapter extends RecyclerView.Adapter<CourseRVAdapter.ViewHolder> {
    private Context context;
    private ArrayList<CourseModal> courseModalArrayList;

    // creating a constructor class.
    public CourseRVAdapter(Context context, ArrayList<CourseModal> courseModalArrayList) {
        this.context = context;
        this.courseModalArrayList = courseModalArrayList;
    }

    @NonNull
    @Override
    public CourseRVAdapter.ViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType) {
        // passing our layout file for displaying our card item
        return new ViewHolder(LayoutInflater.from(context).inflate(R.layout.course_rv_item, parent, false));
    }

    @Override
    public void onBindViewHolder(@NonNull CourseRVAdapter.ViewHolder holder, int position) {
        // setting data to our text views from our modal class.
        CourseModal courses = courseModalArrayList.get(position);
        holder.courseNameTV.setText(courses.getCourseName());
        holder.courseDurationTV.setText(courses.getCourseDuration());
        holder.courseDescTV.setText(courses.getCourseDescription());

        // adding on click listener for our item of recycler view.
        holder.itemView.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                // calling a intent to open new activity.
                Intent i = new Intent(context, UpdateCourseActivity.class);

                // on below line we are passing data to our intent on below line.
                i.putExtra("courseName", courses.getCourseName());
                i.putExtra("courseDescription", courses.getCourseDescription());
                i.putExtra("courseDuration", courses.getCourseDuration());

                // starting our activity on below line.
                context.startActivity(i);
            }
        });
    }

    @Override
    public int getItemCount() {
        return courseModalArrayList.size();
    }

    public class ViewHolder extends RecyclerView.ViewHolder {
        // creating variables for our text views.
        private final TextView courseNameTV;
        private final TextView courseDurationTV;
        private final TextView courseDescTV;

        public ViewHolder(@NonNull View itemView) {
            super(itemView);
            // initializing our text views.
            courseNameTV = itemView.findViewById(R.id.idTVCourseName);
            courseDurationTV = itemView.findViewById(R.id.idTVCourseDuration);
            courseDescTV = itemView.findViewById(R.id.idTVCourseDescription);
        }
    }
}
```

**第三步:使用 activity_update_course.xml 文件**

导航至 **app > res >布局>activity _ update _ course . XML**并添加以下代码。

## XML

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".UpdateCourseActivity">

    <!--Edit text for getting course Name-->
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

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="10dp"
        android:orientation="horizontal"
        android:weightSum="2">

        <!--button for updating our course-->
        <Button
            android:id="@+id/idBtnUpdate"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="2"
            android:text="Update Course"
            android:textAllCaps="false" />

    </LinearLayout>

</LinearLayout>
```