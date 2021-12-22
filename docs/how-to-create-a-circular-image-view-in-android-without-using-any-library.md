# 如何不使用任何库，在安卓中创建 Circular 图像视图？

> 原文:[https://www . geesforgeks . org/如何在不使用任何库的情况下在 android 中创建圆形图像视图/](https://www.geeksforgeeks.org/how-to-create-a-circular-image-view-in-android-without-using-any-library/)

本文旨在帮助如何使用安卓应用程序在图像上创建圆形图像视图。一个简单的圆形图像视图可以在不使用任何库的情况下用白色边框和带有形状的透明内容制作。

以下是如何做到这一点的步骤:

*   **步骤 1:创建圆形图像视图的布局**
    在可绘制目录中创建新的可绘制资源文件，该文件定义图像视图的形状为圆形。

这里文件名是循环的

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>

 <!--res/drawable/circular.xml-->
 <!--defines the circular shape and its properties-->
<shape xmlns:android="http://schemas.android.com/apk/res/android"

    android:innerRadius="0dp"
    android:shape="ring"
    android:thicknessRatio="2.0"
    android:useLevel="false" >

    <solid
        android:color="@android:color/transparent" />

    <stroke
        android:width="9dp"
        android:color="@android:color/white" />
</shape>
```