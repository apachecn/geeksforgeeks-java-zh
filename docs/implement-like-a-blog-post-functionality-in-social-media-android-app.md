# 在社交媒体安卓应用中实现类似博文的功能

> 原文:[https://www . geesforgeks . org/implement-like-a-blog-post-functional-in-social-media-Android-app/](https://www.geeksforgeeks.org/implement-like-a-blog-post-functionality-in-social-media-android-app/)

这是**“在 Android Studio 上构建社交媒体应用”**教程的**第 10 部分**，我们将在本文中介绍以下功能:

*   We will introduce Like a Blog. We use two images to achieve this function, one button with a white background and the other button with a blue background.
*   When the user clicks the button for the first time, we change the image to a button with a blue background color and will increase the count. When the user clicks again, then we will decrease the count and change the background white like button.

### **分步实施**

**步骤 1:** **使用 row _ posts.xml 文件**

添加一个相似按钮和总相似[文本视图](https://www.geeksforgeeks.org/working-with-the-textview-in-android/)。

## XML

```java
<Button
  android:id="@+id/like"
  android:layout_width="wrap_content"
  android:layout_height="wrap_content"
  android:layout_weight="1"
  android:autoLink="all"
  android:background="@color/colorWhite"
  android:drawableStart="@drawable/ic_like"
  android:drawableLeft="@drawable/ic_like"
  android:padding="5dp"
  android:text="Like" />
```