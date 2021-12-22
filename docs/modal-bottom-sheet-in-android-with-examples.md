# 安卓中的模态底层，示例

> 原文:[https://www . geeksforgeeks . org/modal-带示例的安卓底部表单/](https://www.geeksforgeeks.org/modal-bottom-sheet-in-android-with-examples/)

在本文中，我们将了解如何在我们的应用程序中添加 [**【模态底单】**](https://developer.android.com/reference/com/google/android/material/bottomsheet/package-summary) 。我们已经在日常应用中看到了这个用户界面组件，如谷歌驱动、地图或音乐播放器应用。模态的底部表单总是出现在屏幕的底部，如果用户点击了外部内容，它就会消失。它可以垂直拖动，也可以通过向下滑动来消除。

**进场:**

1.  在 **[build.gradle](https://www.geeksforgeeks.org/android-build-gradle/)** 文件中添加支持库，并在依赖项部分添加依赖项。在这个库的帮助下，我们可以继承**底层对话片段**，它帮助我们实现底层组件。

    ```
    dependencies {         
          implementation 'com.google.android.material:material:1.2.0-alpha02'     
    }         
    ```

2.  现在创建一个 **bottom_sheet_layout.xml** 文件，并添加以下代码。在这里，我们设计了我们的模态底板的布局。它有一个**文本视图**和**两个按钮**。

    ## bottom _ sheet _ layout . XML

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center_horizontal"
    android:orientation="vertical"
    android:padding="16dp">

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="This is a Modal BottomSheet"
        android:textSize="25sp" />

    <Button
        android:layout_margin="10dp"
        android:id="@+id/algo_button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Share this Algorithm" />

    <Button
        android:layout_margin="10dp"
        android:id="@+id/course_button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Share this Course" />

</LinearLayout>
```