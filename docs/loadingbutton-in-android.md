# 安卓加载按钮

> 原文:[https://www.geeksforgeeks.org/loadingbutton-in-android/](https://www.geeksforgeeks.org/loadingbutton-in-android/)

本文在安卓中增加了 **LoadingButton** 。**加载按钮**为我们提供了一个惊人的用户界面和一个动画，只要用户点击它。在应用中添加**加载按钮**非常容易。和安卓中的 [**按钮**](https://www.geeksforgeeks.org/handling-click-events-button-android/) 很像，只是增加了依赖和几个属性。像 **BL_backgroundColor** 、 **BL_circleColor** 、 **BL_circleColorSecond** 、 **BL_stateShow** 等标签可以用来定制**加载按钮**。**加载按钮**视图用于开发人员希望用户等待一段时间的任何地方。我们也可以使用[进度条](https://www.geeksforgeeks.org/progressbar-in-kotlin/#:~:text=Android%20ProgressBar%20is%20a%20user,the%20time%20remaining%20in%20operation.)来代替这个，但是加载按钮提供了独特而有吸引力的用户界面，增加了用户体验。它还为开发人员提供了完全的控制，因为它可以根据需求进行定制。

### 方法:

**步骤 1:** 在你的根**中添加支持库[build.gradle](https://www.geeksforgeeks.org/android-build-gradle/)T5】文件(不是你的模块 build . gradle 文件)。这个库 **jitpack** 是一个新颖的包存储库。它是为 JVM 而做的，这样在 [github](https://www.geeksforgeeks.org/ultimate-guide-git-github/) 和 [bigbucket](https://www.geeksforgeeks.org/bitbucket-vs-github-vs-gitlab/) 中存在的任何库都可以直接在应用程序中使用。**

## 可扩展标记语言

```java

allprojects {           
 repositories {           
        maven { url 'https://jitpack.io' }           
     }          
}           
```

**第二步:**在 **[build.gradle](https://www.geeksforgeeks.org/android-build-gradle/)** 文件中添加支持库，并在依赖项部分添加依赖项。

## 可扩展标记语言

```java

dependencies {     
      //For Snackbar 
      implementation 'com.google.android.material:material:1.1.0'     

      //For LoadingButton
      implementation 'com.github.andreasagap:LoadingButtonLibrary:v1.0'
}          
```

**第三步:**在 **activity_main.xml** 文件中添加以下代码。在这个文件中，我们将**加载按钮**添加到布局中。

## activity_main.xml

```java

<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:id="@+id/root"
    android:layout_height="match_parent">

    <andreasagap.loadingbutton.ButtonLoading
        android:id="@+id/loadingbutton"
        android:layout_width="200dp"
        android:layout_height="50dp"
        android:padding="6dp"
        app:BL_backgroundColor="#9c9b9999"
        app:BL_circleColor="#219806"
        app:BL_circleColorSecond="#126300"
        app:BL_enable="true"
        app:BL_stateShow="normal"
        app:BL_text="Buy Course"
        app:BL_textColor="#FFF"
        app:BL_textSize="16sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

**步骤 4:** 在 MainActivity.java 文件中添加以下代码。在这个文件中，将加载按钮附加到根布局，然后添加一个**监听器**。因此，每当用户点击它时，就会自动调用**设置按钮加载列表器**。在侦听器内部，有三种方法:onClick()、onStart()和 onFinish()。在 **onClick** 方法里面添加按钮被点击时应该执行的代码，在 **onStart()** 方法里面添加按钮被点击时应该立即执行的代码，在 onFinish()方法里面添加其他两个功能执行完之后执行的代码。

## MainActivity.java

```java

package org.geeksforgeeks.loadingbutton          

import androidx.appcompat.app.AppCompatActivity;
import androidx.constraintlayout.widget.ConstraintLayout;
import android.os.Bundle;
import android.widget.Toast;
import com.google.android.material.snackbar.BaseTransientBottomBar;
import com.google.android.material.snackbar.Snackbar;
import andreasagap.loadingbutton.ButtonLoading;

public class MainActivity extends AppCompatActivity {
    ButtonLoading loading_button;
    ConstraintLayout layout;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        layout = findViewById(R.id.root);
        loading_button =findViewById(R.id.loadingbutton);
        loading_button.setRoot(loading_button,this, layout);

        //set OnClickListner to button
        loading_button.setOnButtonLoadingListener(
                new ButtonLoading.OnButtonLoadingListener() {
            @Override
            public void onClick() {
            }
            @Override
            public void onStart() {
                Toast.makeText(MainActivity.this,
                        "Loading Start", Toast.LENGTH_LONG).show();
            }
            @Override
            public void onFinish() {
                //show snackbar when loading finished
                Snackbar.make(layout, "Thank you for
                        buying our Course!",
                        BaseTransientBottomBar
                       .LENGTH_LONG)
                       .show();
            }
        });
    }

    @Override
    public void onBackPressed() {
        loading_button.cancel();
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-454786-1" width="320" height="540" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200717135823/2020_07_17_13_56_44_0011.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200717135823/2020_07_17_13_56_44_0011.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200717135823/2020_07_17_13_56_44_0011.mp4)</video>

**参考:**T2**https://github.com/andreasagap/LoadingButtonLibrary**T5】