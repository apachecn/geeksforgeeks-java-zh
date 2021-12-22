# 安卓中的插值器，示例

> 原文:[https://www . geeksforgeeks . org/带示例的安卓插值器/](https://www.geeksforgeeks.org/interpolator-in-android-with-example/)

**插值器**是一个函数(在数学意义上)，它输出在给它作为输入的一系列值之间“插值”的值。**插值**简单来说就是在两个固定数据点之间生成新数据点的方法。这些生成的数据点的精确值由执行的插值类型决定。例如在**线性插值**中，所有生成的值均匀分布在固定点之间。虽然理解插值是有帮助的，但是没有必要开始在应用程序中制作视图动画。事实上，插值的动画视角可能有助于理解它！那么，让我们开始吧。在这个例子中，我们将创建一个带有按钮列表的简单应用程序。这些按钮中的每一个都是针对特定类型的插值动画，当您按下它时就会启动。动画是一个简单的水平平移，将按钮向右移动。

## 插值器接口

在安卓开发框架中，[插值器](https://developer.android.com/reference/android/view/animation/Interpolator)被定义为一个接口。这允许方法接受一个插值器，它可以带来自己的配置，而不会将开发人员束缚在特定的实现上。在撰写本文时，插值器接口有 11 个间接子类。它们是:

*   [线性插值器](https://developer.android.com/reference/android/view/animation/Interpolator):两个固定点之间生成的值均匀分布。例如，将 **a** = 1 和 **b** = 5 视为固定点。 *a* 和 *b* 之间的线性插值看起来像:1 - > 2 - > 3 - > 4 - > 5，其中 1 和 5 之间的数字已经生成。
*   [加速插值器](https://developer.android.com/reference/android/view/animation/AccelerateInterpolator):这个插值器产生的值最初有一个小的差值，然后逐渐增加差值，直到到达终点。例如，使用加速插值在 1 - > 5 之间生成的值可以是 1->1.2->1.5->1.9->2.4->3.0->3.6->4.3->5。请注意连续值之间的差异如何持续增长。
*   [减速插值器](https://developer.android.com/reference/android/view/animation/DecelerateInterpolator):在加速插值器以加速方式生成值的意义上，当您在生成值列表中向前移动时，减速插值器会生成“减速”的值。因此，最初生成的值之间有较大的差异，并且差异逐渐减小，直到到达终点。因此，在 1 - > 5 之间生成的值可能看起来像 1->1.8->2.5->3.1->3.6->4.0->4.3->4.5->4.6->4.7->4.8->4.9->5。再次，注意连续值之间的差异越来越小。
*   [加速减速内插器](https://developer.android.com/reference/android/view/animation/AccelerateDecelerateInterpolator):这个内插器以缓慢的变化率开始，并向中间加速。当接近终点时，它开始减速，即降低变化率。
*   [预计插值器](https://developer.android.com/reference/android/view/animation/AnticipateInterpolator):该插值首先向后移动，然后向前“甩”，然后逐渐进行到最后。这给了它一种类似于卡通的效果，在卡通中，角色在逃跑前会后退。例如，在 1 - > 3 之间生成的值可能看起来像:1 - > 0.5 - > 2 - > 2.5 - > 3。请注意，第一个生成的值是如何“落后于”起始值的，以及它是如何向前跳到起始值之前的值的。然后，它统一前进到端点。
*   [弹跳插值器](https://developer.android.com/reference/android/view/animation/BounceInterpolator):要理解这个插值器，考虑一个垂直立在固体表面上的米尺。起始值在顶部，结束值在底部，与表面接触。现在想想，一个球掉到了米尺旁边。球碰到地面时会上下弹跳几次，直到最后停在地面上。使用弹跳插值器，生成的值类似于球在仪表刻度旁边经过的值列表。例如，在 1 - > 5 之间生成的值可以是 1->2->3->4->5->4.2->5->4.5->5。请注意生成的值如何反弹。
*   [过冲插值器](https://developer.android.com/reference/android/view/animation/OvershootInterpolator):该插值器从开始到结束统一生成值。然而，到达终点后，**超出**或超出最后一个值一点点，然后回到终点。例如，在 1 - > 5 之间生成的值可能看起来像:1->2->3->4->5->5.5->5。
*   [预期过冲插值器](https://developer.android.com/reference/android/view/animation/AnticipateOvershootInterpolator):该插值器是预期和过冲插值器的组合。也就是说，它首先从起始值向后，向前投掷并均匀地移动到端点，超过它，然后返回到端点。

## 创建应用程序

为了更好地理解上面提到的类，并看到它们的实际应用，强烈建议您在构建实际项目的同时运行该应用程序。

*   **启用和设置视图绑定(可选)**
    视图绑定是不久前推出的一个简洁的小功能，它使您在应用程序中处理视图变得更加容易。本质上，它取消了 *findViewById* 调用，并为您提供了更易于使用的视图句柄。它们还能让你的代码更干净。这是一个非常简单的过程，你可以在[官方文档](https://developer.android.com/topic/libraries/view-binding)中看到如何打开和设置它。但是，这一步是可选的，如果您更喜欢手动连接视图，也可以继续。最终的结果只需要你有你想要配置的按钮的句柄。
*   **创建布局**
    在您的 *activity_main.xml* 文件中，创建按钮列表，如下面的代码部分所示。布局基本上由不同按钮的重复代码组成，因此如果您了解一个按钮的情况，您也可以将相同的内容应用到其他按钮。

**步骤 1:使用 activity_main.xml 文件**

转到 **activity_main.xml** 文件，参考以下代码。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<ScrollView
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="16dp"
        android:gravity="center"
        android:orientation="vertical"
        android:padding="16dp">

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Interpolators"
            app:layout_constraintBottom_toBottomOf="parent"
            app:layout_constraintLeft_toLeftOf="parent"
            app:layout_constraintRight_toRightOf="parent"
            app:layout_constraintTop_toTopOf="parent" />

        <androidx.appcompat.widget.AppCompatButton
            android:id="@+id/linear"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="16dp"
            android:text="Linear"
            android:textColor="#FFF" />

        <androidx.appcompat.widget.AppCompatButton
            android:id="@+id/accelerate"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="16dp"
            android:text="Accelerate"
            android:textColor="#FFF" />

        <androidx.appcompat.widget.AppCompatButton
            android:id="@+id/decelerate"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="16dp"
            android:text="Decelerate"
            android:textColor="#FFF" />

        <androidx.appcompat.widget.AppCompatButton
            android:id="@+id/bounce"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="16dp"
            android:text="Bounce"
            android:textColor="#FFF" />

        <androidx.appcompat.widget.AppCompatButton
            android:id="@+id/overshoot"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="16dp"
            android:text="Overshoot"
            android:textColor="#FFF" />

        <androidx.appcompat.widget.AppCompatButton
            android:id="@+id/anticipate"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="16dp"
            android:text="Anticipate"
            android:textColor="#FFF" />

        <androidx.appcompat.widget.AppCompatButton
            android:id="@+id/cycle"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="16dp"
            android:text="Cycle"
            android:textColor="#FFF" />

        <androidx.appcompat.widget.AppCompatButton
            android:id="@+id/accelerateDecelerate"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="16dp"
            android:text="Accelerate Decelerate"
            android:textColor="#FFF" />

        <androidx.appcompat.widget.AppCompatButton
            android:id="@+id/anticipateOvershoot"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_marginTop="16dp"
            android:text="Anticipate Overshoot"
            android:textColor="#FFF" />

    </LinearLayout>
</ScrollView>
```

**步骤 2:使用 MainActivity.java 文件**

**设置对象动画师对象:**在本例中，我们将使用单个*对象动画师*来激活不同的按钮。我们还将使用 2 秒的固定持续时间来播放动画，这给了我们足够的时间来观察动画行为。您可以用下面的两行代码来设置它。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// 2-second animation duration
final private static int ANIMATION_DURATION = 2000;
private ObjectAnimator animator;
```

**在按钮点击时设置动画:**现在我们已经设置了先决条件，我们终于可以开始配置按钮来触发它们各自的动画了。对于每个按钮，您可以将特定属性配置为动画、其持续时间和插值等。基本的三步配置如下面的代码片段所示:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Linear
binding.linear.setOnClickListener(clickedView -> {
    animator = ObjectAnimator.ofFloat(binding.linear,"translationX", 200f);
    animator.setInterpolator(new LinearInterpolator());
    animator.setDuration(ANIMATION_DURATION);
    animator.start();
});
```

以下是**文件的完整代码。代码中添加了注释，以更详细地理解代码。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
import android.animation.ObjectAnimator;
import android.os.Bundle;
import android.view.View;
import android.view.animation.AccelerateDecelerateInterpolator;
import android.view.animation.AccelerateInterpolator;
import android.view.animation.AnticipateInterpolator;
import android.view.animation.AnticipateOvershootInterpolator;
import android.view.animation.BounceInterpolator;
import android.view.animation.CycleInterpolator;
import android.view.animation.DecelerateInterpolator;
import android.view.animation.LinearInterpolator;
import android.view.animation.OvershootInterpolator;
import androidx.appcompat.app.AppCompatActivity;
import com.example.doobar.databinding.ActivityMainBinding;

public class MainActivity extends AppCompatActivity {

    // 2-second animation duration
    final private static int ANIMATION_DURATION = 2000; 

    private ActivityMainBinding binding;
    private ObjectAnimator animator;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        binding = ActivityMainBinding.inflate(getLayoutInflater());
        View view = binding.getRoot();
        setContentView(view);

        // setup animation buttons

        // Linear
        binding.linear.setOnClickListener(clickedView -> {
            animator = ObjectAnimator.ofFloat(binding.linear, "translationX", 200f);
            animator.setInterpolator(new LinearInterpolator());
            animator.setDuration(ANIMATION_DURATION);
            animator.start();
        });

        // Accelerate
        binding.accelerate.setOnClickListener(clickedView -> {
            animator = ObjectAnimator.ofFloat(binding.accelerate, "translationX", 200f);
            animator.setInterpolator(new AccelerateInterpolator());
            animator.setDuration(ANIMATION_DURATION);
            animator.start();
        });

        // Decelerate
        binding.decelerate.setOnClickListener(clickedView -> {
            animator = ObjectAnimator.ofFloat(binding.decelerate, "translationX", 200f);
            animator.setInterpolator(new DecelerateInterpolator());
            animator.setDuration(ANIMATION_DURATION);
            animator.start();
        });

        // Bounce
        binding.bounce.setOnClickListener(clickedView -> {
            animator = ObjectAnimator.ofFloat(binding.bounce, "translationX", 200f);
            animator.setInterpolator(new BounceInterpolator());
            animator.setDuration(ANIMATION_DURATION);
            animator.start();
        });

        // Overshoot
        binding.overshoot.setOnClickListener(clickedView -> {
            animator = ObjectAnimator.ofFloat(binding.overshoot, "translationX", 200f);
            animator.setInterpolator(new OvershootInterpolator());
            animator.setDuration(ANIMATION_DURATION);
            animator.start();
        });

        // Anticipate
        binding.anticipate.setOnClickListener(clickedView -> {
            animator = ObjectAnimator.ofFloat(binding.anticipate, "translationX", 200f);
            animator.setInterpolator(new AnticipateInterpolator());
            animator.setDuration(ANIMATION_DURATION);
            animator.start();
        });

        // Cycle
        binding.cycle.setOnClickListener(clickedView -> {
            animator = ObjectAnimator.ofFloat(binding.cycle, "translationX", 200f);
            animator.setInterpolator(new CycleInterpolator(2));
            animator.setDuration(ANIMATION_DURATION);
            animator.start();
        });

        // Accelerate Decelerate
        binding.accelerateDecelerate.setOnClickListener(clickedView -> {
            animator = ObjectAnimator.ofFloat(binding.accelerateDecelerate, "translationX", 200f);
            animator.setInterpolator(new AccelerateDecelerateInterpolator());
            animator.setDuration(ANIMATION_DURATION);
            animator.start();
        });

        // Anticipate Overshoot
        binding.anticipateOvershoot.setOnClickListener(clickedView -> {
            animator = ObjectAnimator.ofFloat(binding.anticipateOvershoot, "translationX", 200f);
            animator.setInterpolator(new AnticipateOvershootInterpolator());
            animator.setDuration(ANIMATION_DURATION);
            animator.start();
        });
    }
}
```

### ****输出:运行应用****

**已经建立了按钮，并设置它们触发动画时，按下，你都设置启动应用程序，看到你的动画来了。你完蛋了！这就是你如何在动画中使用插值器来增加趣味，而不是让它们看起来单调。**

**<video class="wp-video-shortcode" id="video-523072-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201129145930/recording.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201129145930/recording.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201129145930/recording.mp4)</video>**

**您可以在这里查看整个应用程序:[https://github.com/krishnakeshan/android-interpolators](https://github.com/krishnakeshan/android-interpolators)。**