# 安卓中的重力视图

> 原文:[https://www.geeksforgeeks.org/gravityview-in-android/](https://www.geeksforgeeks.org/gravityview-in-android/)

在本文中，我们将展示 android 中的 GravityView。在本文中，我们将看到重力对图像的影响。当我们移动手机时，我们会看到图像的不同部分。这里我们将使用[水平滚动视图](https://www.geeksforgeeks.org/horizontalscrollview-in-kotlin/)，所以我们将水平移动我们的手机。在下面的视频中，你可以想象这是如何发生的

<video class="wp-video-shortcode" id="video-589861-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210403102327/gravity.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210403102327/gravity.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210403102327/gravity.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:** **将此添加到 build.gradle 文件**

```
implementation 'co.gofynd.library:gravity-view:1.0'
```

**步骤 3:使用 activity_main.xml 文件**

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

    <HorizontalScrollView
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

        <ImageView
            android:id="@+id/imageView"
            android:layout_width="match_parent"
            android:layout_height="wrap_content" />
    </HorizontalScrollView>

</RelativeLayout>
```

**步骤 4:** **处理 MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码

```
if(!gravityView.deviceSupported()){
            // show the error / imageView
            Toast.makeText(GravityViewActivity.this,"Not Supported",Toast.LENGTH_LONG).show();
        }
        else
        {
          // if device is supported then we will add the image
          // in imageview and will show the image using graviety view
          gravityView.setImage(imageView,R.drawable.image).center();
}
```

以下是**MainActivity.java**文件的代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.os.Bundle;
import android.widget.ImageView;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

import co.gofynd.gravityview.GravityView;

public class MainActivity extends AppCompatActivity {

    GravityView gravityView;
    ImageView imageView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        imageView = findViewById(R.id.imageView);
        gravityView = GravityView.getInstance(this);
        if (!gravityView.deviceSupported()) {
            // show the error
            Toast.makeText(MainActivity.this, "Not Supported", Toast.LENGTH_LONG).show();
        } else {
            // if device is supported then we will add the image
            // in imageview and will show the image using graviety view
            gravityView.setImage(imageView, R.drawable.image).center();
        }
    }

    @Override
    protected void onStop() {
        super.onStop();
        gravityView.unRegisterListener();
    }

    @Override

    protected void onResume() {
        super.onResume();
        gravityView.registerListener();
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-589861-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210403102327/gravity.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210403102327/gravity.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210403102327/gravity.mp4)</video>