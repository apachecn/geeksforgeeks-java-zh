# 如何在安卓中保存数组列表到 SharedPreferences？

> 原文:[https://www . geesforgeks . org/如何保存-ArrayList-to-shared preferences-in-Android/](https://www.geeksforgeeks.org/how-to-save-arraylist-to-sharedpreferences-in-android/)

[Android 中的 shared references](https://www.geeksforgeeks.org/shared-preferences-in-android-with-examples/)是本地存储，用来存储手机存储中的字符串、整数和变量，这样我们就可以管理 app 的状态。我们已经看到用键和值对将简单变量存储在共享的 prefs 中。在本文中，我们将看到如何将[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)存储到我们的安卓应用程序中的共享首选项中。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将在一个简单的[recycle view](https://www.geeksforgeeks.org/android-recyclerview/)中显示课程名称及其描述，并将所有这些数据存储在我们的共享首选项中。因此，当我们关闭应用程序并重新打开应用程序时，所有数据都将保存在共享首选项中，回收器视图的状态将保持不变。下面给出了一个示例视频，让我们了解一下在本文中要做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-549002-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210124105228/Screenrecorder-2021-01-24-10-25-32-939.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210124105228/Screenrecorder-2021-01-24-10-25-32-939.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210124105228/Screenrecorder-2021-01-24-10-25-32-939.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在 build.gradle** 中添加 gson 的依赖关系

导航到**应用程序>梯度脚本>构建.梯度(应用程序)**，并在依赖项部分添加以下依赖项。

> 实现' com . Google . code . gson:gson:2 . 8 . 5 '

添加此依赖项后，同步您的项目。

**第三步:创建一个模态类来存储我们的数据**

导航到**应用程序> java >你的应用程序的包名>右键单击它>新建> Java 类**并将你的类命名为 **CourseModal** ，并在其中添加下面的代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class CourseModal {

    // variables for our course 
    // name and description.
    private String courseName;
    private String courseDescription;

    // creating constructor for our variables.
    public CourseModal(String courseName, String courseDescription) {
        this.courseName = courseName;
        this.courseDescription = courseDescription;
    }

    // creating getter and setter methods.
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
}
```

**第 4 步:为我们的回收视图**创建布局文件

导航至 **app > res >布局>右键单击>新建>布局资源文件**并将您的布局命名为 **course_rv_item** 并添加以下代码。

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

    <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

        <!--text view for our course name-->
        <TextView
            android:id="@+id/idTVCourseName"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:padding="8dp"
            android:text="Course Name"
            android:textColor="@color/black"
            android:textSize="18sp" />

        <!--text view for our course description-->
        <TextView
            android:id="@+id/idTVCourseDescription"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_below="@id/idTVCourseName"
            android:padding="5dp"
            android:text="COurse Description"
            android:textColor="@color/black" />

    </RelativeLayout>

</androidx.cardview.widget.CardView>
```

**第 5 步:创建一个适配器类，用于将数据设置到我们的 recycle view**的项目中

导航到**应用> java >你的应用的包名>右键点击它>新建> Java 类**并将其命名为 **CourseAdapter** 并添加下面的代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.Context;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.TextView;

import androidx.annotation.NonNull;
import androidx.recyclerview.widget.RecyclerView;

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
        holder.courseDescTV.setText(modal.getCourseDescription());
    }

    @Override
    public int getItemCount() {
        // returning the size of array list.
        return courseModalArrayList.size();
    }

    public class ViewHolder extends RecyclerView.ViewHolder {

        // creating variables for our views.
        private TextView courseNameTV, courseDescTV;

        public ViewHolder(@NonNull View itemView) {
            super(itemView);

            // initializing our views with their ids.
            courseNameTV = itemView.findViewById(R.id.idTVCourseName);
            courseDescTV = itemView.findViewById(R.id.idTVCourseDescription);
        }
    }
}
```

**第 6 步:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--edit text for adding course name-->
    <EditText
        android:id="@+id/idEdtCourseName"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_toStartOf="@id/idBtnSave"
        android:layout_toLeftOf="@id/idBtnSave"
        android:hint="Enter course Name" />

    <!--edit text for adding course description-->
    <EditText
        android:id="@+id/idEdtCourseDescription"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idEdtCourseName"
        android:layout_marginEnd="4dp"
        android:layout_marginRight="4dp"
        android:layout_toLeftOf="@id/idBtnAdd"
        android:hint="Enter Course Description" />

    <!--button for adding data to recycler view-->
    <Button
        android:id="@+id/idBtnAdd"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/idEdtCourseName"
        android:layout_alignParentEnd="true"
        android:layout_alignParentRight="true"
        android:layout_margin="10dp"
        android:text="Add " />

    <!--button for saving data to shared prefs-->
    <Button
        android:id="@+id/idBtnSave"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentEnd="true"
        android:layout_alignParentRight="true"
        android:layout_margin="10dp"
        android:text="Save " />

    <!--recycler view to display our data-->
    <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/idRVCourses"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:layout_below="@id/idEdtCourseDescription" />

</RelativeLayout>
```

**第 7 步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.SharedPreferences;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;
import androidx.recyclerview.widget.LinearLayoutManager;
import androidx.recyclerview.widget.RecyclerView;

import com.google.gson.Gson;
import com.google.gson.reflect.TypeToken;

import java.lang.reflect.Type;
import java.util.ArrayList;

public class MainActivity extends AppCompatActivity {

    // creating variables for our ui components.
    private EditText courseNameEdt, courseDescEdt;
    private Button addBtn, saveBtn;
    private RecyclerView courseRV;

    // variable for our adapter class and array list
    private CourseAdapter adapter;
    private ArrayList<CourseModal> courseModalArrayList;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initializing our variables.
        courseNameEdt = findViewById(R.id.idEdtCourseName);
        courseDescEdt = findViewById(R.id.idEdtCourseDescription);
        addBtn = findViewById(R.id.idBtnAdd);
        saveBtn = findViewById(R.id.idBtnSave);
        courseRV = findViewById(R.id.idRVCourses);

        // calling method to load data
        // from shared prefs.
        loadData();

        // calling method to build
        // recycler view.
        buildRecyclerView();

        // on click listener for adding data to array list.
        addBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // below line is use to add data to array list.
                courseModalArrayList.add(new CourseModal(courseNameEdt.getText().toString(), courseDescEdt.getText().toString()));
                // notifying adapter when new data added.
                adapter.notifyItemInserted(courseModalArrayList.size());
            }
        });
        // on click listener for saving data in shared preferences.
        saveBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // calling method to save data in shared prefs.
                saveData();
            }
        });
    }

    private void buildRecyclerView() {
        // initializing our adapter class.
        adapter = new CourseAdapter(courseModalArrayList, MainActivity.this);

        // adding layout manager to our recycler view.
        LinearLayoutManager manager = new LinearLayoutManager(this);
        courseRV.setHasFixedSize(true);

        // setting layout manager to our recycler view.
        courseRV.setLayoutManager(manager);

        // setting adapter to our recycler view.
        courseRV.setAdapter(adapter);
    }

    private void loadData() {
        // method to load arraylist from shared prefs
        // initializing our shared prefs with name as 
        // shared preferences.
        SharedPreferences sharedPreferences = getSharedPreferences("shared preferences", MODE_PRIVATE);

        // creating a variable for gson.
        Gson gson = new Gson();

        // below line is to get to string present from our 
        // shared prefs if not present setting it as null.
        String json = sharedPreferences.getString("courses", null);

        // below line is to get the type of our array list.
        Type type = new TypeToken<ArrayList<CourseModal>>() {}.getType();

        // in below line we are getting data from gson 
        // and saving it to our array list
        courseModalArrayList = gson.fromJson(json, type);

        // checking below if the array list is empty or not
        if (courseModalArrayList == null) {
            // if the array list is empty
            // creating a new array list.
            courseModalArrayList = new ArrayList<>();
        }
    }

    private void saveData() {
        // method for saving the data in array list.
        // creating a variable for storing data in
        // shared preferences.
        SharedPreferences sharedPreferences = getSharedPreferences("shared preferences", MODE_PRIVATE);

        // creating a variable for editor to 
        // store data in shared preferences.
        SharedPreferences.Editor editor = sharedPreferences.edit();

        // creating a new variable for gson.
        Gson gson = new Gson();

        // getting data from gson and storing it in a string.
        String json = gson.toJson(courseModalArrayList);

        // below line is to save data in shared 
        // prefs in the form of string.
        editor.putString("courses", json);

        // below line is to apply changes 
        // and save data in shared prefs.
        editor.apply();

        // after saving data we are displaying a toast message.
        Toast.makeText(this, "Saved Array List to Shared preferences. ", Toast.LENGTH_SHORT).show();
    }
}
```

现在运行您的应用程序，并查看应用程序的输出。

### **输出:**

<video class="wp-video-shortcode" id="video-549002-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210124105228/Screenrecorder-2021-01-24-10-25-32-939.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210124105228/Screenrecorder-2021-01-24-10-25-32-939.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210124105228/Screenrecorder-2021-01-24-10-25-32-939.mp4)</video>