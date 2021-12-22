# 如何在安卓中添加 Slidr 库？

> 原文:[https://www . geesforgeks . org/how-add-slidr-library in-Android/](https://www.geeksforgeeks.org/how-to-add-slidr-library-in-android/)

在这个布局中，我们将学习在安卓中添加 **Slidr Library** 。当用户从一个活动切换到另一个活动时，该库用于创建吸引人的动画。该库可用于[](https://www.geeksforgeeks.org/activity-lifecycle-in-android-with-demo-app/)**和 [**片段**](https://www.geeksforgeeks.org/introduction-fragments-android/) 。它非常容易实现。当 Slidr 附加到活动时，它的接口返回给我们两种方法:-**

*   **SlidrInterface.lock()***   **SlidrInterface.unlock();

    **进场:**

    1.  在 **[build.gradle](https://www.geeksforgeeks.org/android-build-gradle/)** 文件中添加支持库，并在依赖项部分添加依赖项。这将帮助我们直接添加主题和方法来添加动画。

        ```
        dependencies {         
              implementation 'com.r0adkll:slidableactivity:2.1.0'     
        }         
        ```

    2.  现在为 Slidr 活动添加主题。将这些属性添加到主题中，这是 Slidr 正常工作所必需的。

    ```
    <style name="AppTheme.SlidrActivityTheme">
            <item name="android:windowIsTranslucent">true</item>
            <item name="android:windowBackground">@android:color/transparent
            </item>
    </style>
    ```**