# 如何在安卓中添加 ViewFlipper？

> 原文:[https://www . geeksforgeeks . org/how-add-viewripler-in-Android/](https://www.geeksforgeeks.org/how-to-add-viewflipper-in-android/)

本文讲述的是 [**ViewFipper**](https://developer.android.com/reference/android/widget/ViewFlipper) 在安卓中的实现。它是 [**视图动画器**](https://developer.android.com/reference/android/widget/ViewAnimator) 类的扩展，有助于在添加到其中的视图之间制作动画。ViewFlipper 使切换视图变得很容易。为了控制视图之间的翻转，视图翻转器提供了两种方法**开始翻转()**和**停止翻转()**。要在视图之间自动切换，添加**自动启动**标签，并将其值设置为真。为了给用户更多的控制，在 ViewFlipper 中动态添加视图。图库应用程序中可以使用 ViewFlipper 在图像或视频之间导航。

**进场:**

1.  创建**新的安卓资源目录**。右键点击 **res** 文件夹，选择安卓资源目录。确保选择资源类型为**动画**。
2.  现在在**动漫目录**中创建新的 **slide_left.xml 文件**，并添加以下代码。这是将用于切换视图的动画。

    ## slide _ left . XML

    ```

    <?xml version="1.0" encoding="utf-8"?>
    <set xmlns:android="http://schemas.android.com/apk/res/android">
        <translate
            android:duration="@android:integer/config_mediumAnimTime"
            android:fromXDelta="0"
            android:toXDelta="-50%p" />
        <alpha
            android:duration="@android:integer/config_mediumAnimTime"
            android:fromAlpha="1.0"
            android:toAlpha="0.0" />
    </set>     
    ```

3.  现在在**动漫目录**中创建新的 **slide_right.xml 文件**，并添加以下代码。这是将用于切换视图的动画。

    ## 滑动 _ 右键

```

<?xml version="1.0" encoding="utf-8"?>
<set xmlns:android="http://schemas.android.com/apk/res/android">
    <translate
        android:duration="@android:integer/config_mediumAnimTime"
        android:fromXDelta="50%p"
        android:toXDelta="0" />
    <alpha
        android:duration="@android:integer/config_mediumAnimTime"
        android:fromAlpha="0.0"
        android:toAlpha="1.0" />
</set>
```