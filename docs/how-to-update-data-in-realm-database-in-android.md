# 安卓如何更新领域数据库中的数据？

> 原文:[https://www . geesforgeks . org/如何更新领域数据-安卓数据库/](https://www.geeksforgeeks.org/how-to-update-data-in-realm-database-in-android/)

在之前的文章中，我们已经看到[在安卓](https://www.geeksforgeeks.org/how-to-install-and-add-data-to-realm-database-in-android/)中添加和[从我们的领域数据库中读取数据。在那篇文章中，我们在数据库中添加了课程细节，并以列表的形式读取数据。在本文中，我们将看一下**在我们的安卓应用程序中更新这些数据。**](https://www.geeksforgeeks.org/how-to-read-data-from-realm-database-in-android/)

### 我们将在本文中构建什么？

我们将致力于我们在之前文章中构建的现有应用程序。在这种情况下，我们将创建一个新的活动，我们将创建一个表格来更新我们的课程详细信息。下面是视频，我们将在其中看到我们将在本文中构建的内容。

<video class="wp-video-shortcode" id="video-580198-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210320111617/20210320_111504.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210320111617/20210320_111504.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210320111617/20210320_111504.mp4)</video>

### **分步实施**

**第 1 步** : **创建一个更新我们课程的新活动**

因为我们想更新我们的课程，所以在这个过程中，我们将创建一个新的活动，我们将能够在 SQLite 数据库中更新我们的课程。要创建新活动，我们必须导航到**应用程序> java >您的应用程序的包名>右键单击包名>新建>空活动**并将您的活动命名为**更新课程活动**并创建新活动。确保选择**空活动**。

**第二步:在应用项目的 build.gradle 文件中添加 google repository。**

> buildscript {
> 
> 存储库{
> 
> 谷歌()
> 
> mavenuentral _)
> 
> }

**所有的 Jetpack 组件都可以在 Google Maven 存储库中找到，包括在 build.gradle 文件**中

> 所有项目{
> 
> 存储库{
> 
> 谷歌()
> 
> mavenuentral _)
> 
> }
> 
> }

**第三步:更新我们的 CourseRVAdapter.java 类**

因为我们将开始一项新的活动来更新我们的课程。我们必须为我们的**回收视图**的项目添加点击监听器。要将 **onClickListener()** 添加到我们的回收器视图项目，请导航到**应用程序> java >您的应用程序的包名> CourseRVAdapter** 类，并简单地为我们的回收器视图项目添加一个 **onClickListener()** 。将下面的代码添加到适配器类中。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// adding on click listener for item of recycler view.
holder.itemView.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // on below line we are creating a new intent.
                Intent i = new Intent(context, UpdateCourseActivity.class);
                // on below line we are passing all the data to new activity.
                i.putExtra("courseName", modal.getCourseName());
                i.putExtra("courseDescription", modal.getCourseDescription());
                i.putExtra("courseDuration", modal.getCourseDuration());
                i.putExtra("courseTracks", modal.getCourseTracks());
                i.putExtra("id", modal.getId());
                // on below line we are starting a new activity.
                context.startActivity(i);
       }
});
```

以下是添加上述代码片段后**CourseRVAdapter.java**文件的更新代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.content.Context;
import android.content.Intent;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.TextView;

import androidx.annotation.NonNull;
import androidx.recyclerview.widget.RecyclerView;

import java.util.List;

public class CourseRVAdapter extends RecyclerView.Adapter<CourseRVAdapter.ViewHolder> {

    // variable for our array list and context
    private List<DataModal> dataModalArrayList;
    private Context context;

    public CourseRVAdapter(List<DataModal> dataModalArrayList, Context context) {
        this.dataModalArrayList = dataModalArrayList;
        this.context = context;
    }

    @NonNull
    @Override
    public CourseRVAdapter.ViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType) {
        // on below line we are inflating our layout
        // file for our recycler view items.
        View view = LayoutInflater.from(parent.getContext()).inflate(R.layout.course_rv_item, parent, false);
        return new ViewHolder(view);
    }

    @Override
    public void onBindViewHolder(@NonNull CourseRVAdapter.ViewHolder holder, int position) {
        DataModal modal = dataModalArrayList.get(position);
        holder.courseNameTV.setText(modal.getCourseName());
        holder.courseDescTV.setText(modal.getCourseDescription());
        holder.courseDurationTV.setText(modal.getCourseDuration());
        holder.courseTracksTV.setText(modal.getCourseTracks());

        // adding on click listener for item of recycler view.
        holder.itemView.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // on below line we are creating a new intent.
                Intent i = new Intent(context, UpdateCourseActivity.class);
                // on below line we are passing all the data to new activity.
                i.putExtra("courseName", modal.getCourseName());
                i.putExtra("courseDescription", modal.getCourseDescription());
                i.putExtra("courseDuration", modal.getCourseDuration());
                i.putExtra("courseTracks", modal.getCourseTracks());
                i.putExtra("id", modal.getId());
                // on below line we are starting a new activity.
                context.startActivity(i);
            }
        });
    }

    @Override
    public int getItemCount() {
        return dataModalArrayList.size();
    }

    public class ViewHolder extends RecyclerView.ViewHolder {
        // creating variables for our text views.
        private TextView courseNameTV, courseDescTV, courseDurationTV, courseTracksTV;

        public ViewHolder(@NonNull View itemView) {
            super(itemView);
            // initializing our text views
            courseNameTV = itemView.findViewById(R.id.idTVCourseName);
            courseDescTV = itemView.findViewById(R.id.idTVCourseDescription);
            courseDurationTV = itemView.findViewById(R.id.idTVCourseDuration);
            courseTracksTV = itemView.findViewById(R.id.idTVCourseTracks);
        }
    }
}
```