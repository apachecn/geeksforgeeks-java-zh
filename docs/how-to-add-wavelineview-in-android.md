# 如何在安卓中添加 WaveLineView？

> 原文:[https://www . geeksforgeeks . org/如何添加-wavelineview-in-android/](https://www.geeksforgeeks.org/how-to-add-wavelineview-in-android/)

在本文中，WaveLineView 是在 android 中实现的。**wavelline view**为我们提供了非常漂亮的 UI。当用户必须等待一段时间时，可以使用它。**波浪线视图**使我们的布局非常有吸引力，从而增强了应用程序的用户体验。WaveLineView 提供了两种方法 **startAnim()** 和 **stopAnim()** 。**WavelLineView**可以在开发者希望用户等待一段时间的任何地方使用。也可以用 [**进度条**](https://www.geeksforgeeks.org/progressbar-in-kotlin/#:~:text=Android%20ProgressBar%20is%20a%20user,the%20time%20remaining%20in%20operation.) 来代替这个，但是因为它独特的用户界面，它会吸引用户，因此用户会等待足够的时间。它还为开发人员提供了完全的控制，因为他们可以根据需求定制它。

### 方法:

**步骤 1:** 在你的根[中添加支持库**build.gradle**T5】文件(不是你的模块 build . gradle 文件)。这个库 **jitpack** 是一个新颖的包存储库。它是为 JVM 而做的，因此](https://www.geeksforgeeks.org/android-build-gradle/) [github](https://www.geeksforgeeks.org/ultimate-guide-git-github/) 和 bitbucket 中存在的任何库都可以直接在应用程序中使用。

## 可扩展标记语言

```java

allprojects {         
   repositories {         
      maven { url 'https://jitpack.io' }         
  }
}         
```

**第二步:**在 [**build.gradle**](https://www.geeksforgeeks.org/android-build-gradle/) 文件中添加支持库，并在依赖项部分添加依赖项。它有一个内置的波形线视图，允许直接添加视图。

## 可扩展标记语言

```java

dependencies {         
        implementation 'com.github.Jay-Goo:WaveLineView:v1.0.4'         
}
```

**第三步:**在 **activity_main.xml** 文件中添加以下代码。在这个文件中，我们将**波形视图**添加到布局中。

## activity_main.xml

```java

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <jaygoo.widget.wlv.WaveLineView
        android:id="@+id/waveLineView"
        android:layout_width="match_parent"
        android:layout_height="120dp"
        app:wlvBackgroundColor="@android:color/white"
        app:wlvMoveSpeed="290"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        />

</androidx.constraintlayout.widget.ConstraintLayout>
```

**第四步:**在**MainActivity.java**文件中增加以下代码。WaveLineView 为我们提供了两种方法 **startAnim()** 和 **stopAnim()** 。startAnim()启动动画，stopAnim()停止动画。

## MainActivity.java

```java

package com.madhav.maheshwari.wavelineview;

import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import jaygoo.widget.wlv.WaveLineView;

public class MainActivity extends AppCompatActivity {
    WaveLineView waveLineView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        waveLineView = findViewById(R.id.waveLineView);
        waveLineView.startAnim();
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-450646-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200709215403/Record_2020-07-09-21-49-10_6a33b8dc17ce0e45bec163fe538b18f01.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200709215403/Record_2020-07-09-21-49-10_6a33b8dc17ce0e45bec163fe538b18f01.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200709215403/Record_2020-07-09-21-49-10_6a33b8dc17ce0e45bec163fe538b18f01.mp4)</video>