# 安卓中的协调器表格布局

> 原文:[https://www . geeksforgeeks . org/coordinator-tablayout-in-Android/](https://www.geeksforgeeks.org/coordinator-tablayout-in-android/)

许多应用程序使用表格布局，其中我们必须在表格布局上方显示一个图像。这种类型的用户界面设计主要出现在餐厅应用程序和许多其他应用程序中。在本文中，我们将研究在我们的安卓应用程序中使用安卓工作室使用协调器 TabLayout 实现相同类型的视图。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将显示图像，在图像下方，我们将显示一个表格。在该表格中，我们将在该列表中显示与课程相关的详细信息，并在其中显示不同类型的课程。下面给出了一个示例视频，以了解我们将在本文中做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-598375-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210421231432/20210421_231117.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210421231432/20210421_231117.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210421231432/20210421_231117.mp4)</video>

### **安卓中添加协调器表布局的分步实现**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第 2 步:在构建.梯度**中添加使用协调器布局的依赖关系

导航至 **Gradle 脚本> build.gradle(模块:app)** 并在依赖项部分添加以下依赖项。

```
implementation 'cn.hugeterry.coordinatortablayout:coordinatortablayout:1.2.2'
```

添加依赖关系后，现在同步项目，我们将准备工作。

**步骤 3:更新 themes.xml 文件。**

导航到**应用程序> res >值> themes.xml** 并将主题更改为**无菜单栏**。参考以下代码。

## 可扩展标记语言

```
<resources xmlns:tools="http://schemas.android.com/tools">
    <!-- Base application theme with No Action Bar. -->
    <style name="Theme.GFG" parent="Theme.MaterialComponents.DayNight.NoActionBar">
        <!-- Primary brand color. -->
        <item name="colorPrimary">@color/purple_500</item>
        <item name="colorPrimaryVariant">@color/purple_700</item>
        <item name="colorOnPrimary">@color/white</item>
        <!-- Secondary brand color. -->
        <item name="colorSecondary">@color/teal_200</item>
        <item name="colorSecondaryVariant">@color/teal_700</item>
        <item name="colorOnSecondary">@color/black</item>
        <!-- Status bar color. -->
        <item name="android:statusBarColor" tools:targetApi="l">?attr/colorPrimaryVariant</item>
        <!-- Customize your theme here. -->
    </style>
</resources>
```

**第 4 步:使用 activity_main.xml 文件**

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

    <!--creating a coordinator layout on below line-->
    <cn.hugeterry.coordinatortablayout.CoordinatorTabLayout
        android:id="@+id/coordinatortablayout"
        android:layout_width="match_parent"
        android:layout_height="match_parent">

        <!--creating a view pager on below line-->
        <androidx.viewpager.widget.ViewPager
            android:id="@+id/vp"
            android:layout_width="match_parent"
            android:layout_height="match_parent"
            app:layout_behavior="@string/appbar_scrolling_view_behavior" />

    </cn.hugeterry.coordinatortablayout.CoordinatorTabLayout>

</RelativeLayout>
```

**第 5 步:创建一个片段来显示我们的课程详情**

导航到**应用程序> res >布局>右键单击它>新建>空白片段**并将其命名为**主片段**，然后单击创建创建新片段。创建此片段后，现在导航到**应用程序> res >布局>片段 _home** ，并向其中添加以下代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".HomeFragment">

    <!--creating a recycler view for displaying the course content-->
    <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/recyclerview"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />

</RelativeLayout>
```

**第六步:为回收视图**创建新的布局文件

导航至 **app > res >布局>右键单击>新建>布局资源文件**并将其命名为 **item_main** 并添加以下代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="wrap_content">

    <!--text view for displaying course contents-->
    <TextView
        android:id="@+id/tv_num"
        android:layout_width="match_parent"
        android:layout_height="50dp"
        android:gravity="center"
        android:text="1" />

</LinearLayout>
```

**第 7 步:创建一个适配器类，用于将数据设置为回收视图项目**

导航到**应用> java >你的应用的包名>右键点击它>新建> Java 类**并将其命名为 **RecyclerAdapter** 并添加下面的代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.Context;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.TextView;

import androidx.annotation.NonNull;
import androidx.recyclerview.widget.RecyclerView;

import java.util.List;

public class RecyclerAdapter extends RecyclerView.Adapter<RecyclerAdapter.MyViewHolder> {

    // creating variables for context and list.
    private Context mContext;
    private List<String> mDatas;

    // creating constructor.
    public RecyclerAdapter(Context context, List<String> datas) {
        mContext = context;
        mDatas = datas;
    }

    @NonNull
    @Override
    public RecyclerAdapter.MyViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType) {
        // inflating layout on below line.
        return new MyViewHolder(LayoutInflater.from(
                mContext).inflate(R.layout.item_main, parent, false));
    }

    @Override
    public void onBindViewHolder(@NonNull RecyclerAdapter.MyViewHolder holder, int position) {
        // setting data to text view on below line.
        holder.tv.setText(mDatas.get(position));
    }

    @Override
    public int getItemCount() {
        // returning the size of array list.
        return mDatas.size();
    }

    public class MyViewHolder extends RecyclerView.ViewHolder {
        // creating variables for text view.
        TextView tv;

        public MyViewHolder(@NonNull View itemView) {
            super(itemView);
            // initializing the text view.
            tv = (TextView) itemView.findViewById(R.id.tv_num);
        }
    }
}
```