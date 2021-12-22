# 如何在安卓中构建木琴应用？

> 原文:[https://www . geeksforgeeks . org/如何在安卓中构建木琴应用/](https://www.geeksforgeeks.org/how-to-build-a-xylophone-application-in-android/)

在本文中，我们将使用安卓系统中的 **Java 和 XML** 在木琴上构建一个项目。木琴最初是一种通过敲击一排木棒演奏的乐器。该应用程序将实现一种类似木琴的乐器，能够产生声音。我们将在这个应用程序中创建几个[按钮](https://www.geeksforgeeks.org/button-in-kotlin/)，当被敲击时，它们将充当乐器的按键。这将是一个单一的活动应用程序。下面给出了一个示例视频，以了解我们在本文中要做什么。

<video class="wp-video-shortcode" id="video-564063-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210225041940/Edited_20210225_041833.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210225041940/Edited_20210225_041833.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210225041940/Edited_20210225_041833.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在进入编码部分之前，你首先要做一些前置任务**

**添加颜色:**我们需要在资源目录的值中添加颜色。我们将为我们的按钮使用这些颜色。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="green1">#0F9D58</color>
    <color name="green2">#F21BB56A</color>
    <color name="green3">#E620C374</color>
    <color name="green4">#D929CF7E</color>
    <color name="green5">#CC2ED885</color>
    <color name="green6">#BF34E18D</color>
    <color name="green7">#B33FF39B</color>
</resources>
```

**添加关键音符**:将这些音频音符保存在 **app > res > raw** 目录中

> **注**:参考文章: [安卓工作室资源 Raw 文件夹](https://www.geeksforgeeks.org/resource-raw-folder-in-android-studio/)

*   [注 1](https://media.geeksforgeeks.org/wp-content/uploads/20210204222427/note1_c.wav)
*   [注 2](https://media.geeksforgeeks.org/wp-content/uploads/20210204222429/note2_d.wav)
*   [注 3](https://media.geeksforgeeks.org/wp-content/uploads/20210204222431/note3_e.wav)
*   [注 4](https://media.geeksforgeeks.org/wp-content/uploads/20210204222433/note4_f.wav)
*   [注 5](https://media.geeksforgeeks.org/wp-content/uploads/20210204222435/note5_g.wav)
*   [注 6](https://media.geeksforgeeks.org/wp-content/uploads/20210204222437/note6_a.wav)
*   [注 7](https://media.geeksforgeeks.org/wp-content/uploads/20210204222438/note7_b.wav)

**步骤 3:使用 activity_main.xml 文件**

XML 代码用于构建活动的结构及其样式部分。在这个 XML 文件中，我们将创建一个垂直方向的[线性布局](https://www.geeksforgeeks.org/linearlayout-and-its-important-attributes-with-examples-in-android/)。这将包含七个**按钮**，每个按钮具有不同的**点击**功能。按钮的宽度随着我们往下走而减小，使它看起来像木琴，也象征着按钮越小，音符声音越小。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:paddingBottom="@dimen/activity_vertical_margin"
    android:paddingLeft="@dimen/activity_horizontal_margin"
    android:paddingRight="@dimen/activity_horizontal_margin"
    android:paddingTop="@dimen/activity_vertical_margin"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <Button
        style="@style/KeyStyle"
        android:id="@+id/c_key"
        android:background="@color/green1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:onClick="c"/>

    <Button
        style="@style/KeyStyle"
        android:id="@+id/d_key"
        android:background="@color/green2"
        android:layout_marginLeft="5dp"
        android:layout_marginRight="5dp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:onClick="d"/>

    <Button
        style="@style/KeyStyle"
        android:id="@+id/e_key"
        android:background="@color/green3"
        android:layout_marginLeft="10dp"
        android:layout_marginRight="10dp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:onClick="e"/>

    <Button
        style="@style/KeyStyle"
        android:id="@+id/f_key"
        android:background="@color/green4"
        android:layout_marginLeft="15dp"
        android:layout_marginRight="15dp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:onClick="f"/>

    <Button
        style="@style/KeyStyle"
        android:id="@+id/g_key"
        android:background="@color/green5"
        android:layout_marginLeft="20dp"
        android:layout_marginRight="20dp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:onClick="g"/>

    <Button
        style="@style/KeyStyle"
        android:id="@+id/a_key"
        android:background="@color/green6"
        android:layout_marginLeft="25dp"
        android:layout_marginRight="25dp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:onClick="a"/>

    <Button
        style="@style/KeyStyle"
        android:id="@+id/b_key"
        android:background="@color/green7"
        android:layout_marginLeft="30dp"
        android:layout_marginRight="30dp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:onClick="b"/>

</LinearLayout>
```

**步骤 4:使用 MainActivity.java 文件**

在主活动中，我们需要创建一个新的**音池**。声音池使用媒体播放器库服务来加载音频文件。我们将为每个按键创建一个带有不同音频音符的功能。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.media.AudioManager;
import android.media.SoundPool;
import android.os.Bundle;
import android.util.Log;
import android.view.View;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    // Helpful Constants
    private final int sim_sound = 7;
    private final float lft_vol = 1.0f;
    private final float rgt_vol = 1.0f;
    private final int loop = 0;
    private final int prty = 0;
    private final float NORMAL_PLAY_RATE = 1.0f;

    // Add member variables here
    private SoundPool mSoundPool;
    private int mCSoundId1;
    private int mDSoundId2;
    private int mESoundId3;
    private int mFSoundId4;
    private int mGSoundId5;
    private int mASoundId6;
    private int mBSoundId7;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Create a new SoundPool
        mSoundPool = new SoundPool(sim_sound, AudioManager.STREAM_MUSIC, 0);

        // Load and get the IDs to identify the sounds
        mCSoundId1 = mSoundPool.load(getApplicationContext(), R.raw.note1_c, 1);
        mDSoundId2 = mSoundPool.load(getApplicationContext(), R.raw.note2_d, 1);
        mESoundId3 = mSoundPool.load(getApplicationContext(), R.raw.note3_e, 1);
        mFSoundId4 = mSoundPool.load(getApplicationContext(), R.raw.note4_f, 1);
        mGSoundId5 = mSoundPool.load(getApplicationContext(), R.raw.note5_g, 1);
        mASoundId6 = mSoundPool.load(getApplicationContext(), R.raw.note6_a, 1);
        mBSoundId7 = mSoundPool.load(getApplicationContext(), R.raw.note7_b, 1);

    }

    // Add the play methods triggered by the buttons
    public void c (View v){
        mSoundPool.play(mCSoundId1, lft_vol, rgt_vol, prty,loop,NORMAL_PLAY_RATE);
    }

    public void d (View v){
        mSoundPool.play(mDSoundId2, lft_vol, rgt_vol, prty,loop,NORMAL_PLAY_RATE);
    }

    // Add the play methods triggered by the buttons
    public void e (View v){
        mSoundPool.play(mESoundId3, lft_vol, rgt_vol, prty,loop,NORMAL_PLAY_RATE);
    }

    public void f (View v){
        mSoundPool.play(mFSoundId4, lft_vol, rgt_vol, prty,loop,NORMAL_PLAY_RATE);
    }

    public void g (View v){
        mSoundPool.play(mGSoundId5, lft_vol, rgt_vol, prty,loop,NORMAL_PLAY_RATE);
    }

    public void a (View v){
        mSoundPool.play(mASoundId6, lft_vol, rgt_vol, prty,loop,NORMAL_PLAY_RATE);
    }

    public void b (View v){
        mSoundPool.play(mBSoundId7, lft_vol, rgt_vol, prty,loop,NORMAL_PLAY_RATE);
    }

}
```

### 输出:

<video class="wp-video-shortcode" id="video-564063-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210225041940/Edited_20210225_041833.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210225041940/Edited_20210225_041833.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210225041940/Edited_20210225_041833.mp4)</video>