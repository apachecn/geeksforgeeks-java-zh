# 如何在安卓中创建 AnimatedGradient？

> 原文:[https://www . geesforgeks . org/how-create-animated radient in Android/](https://www.geeksforgeeks.org/how-to-create-animatedgradient-in-android/)

在本文中，我们将学习如何在 android 中创建 **AnimatedGradient** 。它可以在我们应用的后台使用。在这种情况下，我们添加不同的颜色渐变并制作动画。即使在旧版本的 Instagram 中，开发人员也使用 AnimatedGradient 作为登录屏幕的背景，以使布局看起来有吸引力。

**方法:**
**步骤 1:** 创建不同的渐变 xml 文件，在后台进行更改。这些文件包括上图所示的**起始颜色**、下图所示的**结束颜色**以及分割两部分的水平线的**角度**。这里我们创建三个渐变 xml 文件。

1.  在可绘制文件夹中创建一个 **gradient_one.xml** 文件，并添加以下代码。

    ## 渐变 _ one . XML

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <shape xmlns:android="http://schemas.android.com/apk/res/android">
        <gradient
            android:angle="225"
            android:endColor="#09CCC8"
            android:startColor="#ffd6d3" />
    </shape>
    ```

2.  在可绘制文件夹中创建 **gradient_two.xml** 文件，并添加以下代码。

    ## 渐变

```
<?xml version="1.0" encoding="utf-8"?>
<shape xmlns:android="http://schemas.android.com/apk/res/android">
    <gradient
        android:angle="45"
        android:endColor="#FD7BCE"
        android:startColor="#A4DDF8" />
</shape>
```