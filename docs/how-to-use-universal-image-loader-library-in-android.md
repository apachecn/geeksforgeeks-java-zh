# 如何在安卓系统中使用通用图像加载器库？

> 原文:[https://www . geeksforgeeks . org/如何使用-通用-图像加载器-安卓库/](https://www.geeksforgeeks.org/how-to-use-universal-image-loader-library-in-android/)

**UIL(通用图像加载器)**是一个类似于[毕加索](https://www.geeksforgeeks.org/image-loading-caching-library-android-set-1/)和[格莱德](https://www.geeksforgeeks.org/image-loading-caching-library-android-set-2/)的库，执行从任何网页网址加载图像到安卓的 [ImageView](https://www.geeksforgeeks.org/imageview-in-kotlin/) 中。创建这个图像加载库是为了提供一个强大、灵活和可定制的解决方案，从服务器加载安卓系统中的图像。这个图像加载库是由一个独立开发人员创建的，它出现在 GitHub 的顶部列表中。UIL(通用图像加载器)库的特点:

*   该库提供多线程图像加载。
*   图像缓存可以在内存和用户设备中完成。
*   监听加载过程(包括下载进度)。
*   许多可定制的功能可用于每次显示图像调用。

> 注意，我们将使用 **Java** 语言来实现这个项目。

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在 build.gradle 文件中添加 UIL 图像库的依赖项。**

导航到梯度脚本，然后导航到构建.梯度(模块)级别。在依赖项部分的 [build.gradle](https://www.geeksforgeeks.org/android-build-gradle/) 文件中添加以下行。

> 实现“com . nostra 13 . universal image loader:universal-image-loader:1 . 9 . 5”

**第三步:在 AndroidManifest.xml 文件**中添加互联网权限

导航至**应用程序>清单**打开清单文件。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.gtappdevelopers.camviewlibrary">

    <!--Permission for internet-->
    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.CamViewLibrary">
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>
```

**第 4 步:在 activity_main.xml.** 中创建新的 ImageView

导航到**应用程序> res >布局**打开 **activity_main.xml** 文件。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--Image view for loading our image-->
    <ImageView
        android:id="@+id/idImageView"
        android:layout_width="200dp"
        android:layout_height="200dp"
        android:layout_centerInParent="true"
        android:contentDescription="@string/app_name" />

</RelativeLayout>
```

**第五步:初始化你的 ImageView 并在 MainActivity.java 文件**中使用 UIL(通用图像加载器)

导航到**应用程序> java >您的应用程序包名称>MainActivity.java**文件。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.os.Bundle;
import android.widget.ImageView;
import androidx.appcompat.app.AppCompatActivity;
import com.nostra13.universalimageloader.core.DisplayImageOptions;
import com.nostra13.universalimageloader.core.ImageLoader;
import com.nostra13.universalimageloader.core.ImageLoaderConfiguration;

public class MainActivity extends AppCompatActivity {

    private ImageView img;
    DisplayImageOptions options;
    ImageLoader imageLoader;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initialize image loader before using
        imageLoader = ImageLoader.getInstance();
        imageLoader.init(ImageLoaderConfiguration.createDefault(getApplicationContext()));

        // initialize imageview from activity_main.xml
        img = findViewById(R.id.idImageView);

        // URL for our image that we have to load..
        String imageUri = "https://www.geeksforgeeks.org/wp-content/uploads/gfg_200X200-1.png";

        // with below method we are setting display option for our image..
        options = new DisplayImageOptions.Builder()

                // stub image will display when your image is loading
                .showStubImage(R.drawable.ic_launcher_foreground)

                // below image will be displayed when the image url is empty
                .showImageForEmptyUri(R.drawable.ic_launcher_background)

                // cachememory method will caches the image in users external storage
                .cacheInMemory()

                // cache on disc will caches the image in users internal storage
                .cacheOnDisc()

                // build will build the view for displaying image..
                .build();
        // below method will display image inside our image view..
        imageLoader.displayImage(imageUri, img, options, null);
    }
}
```

> **注意:**所有可抽词都在[可抽词文件夹](https://www.geeksforgeeks.org/how-to-add-image-to-drawable-folder-in-android-studio/)中。您可以在可绘制文件夹中添加可绘制内容。访问可绘制文件夹。导航到应用程序>资源>可绘制区>这个文件夹包含了你所有的可绘制区。

### **输出:**

![UIL Output](img/e22045630503dfac60177d84e9c07d7a.png)