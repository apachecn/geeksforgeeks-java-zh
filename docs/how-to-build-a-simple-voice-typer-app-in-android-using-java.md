# 如何用 Java 在安卓系统中搭建一个简单的语音 Typer App？

> 原文:[https://www . geesforgeks . org/how-to-build-a-simple-voice-typer-app-in-Android-use-Java/](https://www.geeksforgeeks.org/how-to-build-a-simple-voice-typer-app-in-android-using-java/)

**先决条件:**

*   [新手安卓应用开发基础](https://www.geeksforgeeks.org/android-app-development-fundamentals-for-beginners/)
*   [安卓工作室安装设置指南](https://www.geeksforgeeks.org/guide-to-install-and-set-up-android-studio/)
*   [如何在安卓工作室创建/启动新项目？](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)
*   [运行你的第一个安卓应用](https://www.geeksforgeeks.org/android-running-your-first-android-app/)
*   [安卓中的微调器](https://www.geeksforgeeks.org/spinner-in-android-using-java-with-example/)
*   [识别安卓系统中的意图](https://www.geeksforgeeks.org/how-to-convert-speech-to-text-in-android/)

在本文中，我们将使用 **Java** 在安卓系统中构建一个简单的**语音打字应用程序**。这是我们将要构建的应用程序的一瞥。该应用程序包含一个单一的[活动](https://www.geeksforgeeks.org/introduction-to-activities-in-android/)，带有两个[文本视图](https://www.geeksforgeeks.org/textview-widget-in-android-using-java-with-examples/)，一个[微调器](https://www.geeksforgeeks.org/spinner-in-android-using-java-with-example/)选择语言，一个[编辑文本](https://www.geeksforgeeks.org/edittext-widget-in-android-using-java-with-examples/)显示消息，以及两个可点击的[图像视图](https://www.geeksforgeeks.org/imageview-in-android-with-example/)，一个用于语音输入，另一个用于将消息复制到剪贴板。我们将使用识别意图类来获取用户的语音输入。下面给出了一个示例视频，以了解我们将在本文中做什么。

**预览:**

<video class="wp-video-shortcode" id="video-713262-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20211110182713/Untitled-265_1440p.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20211110182713/Untitled-265_1440p.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20211110182713/Untitled-265_1440p.mp4)</video>

### 逐步实施

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:添加矢量资产**

让我们添加必要的矢量资源和可绘制的资源文件。转到**应用程序> res >可绘制**并添加以下 XML 文件。

***ic_mic.xml** (麦克风图标)*

## 可扩展标记语言

```
<vector xmlns:android="http://schemas.android.com/apk/res/android"
    android:width="24dp"
    android:height="24dp"
    android:viewportWidth="24"
    android:viewportHeight="24"
    android:tint="?attr/colorControlNormal">
  <path
      android:fillColor="@android:color/white"
      android:pathData="M12,14c1.66,0 2.99,-1.34 2.99,-3L15,5c0,-1.66 -1.34,-3 -3,
                        -3S9,3.34 9,5v6c0,1.66 1.34,3 3,3zM17.3,11c0,3 -2.54,5.1 -5.3,
                        5.1S6.7,14 6.7,11L5,11c0,3.41 2.72,6.23 6,6.72L11,21h2v-3.28c3.28,
                        -0.48 6,-3.3 6,-6.72h-1.7z"/>
</vector>
```

**预览:**

![](img/f7e70e1ebeb12303eaa143cb0dbb99ff.png)

ic_mic.xml

*T1(剪贴板图标)*

## 可扩展标记语言

```
<vector xmlns:android="http://schemas.android.com/apk/res/android"
    android:width="24dp"
    android:height="24dp"
    android:viewportWidth="24"
    android:viewportHeight="24"
    android:tint="?attr/colorControlNormal">
  <path
      android:fillColor="@android:color/white"
      android:pathData="M16,1L4,1c-1.1,0 -2,0.9 -2,2v14h2L4,3h12L16,1zM19,
                        5L8,5c-1.1,0 -2,0.9 -2,2v14c0,1.1 0.9,2 2,2h11c1.1,0 2,
                        -0.9 2,-2L21,7c0,-1.1 -0.9,-2 -2,-2zM19,21L8,21L8,7h11v14z"/>
</vector>
```

**预览:**

![](img/5fd41c6afa310dc8891bcbb4ca7959ae.png)

ic_copy.xml

***et_bg.xml** (编辑文本自定义背景)*

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:state_focused="true">
        <shape android:shape="rectangle">
            <stroke android:color="@color/purple_200" android:width="2dp"/>
            <corners android:radius="5dp"/>
        </shape>
    </item>
    <item android:state_focused="false">
        <shape android:shape="rectangle">
            <stroke android:color="#808080" android:width="2dp"/>
            <corners android:radius="5dp"/>
        </shape>
    </item>
</selector>
```