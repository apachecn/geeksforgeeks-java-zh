# 安卓中的 AdapterViewFlipper 示例

> 原文:[https://www . geeksforgeeks . org/adapterviewflipper-in-Android-with-example/](https://www.geeksforgeeks.org/adapterviewflipper-in-android-with-example/)

AdapterViewFlipper 类是 ViewAnimator 类的一个子类，用于在两个或多个视图之间翻转，这样一次只能显示一个视图。它通常用于幻灯片。它是过渡小部件的一个元素，有助于在视图上添加过渡。在屏幕上制作视图动画非常有用。AdapterViewFlipper 在两个或多个视图( [TextView](https://www.geeksforgeeks.org/textview-widget-in-android-using-java-with-examples/) 、 [ImageView](https://www.geeksforgeeks.org/imageview-in-kotlin/) 或任何布局)之间平滑切换，从而提供了一种通过适当的动画从一个视图过渡到另一个视图的方式。下面是 AdapterViewFlipper 的预览示例。

![AdapterViewFlipper](img/c36ca693b5406e47a12ba29916b4c1e6.png)

### **查看器和适配器查看器的区别**

[ViewFlipper](https://www.geeksforgeeks.org/how-to-add-viewflipper-in-android/) 和 AdapterViewFlipper 都是 ViewAnimator 的子类。ViewFlipper 最初用于显示所有固定的幻灯片视图。这意味着视图不会被回收。AdapterViewFlipper 使用适配器来填充数据(类似于[列表视图](https://www.geeksforgeeks.org/android-listview-in-java-with-example/) / [微调器](https://www.geeksforgeeks.org/spinner-in-android-using-java-with-example/) / [回收视图](https://www.geeksforgeeks.org/android-recyclerview/)等)，因此可以动态确定子视图，并且可以回收代表子视图的视图。所以 AdapterViewFlipper 用于显示所有子视图。因此，有回收视图和动态加载视图的空间。

### 创建适配器视图的步骤

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 [Java](https://www.geeksforgeeks.org/java/) 作为编程语言。

**步骤 2:** **使用 activity_main.xml 文件**

点击**Res->Layout->activity _ main . XML**并添加一个 TextView 来显示一个文本，添加 AdapterViewFlipper 来显示功能。下面是 **activity_main.xml** 文件的完整代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#fff"
    tools:context=".MainActivity">

    <!--Text view to display Global stats-->
    <TextView
        android:id="@+id/heading"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="The North"
        android:textSize="28sp"
        android:textAlignment="center"
        android:textColor="#000"
        android:textStyle="bold"/>

    <!--AdapterViewFlipper to display the functionality-->
    <AdapterViewFlipper
        android:id="@+id/adapterViewFlipper"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/heading"
        android:layout_marginTop="10dp"
        android:layout_centerHorizontal="true">
    </AdapterViewFlipper>

</RelativeLayout>
```

**步骤 3:** **创建另一个布局文件**

现在通过右键单击**RES->Layout->new->Layout 资源文件**创建另一个 XML layouts 文件，并将其命名为**custom _ adapter _ Layout . XML**。在这个文件中添加一个[图像视图](https://www.geeksforgeeks.org/imageview-in-kotlin/)和[文本视图](https://www.geeksforgeeks.org/textview-widget-in-android-using-java-with-examples/)在适配器中使用。下面是**custom _ adapter _ layout . XML**文件的完整代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<!--Relative Layout to display all the details-->
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:background="#fff">

    <!--Image view to display-->
    <ImageView
        android:id="@+id/image"
        android:layout_width="match_parent"
        android:layout_height="250dp"
        android:layout_alignParentTop="true" />

    <!--Text view to display stats coordinate with image-->
    <TextView
        android:id="@+id/name"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/image"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="5dp"
        android:textColor="#000"
        android:textSize="20sp" />

</RelativeLayout>
```

**第四步:使用 MainActivity.java 文件**

打开 MainActivity 并添加以下代码以启动 AdapterViewFlipper。首先创建两个数组，一个用于图像，另一个用于名称。创建后，设置适配器以填充视图中的数据。最后设置自动开始和翻转间隔时间，以便 AdapterViewFlipper 在视图之间切换，当前视图将退出，下一个视图将在给定的时间间隔后进入。以下是**MainActivity.java**文件的完整代码。请参考代码中的注释以了解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.content.Context;
import android.os.Bundle;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.AdapterViewFlipper;
import android.widget.BaseAdapter;
import android.widget.ImageView;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    AdapterViewFlipper adapterViewFlipper;

    int[] IMAGES = {
            R.drawable.ldeosai,
            R.drawable.lakedudipatsar,
            R.drawable.lrama,
            R.drawable.lakekachura
    };

    String[] NAMES = {
            "Deosai National Park",
            "Lake Dudipatsar",
            "Rama Meadows",
            "Lower Kachura Lake"
    };

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Link those objects with their respective id's
        // that we have given in .XML file
        adapterViewFlipper = (AdapterViewFlipper) findViewById(R.id.adapterViewFlipper);
        CustomAdapter customAdapter = new CustomAdapter(getApplicationContext(), NAMES, IMAGES);
        adapterViewFlipper.setAdapter(customAdapter);
        adapterViewFlipper.setFlipInterval(2600);
        adapterViewFlipper.setAutoStart(true);
    }
}

class CustomAdapter extends BaseAdapter {
    Context context;
    int[] images;
    String[] names;
    LayoutInflater inflater;

    public CustomAdapter(Context applicationContext, String[] names, int[] images) {
        this.context = applicationContext;
        this.images = images;
        this.names = names;
        inflater = (LayoutInflater.from(applicationContext));
    }

    @Override
    public int getCount() {
        return names.length;
    }

    @Override
    public Object getItem(int position) {
        return null;
    }

    @Override
    public long getItemId(int position) {
        return 0;
    }

    @Override
    public View getView(int position, View view, ViewGroup parent) {
        view = inflater.inflate(R.layout.custom_adapter_layout, null);

        // Link those objects with their respective id's
        // that we have given in .XML file
        TextView name = (TextView) view.findViewById(R.id.name);
        ImageView image = (ImageView) view.findViewById(R.id.image);

        // Set the data in text view
        name.setText(names[position]);

        // Set the image in Image view
        image.setImageResource(images[position]);
        return view;
    }
}
```

### **输出:在仿真器上运行**

现在用 USB 电缆或仿真器连接您的设备，并启动应用程序。您将看到图像的自适应翻转，它将在某毫秒后发生变化。

<video class="wp-video-shortcode" id="video-484338-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200830211019/adapter.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200830211019/adapter.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200830211019/adapter.mp4)</video>