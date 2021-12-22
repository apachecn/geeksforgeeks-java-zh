# 如何在安卓中创建嵌套的 recycle view

> 原文:[https://www . geeksforgeeks . org/如何在安卓中创建嵌套回收视图/](https://www.geeksforgeeks.org/how-to-create-a-nested-recyclerview-in-android/)

一个**嵌套的回收视图**是一个回收视图内的一个[回收视图](https://www.geeksforgeeks.org/android-recyclerview/)的实现。这种布局的一个例子可以在各种应用程序中看到，例如游戏商店，其中外部(父)回收视图为垂直方向，而内部(子)回收视图为水平方向。这里开发了类似的布局。
**方法:**
**第一步:添加所需的依赖项**
将以下依赖项添加到 **build.gradle (:app)** 文件中。对应于回收视图的第一个依赖项是强制的，第二个依赖项是针对卡片视图的，因此根据用户界面的要求，它是可选的。因为这里的 CardView 是在子 RecyclerView 布局中使用的，所以添加了 CardView 依赖项。
*注意:添加依赖项后，点击**立即同步。***

> 实现' androidx . recycle view:recycle view:1 . 0 . 0 '
> 实现' androidx . card view:card view:1 . 0 . 0 '

注意:要查看依赖关系的正确版本，请查看。
**第二步:实现父回收视图**
父回收视图在 **activity_main** 文件中实现。在这里，activity_main 文件只保存父 RecyclerView，但是可以根据需求进行自定义。

## 活动 _ 主要

```java
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!-- This is the parent RecyclerView-->
    <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/parent_recyclerview"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.271" />

</androidx.constraintlayout.widget.ConstraintLayout>
```