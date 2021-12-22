# 安卓中可扩展的新闻提要，示例

> 原文:[https://www . geesforgeks . org/expandable-news-feed-in-Android-with-example/](https://www.geeksforgeeks.org/expandable-news-feed-in-android-with-example/)

许多新闻应用程序使用可扩展类型的视图来显示新闻和类别。这种类型的功能将有助于使用户界面看起来更好，并在同一用户界面中提供额外的内容。当您在应用程序中显示不同类型的内容并使用不同类别对其进行过滤时，会使用这种类型的用户界面。在本文中，我们将在我们的安卓应用程序中创建一个类似类型的可扩展新闻提要示例。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将显示一个回收视图，其中我们将显示新闻类别，单击新闻类别，我们将在其中的回收视图中显示该特定类别的新闻。下面给出了一个示例视频，以了解我们将在本文中做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-594228-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210418231530/20210418_231327.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210418231530/20210418_231327.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210418231530/20210418_231327.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/idRLView"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--recycler view for displaying news categories. -->
    <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/idRVNewsCategories"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />

</RelativeLayout>
```

**第三步:创建一个模态类来存储我们的新闻**

导航到**应用> java >你的应用的包名>右键点击它>新建> Java 类**并将其命名为**新闻模式**并添加下面的代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class NewsModal {

    // string for news title and description.
    private String newsTitle;
    private String newsDesc;

    // on below line we have created a constructor.
    public NewsModal(String newsTitle, String newsDesc) {
        this.newsTitle = newsTitle;
        this.newsDesc = newsDesc;
    }

    // creating a getter and setter.
    public String getNewsTitle() {
        return newsTitle;
    }

    public void setNewsTitle(String newsTitle) {
        this.newsTitle = newsTitle;
    }

    public String getNewsDesc() {
        return newsDesc;
    }

    public void setNewsDesc(String newsDesc) {
        this.newsDesc = newsDesc;
    }

}
```

**第 4 步:创建一个模态类来存储我们的新闻类别**

同样，创建另一个 Java 类，并将其命名为**类别模式**，并向其中添加以下代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.ArrayList;

public class CategoriesModal {

    // creating variable for our category, 
    // news array list and expanded boolean.
    private String newsCategory;
    private ArrayList<NewsModal> newsModalArrayList;
    private boolean expanded;

    // creating a constructor.
    public CategoriesModal(String newsCategory, ArrayList<NewsModal> newsModalArrayList) {
        this.newsCategory = newsCategory;
        this.newsModalArrayList = newsModalArrayList;

        // default we are setting expanded as false.
        this.expanded = false;
    }

    // getter and setter methods.
    public boolean isExpanded() {
        return expanded;
    }

    public void setExpanded(boolean expanded) {
        this.expanded = expanded;
    }

    public String getNewsCategory() {
        return newsCategory;
    }

    public void setNewsCategory(String newsCategory) {
        this.newsCategory = newsCategory;
    }

    public ArrayList<NewsModal> getNewsModalArrayList() {
        return newsModalArrayList;
    }

    public void setNewsModalArrayList(ArrayList<NewsModal> newsModalArrayList) {
        this.newsModalArrayList = newsModalArrayList;
    }

}
```

**第五步:为我们的新闻项目创建布局文件**

导航至 **app > res >布局>右键点击>新建>布局资源文件**并命名为 **news_rv_item** 并添加以下代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.cardview.widget.CardView 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="3dp"
    android:backgroundTint="@color/purple_200"
    app:cardCornerRadius="1dp">

    <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

        <!--text view for displaying news title-->
        <TextView
            android:id="@+id/idTVNewsTitle"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginStart="4dp"
            android:layout_marginTop="8dp"
            android:padding="4dp"
            android:text="News Title"
            android:textAllCaps="false"
            android:textColor="@color/white"
            android:textStyle="bold" />

        <!--text view for displaying news description-->
        <TextView
            android:id="@+id/idTVNewsDesc"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_below="@id/idTVNewsTitle"
            android:layout_marginStart="4dp"
            android:layout_marginTop="4dp"
            android:padding="4dp"
            android:text="News Desc"
            android:textColor="@color/white"
            android:textSize="12sp" />

    </RelativeLayout>

</androidx.cardview.widget.CardView>
```

**步骤 6:为新闻类别创建新的布局文件**

同样，创建另一个布局资源文件，并将其命名为 **news_categories_rv_item** ，并向其中添加以下代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.cardview.widget.CardView 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="3dp"
    app:cardCornerRadius="4dp">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical">

        <!--text view for displaying news category-->
        <TextView
            android:id="@+id/idTVCategory"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:padding="8dp"
            android:text="Category"
            android:textSize="15sp" />

        <androidx.cardview.widget.CardView
            android:id="@+id/idCVCategory"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:elevation="0dp"
            app:cardElevation="0dp">

            <!--recycler view for displaying news recycler view-->
            <androidx.recyclerview.widget.RecyclerView
                android:id="@+id/idRVNews"
                android:layout_width="match_parent"
                android:layout_height="wrap_content" />

        </androidx.cardview.widget.CardView>

    </LinearLayout>

</androidx.cardview.widget.CardView>
```

**第 7 步:创建新的适配器类，用于在新闻回收视图**中设置数据

创建另一个 Java 类，并将其命名为**newsvadapter**，并向其中添加以下代码。代码中添加了注释，以便更详细地了解。

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

public class NewsRVAdapter extends RecyclerView.Adapter<NewsRVAdapter.ViewHolder> {

    // variables for array list and context.
    private ArrayList<NewsModal> newsModalArrayList;
    private Context context;

    // creating a constructor.
    public NewsRVAdapter(ArrayList<NewsModal> newsModalArrayList, Context context) {
        this.newsModalArrayList = newsModalArrayList;
        this.context = context;
    }

    @NonNull
    @Override
    public NewsRVAdapter.ViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType) {
        // passing our layout file for displaying our card item
        return new NewsRVAdapter.ViewHolder(LayoutInflater.from(context).inflate(R.layout.news_rv_item, parent, false));

    }

    @Override
    public void onBindViewHolder(@NonNull NewsRVAdapter.ViewHolder holder, int position) {
        // on below line we are setting data to our ui components.
        NewsModal modal = newsModalArrayList.get(position);
        holder.newsDescTV.setText(modal.getNewsDesc());
        holder.newsTitleTV.setText(modal.getNewsTitle());
    }

    @Override
    public int getItemCount() {
        // returning the size of array list
        return newsModalArrayList.size();
    }

    public class ViewHolder extends RecyclerView.ViewHolder {

        // creating variables for our text view.
        private TextView newsTitleTV, newsDescTV;

        public ViewHolder(@NonNull View itemView) {
            super(itemView);
            // initializing our text view
            newsTitleTV = itemView.findViewById(R.id.idTVNewsTitle);
            newsDescTV = itemView.findViewById(R.id.idTVNewsDesc);
        }
    }
}
```