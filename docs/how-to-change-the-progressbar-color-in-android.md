# 如何在安卓中改变进度条颜色？

> 原文:[https://www . geesforgeks . org/how-to-change-the-progress bar-in-color-Android/](https://www.geeksforgeeks.org/how-to-change-the-progressbar-color-in-android/)

在本文中，我们将看到如何在 android 中为 [ProgressBar](https://www.geeksforgeeks.org/progressbar-in-kotlin/) 添加颜色。Android ProgressBar 是一个用户界面控件，用于指示操作的进度。比如下载一个文件，在网上上传一个文件我们可以看到 ProgressBar 估计剩余的运行时间。注意在本文中，我们将使用 **Java** 和 **XML** 来设置颜色。

### 逐步实施

**第一步:新建项目**

*   Please refer to [How to create/start a new project in Android Studio](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/) for new projects in Android Studio.
*   Pay attention to **Java** as the programming language.

**步骤 2:创建自定义进度条**

*   Go to **app > RES > to draw >, right-click > to create > to draw the resource file** , and name the file as **progress _ BG** .
*   Add a rotation tag with some attributes inside the XML file (see code)
*   Create a shape label inside the rotating label, and create size and gradient labels in it.
*   The attributes of these tags are given in the following code.
*   The following is the code of **progress _ bg.xml** file.

## XML

```java
<?xml version="1.0" encoding="utf-8"?>
<!--use rotate tag to rotate the drawable-->
<rotate 
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:fromDegrees="0"
    android:pivotX="50%"
    android:pivotY="50%"
    android:toDegrees="360">

    <!--shape tag is used to 
        build a shape in XML-->
    <shape
        android:innerRadiusRatio="3"
        android:shape="ring"
        android:thicknessRatio="8"
        android:useLevel="false">

        <!--set the size of the shape-->
        <size
            android:width="76dip"
            android:height="76dip" />

        <!--set the color gradients
            of the shape-->
        <gradient
            android:angle="0"
            android:endColor="#00ffffff"
            android:startColor="#447a29"
            android:type="sweep"
            android:useLevel="false" />
    </shape>

</rotate>
```