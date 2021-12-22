# 如何在安卓中合成振动模式？

> 原文:[https://www . geesforgeks . org/如何在安卓中合成振动模式/](https://www.geeksforgeeks.org/how-to-compose-vibration-patterns-in-android/)

正如本文前面的 [**如何在安卓**中以编程方式振动设备所讨论的。因此，在本文中，我们讨论了如何制作振动模式，从而产生不同波形的振动。该实现可以是当有来电并且设备产生各种振动模式时产生的振动的复制品。注意，我们也将使用 **Java** 语言来实现这个项目。](https://www.geeksforgeeks.org/how-to-vibrate-a-device-programmatically-in-android/)

## **在安卓中实现振动模式的步骤**

**第一步:创建一个空的活动安卓工作室项目**

*   Create an empty active Android studio project. And choose **Java** as the programming language.
*   Refer to [Android | How to create/start a new project in Android Studio](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/) to learn how to create an empty active Android Studio project.

**步骤 2:使用 activity_main.xml 文件**

*   Implement a button in the layout, which is used to create a vibration waveform when pressed.
*   Call the following code in the **activity _ main.xml** file.

## XML

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    tools:ignore="HardcodedText">

    <!--button to compose vibration waveforms when pressed-->
    <Button
        android:id="@+id/makeVibrationCompositionButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:backgroundTint="@color/colorPrimary"
        android:text="COMPOSE VIBRATION"
        android:textColor="@android:color/white" />

</RelativeLayout>
```