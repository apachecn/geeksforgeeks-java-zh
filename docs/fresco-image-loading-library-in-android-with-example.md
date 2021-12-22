# 安卓壁画图像加载库示例

> 原文:[https://www . geesforgeks . org/fresco-image-loading-library-in-Android-with-example/](https://www.geeksforgeeks.org/fresco-image-loading-library-in-android-with-example/)

Fresco 是 Android 中著名的从 URL 加载图像的库之一。这是一个强大的库，用于显示和管理来自网址的图像。该库可以从用户的设备、服务器和其他本地来源加载图像。这个库最重要的特性是，当来自 URL 的图像需要很长时间加载时，显示一个占位符图像。除此之外，当图像由于任何问题而无法显示时，我们可以使用错误图像。为了节省数据和中央处理器，该库使用三级缓存，其中两级在内存中，一级在内部存储中。可以查看 [Fresco](https://frescolib.org/) 的官方文档。

### 该库的实现

下面给出了一个示例图像，以了解我们将在本文中做什么。注意，我们将使用 **Java** 语言来实现这个项目。

![Fresco Image Loading Library in Android](img/e22045630503dfac60177d84e9c07d7a.png)

### 逐步实施

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考如何在安卓工作室创建/启动新项目。注意选择 **Java** 作为编程语言。

**第二步:在 build.gradle 文件中添加 Fresco 图像库的依赖关系**

导航到梯度脚本，然后导航到构建.梯度(模块)级别。在 dependencies 部分的 build.gradle 文件中添加以下行。

> 实现' com . Facebook . fresco:fresco:2 . 3 . 0 '

还有，

**在应用程序项目的 build.gradle 文件中添加 google repository，如果默认情况下它不在那里**

> buildscript {
> 
> 存储库{
> 
> 谷歌()
> 
> mavenuentral _)
> 
> }

所有的 Jetpack 组件都可以在 Google Maven 存储库中找到，包括在 build.gradle 文件中

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

**第三步:在 AndroidManifest.xml 文件**中添加互联网权限

导航至**应用程序>清单**打开清单文件。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.gtappdevelopers.frescoimageloading">

    <!--Permission for internet-->
    <uses-permission android:name="android.permission.INTERNET" />
    <!--Permission for Network State-->
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.FrescoImageLoading">
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>

</manifest>
```

**第四步:在你的 activity_main.xml** 中创建新的 SimpleDraweeView

导航到**应用程序> res >布局**打开 activity_main.xml 文件。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--To implement ImageView-->
    <!--Constraints are given to align image
        centrally of the view-->
    <!--Scale type centre crop is given to
        crop image centrally-->
    <com.facebook.drawee.view.SimpleDraweeView
        android:id="@+id/idSDimage"
        android:layout_width="match_parent"
        android:layout_height="300dp"
        android:layout_margin="10dp"
        android:scaleType="centerCrop"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

**第五步:初始化并使用 MainActivity.java 文件**中的 SimpleDraweeView

导航到**应用程序> java >你的应用程序包名称>MainActivity.java fil**e .下面是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.net.Uri;
import android.os.Bundle;
import androidx.appcompat.app.AppCompatActivity;
import com.facebook.drawee.backends.pipeline.Fresco;
import com.facebook.drawee.view.SimpleDraweeView;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        // initialize Fresco before setting view.
        Fresco.initialize(this);
        setContentView(R.layout.activity_main);

        // below line is having image url to be added..
        Uri imageUri = Uri.parse("https://www.geeksforgeeks.org/wp-content/uploads/gfg_200X200-1.png");
        SimpleDraweeView draweeView = (SimpleDraweeView) findViewById(R.id.idSDimage);
        draweeView.setImageURI(imageUri);
    }
}
```

**输出:**

> **注意:**如果你更新到 Android Studio 4，你可能会在构建项目时遇到这个错误(NDK at ~/Library/Android/SDK/ndk-bundle 没有 source.properties 文件)。请参考[本](https://stackoverflow.com/questions/64372383/ndk-at-library-android-sdk-ndk-bundle-did-not-have-a-source-properties-file)修复错误。

![](img/e22045630503dfac60177d84e9c07d7a.png)