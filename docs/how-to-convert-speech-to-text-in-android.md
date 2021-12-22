# 如何在安卓系统中将语音转换为文本？

> 原文:[https://www . geesforgeks . org/如何在安卓系统中将语音转换为文本/](https://www.geeksforgeeks.org/how-to-convert-speech-to-text-in-android/)

本文中，**语音转文本**功能在安卓的一个应用中实现。语音转换为文本意味着用户所说的任何内容都被转换为文本。这个特性对于用户来说是一个非常常见和有用的特性。在像谷歌搜索这样实现搜索功能的地方，也可以在像谷歌键盘这样的应用程序中实现，因为它给用户带来了很好的体验。

[![](img/05b2a058893045076ceb58a8f876b114.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200708192503/speechtotext.png)

### 方法:

**第一步:**在 **activity_main.xml** 中添加以下代码。这里添加了麦克风图标的**图像视图**和显示从语音转换而来的文本的**文本视图**。

## activity_main.xml

```java
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <ImageView
        android:id="@+id/iv_mic"
        android:layout_width="60dp"
        android:layout_height="60dp"
        android:layout_alignParentTop="true"
        android:layout_alignParentEnd="true"
        android:layout_marginTop="204dp"
        android:src="@drawable/ic_mic"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/tv_speech_to_text"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentTop="true"
        android:layout_alignParentEnd="true"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="44dp"
        android:textSize="30sp"
        android:padding="10dp"
        android:text="@string/tap_mic_and_speek"
        app:layout_constraintEnd_toEndOf="@+id/iv_mic"
        app:layout_constraintHorizontal_bias="0.489"
        app:layout_constraintStart_toStartOf="@+id/iv_mic"
        app:layout_constraintTop_toBottomOf="@+id/iv_mic" />

</androidx.constraintlayout.widget.ConstraintLayout>
```