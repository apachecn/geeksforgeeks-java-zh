# 安卓中使用可视寻呼机的图像滑块

> 原文:[https://www . geesforgeks . org/image-slider-in-Android-using-view pager/](https://www.geeksforgeeks.org/image-slider-in-android-using-viewpager/)

说起 [安卓 app](https://www.geeksforgeeks.org/top-programming-languages-for-android-app-development/)，首先想到的就是综艺。有太多种类的安卓应用为用户提供了漂亮的动态用户界面。其中一个功能是使用左右滑动在安卓应用中导航，而不是点击 [按钮](https://www.geeksforgeeks.org/button-in-kotlin/) 。它不仅看起来更简单和优雅，而且为用户提供了方便的访问。有很多应用使用这个扫取功能来扫取应用中的不同活动。比如流行的聊天应用 Snapchat，用它刷过镜头，聊过、和故事。这里我们来讨论一下如何使用 [视图页面](https://developer.android.com/reference/androidx/viewpager/widget/ViewPager) 创建图像滑块。ViewPager 是 Java 中[](https://www.geeksforgeeks.org/java/)的一个类，说明是与 [连用的](https://www.geeksforgeeks.org/introduction-fragments-android/) 的片段。主要用于设计应用的 UI。下面给出了一个 GIF 示例，来了解一下和在本文中我们要做什么。

![Image slider](img/e02b41d83670e0b4c81feb65693599f0.png)

### 在安卓系统中创建图像滑块的步骤

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 [Java](https://www.geeksforgeeks.org/java/) 作为编程语言。

**第二步:设计 UI**

*   下面是 **activity_main.xml** 文件的代码。我们只添加了一个**可视寻呼机**来显示图像。下面是 **activity_main.xml** 文件的完整代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

  <!-- viewpager to show images -->
  <androidx.viewpager.widget.ViewPager
      android:id="@+id/viewPagerMain"
      android:layout_width="match_parent"
      android:layout_height="match_parent"/>

</RelativeLayout>
```

*   在**应用程序- > res - >布局**文件夹内创建一个新的**布局资源文件项目. xml** 。仅添加一个[图像视图](https://www.geeksforgeeks.org/imageview-in-kotlin/)。下面是 **item.xml** 文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <!-- image viwer to view the images -->
    <ImageView
        android:id="@+id/imageViewMain"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>

</LinearLayout>
```

**第三步:编码部分**

*   首先，为**可视寻呼机**创建一个**适配器**，并将其命名为**可视寻呼机适配器**类下面是**ViewPagerAdapter.java**类的完整代码。注释被添加到代码中，以理解代码的每一行。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.content.Context;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.ImageView;
import android.widget.LinearLayout;
import androidx.annotation.NonNull;
import androidx.viewpager.widget.PagerAdapter;
import java.util.Objects;

class ViewPagerAdapter extends PagerAdapter {

    // Context object 
    Context context;

    // Array of images
    int[] images;

    // Layout Inflater
    LayoutInflater mLayoutInflater;

    // Viewpager Constructor 
    public ViewPagerAdapter(Context context, int[] images) {
        this.context = context;
        this.images = images;
        mLayoutInflater = (LayoutInflater) context.getSystemService(Context.LAYOUT_INFLATER_SERVICE);
    }

    @Override
    public int getCount() {
        // return the number of images
        return images.length;
    }

    @Override
    public boolean isViewFromObject(@NonNull View view, @NonNull Object object) {
        return view == ((LinearLayout) object);
    }

    @NonNull
    @Override
    public Object instantiateItem(@NonNull ViewGroup container, final int position) {
        // inflating the item.xml 
        View itemView = mLayoutInflater.inflate(R.layout.item, container, false);

        // referencing the image view from the item.xml file 
        ImageView imageView = (ImageView) itemView.findViewById(R.id.imageViewMain);

        // setting the image in the imageView
        imageView.setImageResource(images[position]);

        // Adding the View
        Objects.requireNonNull(container).addView(itemView);

        return itemView;
    }

    @Override
    public void destroyItem(ViewGroup container, int position, Object object) {

        container.removeView((LinearLayout) object);
    }
}
```

*   为**视图寻呼机**创建**适配器**后，从 XML 中引用**视图寻呼机**，并在**MainActivity.java**文件中为其设置适配器。创建一个包含图像的整数数组，我们将在视图页面中显示这些图像。以下是****MainActivity.java**文件的完整代码。注释被添加到代码中，以理解代码的每一行。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
import androidx.appcompat.app.AppCompatActivity;
import androidx.viewpager.widget.ViewPager;
import android.os.Bundle;

public class MainActivity extends AppCompatActivity {

    // creating object of ViewPager
    ViewPager mViewPager;

    // images array
    int[] images = {R.drawable.a1, R.drawable.a2, R.drawable.a3, R.drawable.a4,
                    R.drawable.a5, R.drawable.a6, R.drawable.a7, R.drawable.a8};

    // Creating Object of ViewPagerAdapter
    ViewPagerAdapter mViewPagerAdapter;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Initializing the ViewPager Object
        mViewPager = (ViewPager)findViewById(R.id.viewPagerMain);

        // Initializing the ViewPagerAdapter
        mViewPagerAdapter = new ViewPagerAdapter(MainActivity.this, images);

        // Adding the Adapter to the ViewPager
        mViewPager.setAdapter(mViewPagerAdapter);
    }
}
```

### ****输出:在仿真器上运行****

**<video class="wp-video-shortcode" id="video-484762-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200910081117/image-slider-using-view-pager-in-android-studio.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200910081117/image-slider-using-view-pager-in-android-studio.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200910081117/image-slider-using-view-pager-in-android-studio.mp4)</video>**

****附加链接:****

*   **从[链接](https://github.com/olyklohan/Image-Slider-using-ViewPager-in-Android-Studio)下载完整项目**
*   **下载[图片](https://github.com/olyklohan/Image-Slider-using-ViewPager-in-Android-Studio/tree/master/image_slider_using_viewpager_geeksforgeeks/geeksforgeeks/app/src/main/res/drawable)用于本项目**
*   **下载[应用程序](https://github.com/olyklohan/Image-Slider-using-ViewPager-in-Android-Studio/raw/master/app-debug.apk)**