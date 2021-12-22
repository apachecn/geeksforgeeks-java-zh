# 安卓中的 dropdowview

> 原文:[https://www.geeksforgeeks.org/dropdownview-in-android/](https://www.geeksforgeeks.org/dropdownview-in-android/)

**dropbdowview**是大多数安卓应用中使用的另一个令人兴奋的功能。这是以动画形式表示菜单和其他选项的独特方式。我们可以在 DropDownView 的一个标题下看到选项列表。在本文中，我们将看到如何在安卓中实现 DropDownView。下面给出了一个 GIF 示例，来了解一下我们将在本文中做什么。注意，我们将使用 **Java** 语言来实现这个项目。

![DropDownView in Android Sample GIF](img/1570e058d4ba727aab7150a9ff16c449.png)

### DropDownView 的应用

*   以动画形式表示数据的独特方式。
*   使导航变得容易，并在一个标题下找到许多选项。
*   大选项可以轻松显示。

### DropDownView 的属性

<figure class="table">

| 

属性

 | 

描述

 |
| --- | --- |
| **布局 _ 宽度** | 赋予布局宽度。 |
| **布局 _ 高度** | 给布局赋予高度。 |
| **容器背面颜色** | 给容器赋予背景色。 |
| **叠加颜色** | 给覆盖颜色。 |

</figure>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:添加依赖和 JitPack 存储库**

导航到**渐变脚本>构建.渐变(模块:应用)**，并在依赖项部分添加以下依赖项。

> 实现' com . github . AnthonyFermin:DropDownView:1 . 0 . 1 '

将 JitPack 存储库添加到构建文件中。将其添加到 allprojects{ }部分内存储库末尾的 root build.gradle 中。

> *所有项目{*
> 
> *存储库{*
> 
> *……*
> 
> *maven { URL " https://jitpack . io " }*
> 
> *}*
> 
> *}*

添加这个依赖项后，同步您的项目，现在我们将开始实现它。

**步骤 3:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <!--DropDown Menu-->
    <com.anthonyfdev.dropdownview.DropDownView
        android:id="@+id/drop_down_view"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        app:containerBackgroundColor="@color/purple_200"
        app:overlayColor="#EEEEEE" />

</LinearLayout>
```

**第四步:新建布局资源文件**

导航到**应用程序> res >布局** **>右键单击>新建>布局资源文件**，并将文件命名为**页眉**和**页脚**。

**下面是头文件的代码:**

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="10dp">

    <!--Header for drop down-->
    <TextView
        android:id="@+id/textView2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Amazing" />

</LinearLayout>
```

**以下是**T2T4 文件的代码

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:padding="10dp">

    <!--Items in drop down-->
    <TextView
        android:id="@+id/textView"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Awesome" />

    <TextView
        android:id="@+id/textView1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="10dp"
        android:text="Line 1" />

    <TextView
        android:id="@+id/textView2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="10dp"
        android:text="Line 2" />

    <TextView
        android:id="@+id/textView3"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Line 3" />

    <TextView
        android:id="@+id/textView4"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Line 4" />

    <TextView
        android:id="@+id/textView5"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Line 5" />

    <TextView
        android:id="@+id/textView6"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Line 6" />

    <TextView
        android:id="@+id/textView7"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Line 7" />

</LinearLayout>
```

**第五步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.os.Bundle;
import android.view.LayoutInflater;
import android.view.View;
import android.widget.Button;

import androidx.appcompat.app.AppCompatActivity;

import com.anthonyfdev.dropdownview.DropDownView;

public class MainActivity extends AppCompatActivity {

    Button button;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Drop down menu given using id
        DropDownView dropDownView = (DropDownView) findViewById(R.id.drop_down_view);
        View collapsedView = LayoutInflater.from(this).inflate(R.layout.header, null, false);
        View expandedView = LayoutInflater.from(this).inflate(R.layout.footer, null, false);

        dropDownView.setHeaderView(collapsedView);
        dropDownView.setExpandedView(expandedView);

        collapsedView.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // on click the drop down
                // will open or close
                if (dropDownView.isExpanded()) {
                    dropDownView.collapseDropDown();
                } else {
                    dropDownView.expandDropDown();
                }
            }
        });
    }
}
```

现在点击**运行**选项**构建梯度**需要一些时间。之后，您将获得如下所示的设备输出。

### **输出:**

<video class="wp-video-shortcode" id="video-550638-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210124143314/Screenrecorder-2021-01-24-14-29-19-301.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210124143314/Screenrecorder-2021-01-24-14-29-19-301.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210124143314/Screenrecorder-2021-01-24-14-29-19-301.mp4)</video>