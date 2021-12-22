# 如何使用 Firebase ML 工具包在安卓系统中标注图像？

> 原文:[https://www . geeksforgeeks . org/如何使用 firebase-ml-kit/在 android 中标记图像/](https://www.geeksforgeeks.org/how-to-label-image-in-android-using-firebase-ml-kit/)

我们已经在安卓中看到了许多应用程序，在这些应用程序中，我们将检测图像中存在的对象，无论它是否是任何对象。在本文中，我们将看一下使用 **Firebase ML 工具包**在 Android 中实现图像标注。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，在其中我们将捕获任何对象的图像，并从该图像中，我们将以正确的级别检测图像中存在的对象。下面给出一个视频的样本，来了解一下我们在这篇文章中要做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-562032-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210219104620/Screenrecorder-2021-02-19-10-43-08-472.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210219104620/Screenrecorder-2021-02-19-10-43-08-472.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210219104620/Screenrecorder-2021-02-19-10-43-08-472.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:将你的应用连接到 Firebase**

在 Android Studio 中创建新项目后，将您的应用程序连接到 Firebase。用于将您的应用程序连接到 firebase。导航到顶部栏上的工具。之后点击 Firebase。右侧将打开一个新窗口。在该窗口中，单击 Firebase ML，然后单击在安卓系统中使用 Firebase ML 工具包。你可以看到截图下面的选项。

![](img/8bb9fea32a255b2eb794f1edcbd4658b.png)

点击下一屏的这个选项后，点击**连接到 Firebase** 选项，将你的应用连接到 Firebase。

**第三步:添加语言翻译的依赖项，建立. gradle 文件**

导航至 **Gradle 脚本> build.gradle(模块:app)** 并在依赖项部分添加以下依赖项。

> firebase 核心的依赖关系。
> 
> 实现' com . Google . firebase:firebase-core:15 . 0 . 2 '
> 
> // Firebase ML 依赖项
> 
> 实现' com . Google . firebase:firebase-ml-vision:24 . 0 . 3 '
> 
> 实现' com . Google . firebase:firebase-ml-vision-image-label-model:20 . 0 . 1 '

**第四步:在你的安卓应用和安卓清单文件**中添加访问互联网和元数据的权限

导航到**应用程序> AndroidManifest.xml** 文件，并在其中添加以下代码。代码中添加了注释，以便更详细地了解。

## 可扩展标记语言

```
<!-- below line is use to add camera feature in our app -->
<uses-feature
  android:name="android.hardware.camera"
  android:required="true" />

<!-- permission for internet -->
<uses-permission android:name="android.permission.INTERNET" />
```

在您的应用程序标签中添加下面的行。

## 可扩展标记语言

```
<meta-data
  android:name="com.google.firebase.ml.vision.DEPENDENCIES"
  android:value="label" />
```

下面是 **AndroidManifest.xml** 文件的完整代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.labelimage">

    <!-- below line is use to add camera feature in our app -->
    <uses-feature
        android:name="android.hardware.camera"
        android:required="true" />

    <!-- permission for internet -->
    <uses-permission android:name="android.permission.INTERNET" />

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/Theme.LabelImage">
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />

                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>

        <meta-data
            android:name="com.google.firebase.ml.vision.DEPENDENCIES"
            android:value="label" />

    </application>

</manifest>
```

**第 5 步:使用 activity_main.xml 文件**

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

    <!--image view for displaying our image-->
    <ImageView
        android:id="@+id/image"
        android:layout_width="match_parent"
        android:layout_height="300dp"
        android:layout_alignParentTop="true"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="10dp"
        android:scaleType="centerCrop" />

    <LinearLayout
        android:id="@+id/idLLButtons"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/image"
        android:orientation="horizontal">

        <!--button for capturing our image-->
        <Button
            android:id="@+id/snapbtn"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_margin="5dp"
            android:layout_marginTop="30dp"
            android:layout_weight="1"
            android:text="SNAP"
            android:textSize="25dp"
            android:textStyle="bold" />

        <!--button for detecting the objects-->
        <Button
            android:id="@+id/labelBtn"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_margin="5dp"
            android:layout_marginTop="30dp"
            android:layout_weight="1"
            android:text="Label"
            android:textSize="25dp"
            android:textStyle="bold" />

    </LinearLayout>

    <!--recycler view for displaying the list of objects-->
    <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/idRVResults"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idLLButtons" />

</RelativeLayout>
```

**第 6 步:创建一个模态类来存储我们的数据**

导航到**应用程序> java >你的应用程序的包名>右键单击它>新建> Java 类**并将你的类命名为**数据模式**，并在其中添加下面的代码。在代码中添加注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class DataModal {

    // variables for our 
    // string and confidence.
    private String result;
    private float confidence;

    // constructor
    public DataModal(String result, float confidence) {
        this.result = result;
        this.confidence = confidence;
    }

    // getter and setter methods
    public float getConfidence() {
        return confidence;
    }

    public void setConfidence(float confidence) {
        this.confidence = confidence;
    }

    public String getResult() {
        return result;
    }

    public void setResult(String result) {
        this.result = result;
    }

}
```

**第 7 步:创建一个布局文件来显示我们的回收视图项目**

导航至 **app > res >布局>右键单击>新建>布局资源文件**并将其命名为 **result_rv_item** 并添加以下代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.cardview.widget.CardView 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="5dp"
    android:elevation="8dp"
    app:cardCornerRadius="8dp">

    <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="3dp">

        <!--text view for our result-->
        <TextView
            android:id="@+id/idTVResult"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:padding="3dp"
            android:text="Result"
            android:textColor="@color/black" />

        <!--text view for our confidence-->
        <TextView
            android:id="@+id/idTVConfidence"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_below="@id/idTVResult"
            android:padding="3dp"
            android:text="Confidence"
            android:textColor="@color/black" />

    </RelativeLayout>

</androidx.cardview.widget.CardView>
```