# 如何在安卓中创建入职屏幕？

> 原文:[https://www . geeksforgeeks . org/如何在安卓中创建入职屏幕/](https://www.geeksforgeeks.org/how-to-create-an-onboarding-screen-in-android/)

大家好，极客们，今天我们将学习如何在 android studio 中将 Onboarding Screen 添加到我们的 android 应用程序中，以便为应用程序的用户提供更好的用户体验。

### 什么是入职屏幕？

入职屏幕可以理解为应用程序的虚拟解锁。用户经过一系列屏幕，最终将用户导向应用程序界面。入职屏幕的目标或目的:

*   欢迎用户并激发他们对未来应用的热情。
*   讲述应用程序的特性或功能。
*   允许用户注册或登录。
*   收集关于用户兴趣的信息(例如，当我们第一次打开 Spotify 应用程序时，它会要求用户选择他/她喜欢的歌手)。

### 我们将在本文中构建什么？

这是我们将在本文中创建的入职屏幕的示例视频。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-640015-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210702111706/WhatsApp-Video-2021-07-02-at-11.14.45.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210702111706/WhatsApp-Video-2021-07-02-at-11.14.45.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210702111706/WhatsApp-Video-2021-07-02-at-11.14.45.mp4)</video>

### 逐步实施

**第一步:创建新项目**

*   打开一个新项目。
*   我们将使用 Java 语言来处理空活动。保持所有其他选项不变。
*   您可以在方便的时候更改项目的名称。
*   将有两个名为 **activity_main.xml 和 MainActivity.java**的默认文件。

如果你不知道如何在安卓工作室创建新项目，那么你可以参考[如何在安卓工作室创建/启动新项目？](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)

**第 2 步:导航到构建脚本- > build.gradle(模块)文件，并在其中添加以下依赖项**

```
implementation 'com.ramotion.paperonboarding:paper-onboarding:1.1.3'
```

添加此依赖关系后，单击立即同步保存所有更改。

**步骤 3:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<!-- Here frame layout is used so that different 
     fragments of our onboarding screen can be
     changed within the same layout-->
<FrameLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/frame_layout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">
</FrameLayout>
```

**第四步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.graphics.Color;
import android.os.Bundle;

import androidx.appcompat.app.AppCompatActivity;
import androidx.fragment.app.FragmentManager;
import androidx.fragment.app.FragmentTransaction;

import com.ramotion.paperonboarding.PaperOnboardingFragment;
import com.ramotion.paperonboarding.PaperOnboardingPage;

import java.util.ArrayList;

public class MainActivity extends AppCompatActivity {
    private FragmentManager fragmentManager;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        fragmentManager = getSupportFragmentManager();

        // new instance is created and data is took from an 
        // array list known as getDataonborading
        final PaperOnboardingFragment paperOnboardingFragment = PaperOnboardingFragment.newInstance(getDataforOnboarding());
        FragmentTransaction fragmentTransaction = fragmentManager.beginTransaction();

        // fragmentTransaction method is used
        // do all the transactions or changes
        // between different fragments
        fragmentTransaction.add(R.id.frame_layout, paperOnboardingFragment);

        // all the changes are committed
        fragmentTransaction.commit();
    }

    private ArrayList<PaperOnboardingPage> getDataforOnboarding() {

        // the first string is to show the main title ,
        // second is to show the message below the
        // title, then color of background is passed ,
        // then the image to show on the screen is passed
        // and at last icon to navigate from one screen to other
        PaperOnboardingPage source = new PaperOnboardingPage("Gfg", "Welcome to GeeksForGeeks", Color.parseColor("#ffb174"),R.drawable.gfgimg, R.drawable.search);
        PaperOnboardingPage source1 = new PaperOnboardingPage("Practice", "Practice questions from all topics", Color.parseColor("#22eaaa"),R.drawable.practice_gfg, R.drawable.training);
        PaperOnboardingPage source2 = new PaperOnboardingPage("", " ", Color.parseColor("#ee5a5a"),R.drawable.gfg_contribute, R.drawable.contribution);

        // array list is used to store
        // data of onbaording screen
        ArrayList<PaperOnboardingPage> elements = new ArrayList<>();

        // all the sources(data to show on screens)
        // are added to array list
        elements.add(source);
        elements.add(source1);
        elements.add(source2);
        return elements;
    }
}
```

祝贺您，我们已经成功地为我们的应用程序制作了入职屏幕。最终输出如下所示。

**输出:**

<video class="wp-video-shortcode" id="video-640015-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210702111706/WhatsApp-Video-2021-07-02-at-11.14.45.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210702111706/WhatsApp-Video-2021-07-02-at-11.14.45.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210702111706/WhatsApp-Video-2021-07-02-at-11.14.45.mp4)</video>