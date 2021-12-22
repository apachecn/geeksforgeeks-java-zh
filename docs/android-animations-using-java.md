# 使用 Java 的安卓动画

> 原文:[https://www . geesforgeks . org/Android-动画-使用-java/](https://www.geeksforgeeks.org/android-animations-using-java/)

动画是一种方法，其中一组图像以特定的方式被组合并处理，然后它们作为运动图像出现。构建动画使屏幕上的对象看起来像是活的。 [安卓](https://www.geeksforgeeks.org/introduction-to-android-development/) 有相当多的工具可以帮助你相对轻松地创建动画。所以在本文、中，让我们学习使用 Java 创建安卓动画。

#### **属性表**

<figure class="table">

| **XML 属性** | **描述** |
| --- | --- |
| android:id | 设置视图的唯一 id |
| 安卓:持续时间 | 用于指定动画的持续时间 |
| 安卓:从度 | 起始角位置(度) |
| 安卓:toDegrees | 结束角度位置(度) |
| android:fromXScale | 起始 X 尺寸偏移 |
| android:toXScale | X 尺寸偏移的结束 |
| android:fromYScale | 起始 Y 尺寸偏移 |
| 安卓:toYScale | Y 尺寸偏移的结束 |
| 安卓:fromAlpha | 动画的起始 alpha 值
(1.0 表示完全不透明，0.0 表示完全透明) |
| 安卓:toAlpha | 结束 alpha 值 |
| 安卓:fromYDelta | 要在动画开始时应用的 Y 坐标变化 |
| 安卓:玩具反斗城 | 要在动画结束时应用的 Y 坐标变化 |
| android:pivotX | 表示从起点开始缩放的 X 轴坐标 |
| Android:pivot(旋转) | 表示从起点开始缩放的 Y 轴坐标 |
| 安卓:插值器 | 它定义了动画的变化率 |
| android:启动偏移 | 到达开始时间后，动画运行时会发生延迟(毫秒) |

</figure>

### 如何用 Java 在 Android 中添加动画

**第一步:创建新项目**

*   启动安卓工作室(版本> 2.2)
*   转到文件->新建->新建项目。
*   选择空活动，然后单击下一步
*   选择最小 SDK 为 21
*   选择 Java 语言，然后单击“完成”按钮。
*   修改以下 XML 和 java 文件。

**第二步:修改 activity_main.xml 文件**

在 XML 文件中，我们在[相对布局](https://www.geeksforgeeks.org/android-relativelayout-in-kotlin/)中添加了[图像视图](https://www.geeksforgeeks.org/imageview-in-kotlin/)、[文本视图](https://www.geeksforgeeks.org/textview-in-kotlin/)和[按钮](https://www.geeksforgeeks.org/button-in-kotlin/)。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:id="@+id/RL1"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <ImageView
        android:id="@+id/imageView1"
        android:layout_width="200dp"
        android:layout_height="150dp"
        android:layout_below="@id/textView0"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="100dp"
        android:visibility="visible"
        android:src="@drawable/logo2" />

    <TextView
        android:id="@+id/textView1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="4 common animations in android"
        android:layout_below="@id/imageView1"
        android:layout_marginTop="50dp"
        android:layout_centerHorizontal="true"
        android:gravity="center"
        android:fontFamily="sans-serif"
        android:textSize="50px"/>

    <Button
        android:id="@+id/button1"
        android:layout_width="150dp"
        android:layout_height="wrap_content"
        android:text="Blink"
        android:layout_below="@id/textView1"
        android:layout_marginLeft="50dp"
        android:layout_marginTop="40dp"/>

    <Button
        android:id="@+id/button2"
        android:layout_width="150dp"
        android:layout_height="wrap_content"
        android:text="Slide"
        android:layout_below="@id/textView1"
        android:layout_alignParentRight="true"
        android:layout_marginRight="50dp"
        android:layout_marginTop="40dp"/>

    <Button
        android:id="@+id/button3"
        android:layout_width="150dp"
        android:layout_height="wrap_content"
        android:text="Rotate"
        android:layout_below="@id/button1"
        android:layout_marginLeft="50dp"
        android:layout_marginTop="30dp"/>

    <Button
        android:id="@+id/button4"
        android:layout_width="150dp"
        android:layout_height="wrap_content"
        android:text="Zoom"
        android:layout_below="@id/button2"
        android:layout_alignParentRight="true"
        android:layout_marginRight="50dp"
        android:layout_marginTop="30dp"/>

</RelativeLayout>
```

**第三步:将这些 XML 文件添加到 anim 目录**

修改布局后，我们将为动画创建 XML 文件。所以我们先创建一个文件夹名 **anim** 。在这个文件夹中，我们将添加用于制作动画的 XML 文件。为此，请转到**应用程序/res** 右键单击，然后选择**安卓资源目录**并将其命名为动漫。

安卓系统中常见的动画类型有，

1.  闪烁–隐藏对象 0.6 到 1 秒。
2.  滑动–将对象垂直或水平移动到其轴上。
3.  旋转–顺时针或逆时针旋转对象。
4.  缩放–在 X 轴和 Y 轴上放大或缩小对象。

## blinks.xml

```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
   <alpha android:fromAlpha="0.0"
      android:toAlpha="1.0"
      android:interpolator="@android:anim/accelerate_interpolator"
      android:duration="700"
      android:repeatMode="reverse"
      android:repeatCount="infinite"/>
</set>
```

## rotate.xml

```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">

   <rotate xmlns:android="http://schemas.android.com/apk/res/android"
      android:fromDegrees="0"
      android:toDegrees="360"
      android:pivotX="50%"
      android:pivotY="50%"
      android:duration="2500" >
   </rotate>

   <rotate xmlns:android="http://schemas.android.com/apk/res/android"
      android:startOffset="5000"
      android:fromDegrees="360"
      android:toDegrees="0"
      android:pivotX="50%"
      android:pivotY="50%"
      android:duration="2500" >
   </rotate>

</set>
```

## slides.xml

```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android"
   android:fillAfter="true" >

   <scale
      android:duration="500"
      android:fromXScale="1.0"
      android:fromYScale="1.0"
      android:interpolator="@android:anim/linear_interpolator"
      android:toXScale="1.0"
      android:toYScale="0.0" />
</set>
```

## zoom.xml

```
<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">

   <scale xmlns:android="http://schemas.android.com/apk/res/android"
      android:fromXScale="0.5"
      android:toXScale="3.0"
      android:fromYScale="0.5"
      android:toYScale="3.0"
      android:duration="4000"
      android:pivotX="50%"
      android:pivotY="50%" >
   </scale>

   <scale xmlns:android="http://schemas.android.com/apk/res/android"
      android:startOffset="5000"
      android:fromXScale="3.0"
      android:toXScale="0.5"
      android:fromYScale="3.0"
      android:toYScale="0.5"
      android:duration="4000"
      android:pivotX="50%"
      android:pivotY="50%" >
   </scale>

</set>
```

**第四步:修改 MainActivity.java**

要在安卓系统中执行动画，我们必须调用类**的静态函数**loadAnimation()**animation utils**。我们在动画对象的实例中得到结果。创建动画对象的语法:

> 动画对象= animation utils . load animation(getapplicationcontext()、r . animation . animation file)：

要将上述动画应用于对象(比如在图像中)，我们必须调用对象的 **startAnimation()** 方法。调用方法的语法:

> ImageView 影像= findviewbyid(r . id . image id)；
> 
> image.startAnimation(对象)；

动画类的方法:

<figure class="table">T32

| **方法** | **描述** |
| Start animation (object) | Start animation |
| Set duration (long duration) | Set the duration of the animation |
| Get duration () |

</figure>

## Java 语言(一种计算机语言，尤用于创建网站)

```
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.view.animation.Animation;
import android.view.animation.AnimationUtils;
import android.widget.Button;
import android.widget.ImageView;

public class MainActivity extends AppCompatActivity {
    ImageView logo;
    Button blink, slide, rotate, zoom;

    @Override
    protected void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // GFG logo
        logo = findViewById(R.id.imageView1);

        // blink button
        blink = findViewById(R.id.button1);

        // slide button
        slide = findViewById(R.id.button2);

        // rotate button
        rotate = findViewById(R.id.button3);

        // zoom button
        zoom = findViewById(R.id.button4);

        // blink button listener
        blink.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view)
            {
                // call a static function loadAnimation()
                // of the class AnimationUtils
                Animation object
                    = AnimationUtils
                          .loadAnimation(
                              getApplicationContext(),

                              // blink file is in anim folder
                              R.anim.blinks);
                // call the startAnimation method
                logo.startAnimation(object);
            }
        });
        // slide button listener
        slide.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view)
            {
                // call a static function loadAnimation()
                // of the class AnimationUtils
                Animation object
                    = AnimationUtils
                          .loadAnimation(

                              getApplicationContext(),

                              // slide file is in anim folder
                              R.anim.slide);

                // call the startAnimation method
                logo.startAnimation(object);
            }
        });

        // rotate button listener
        rotate.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view)
            {
                // call a static function loadAnimation()
                // of the class AnimationUtils
                Animation object
                    = AnimationUtils
                          .loadAnimation(
                              getApplicationContext(),

                              // rotate file is in anim folder
                              R.anim.rotate);

                // call the startAnimation method
                logo.startAnimation(object);
            }
        });

        // zoom button listener
        zoom.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view)
            {
                // call a static function loadAnimation()
                // of the class AnimationUtils
                Animation object
                    = AnimationUtils
                          .loadAnimation(
                              getApplicationContext(),

                              // zoom file is in anim folder
                              R.anim.zoom);

                // call the startAnimation method
                logo.startAnimation(object);
            }
        });
    }
}
```

#### **输出:在仿真器上运行**

<video class="wp-video-shortcode" id="video-450561-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200702012037/20200702_011824.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200702012037/20200702_011824.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200702012037/20200702_011824.mp4)</video>