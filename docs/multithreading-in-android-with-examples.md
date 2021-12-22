# 安卓多线程示例

> 原文:[https://www . geeksforgeeks . org/Android 中的多线程与示例/](https://www.geeksforgeeks.org/multithreading-in-android-with-examples/)

同时处理多个任务是**多任务**。同理，一台机器中同时运行的多个线程称为 [**多线程**](https://www.geeksforgeeks.org/multithreading-in-operating-system/) 。从技术上讲，[螺纹](https://www.geeksforgeeks.org/thread-in-operating-system/)是[工艺](https://www.geeksforgeeks.org/states-of-a-process-in-operating-systems/)的一个单元。多个这样的线程组合起来形成一个进程。这意味着当一个进程中断时，有相等数量的线程可用。
**例如**、*自动更正*是软件查找当前正在输入的单词中的错误的过程。无休止地检查错误并同时提供建议是多线程过程的一个例子。

#### 安卓应用示例:

让我们尝试在安卓应用程序的帮助下可视化多线程。在下面的例子中，3 个线程在按钮点击时同时启动，并发工作。

**进场:**
**第一步:**在 **activity_main.xml** 中添加以下代码。这里我们添加三个[文本视图](https://www.geeksforgeeks.org/textview-widget-in-android-using-java-with-examples/)和一个[按钮](https://www.geeksforgeeks.org/button-in-kotlin/)。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/tv1"
        android:layout_width="75sp"
        android:layout_height="75sp"
        android:background="@color/colorPrimary"
        android:textColor="@color/colorAccent"
        android:gravity="center"
        android:textSize="10sp"
        android:layout_centerVertical="true"
        android:layout_toLeftOf="@id/tv2"
        />

    <TextView
        android:id="@+id/tv2"
        android:layout_width="75sp"
        android:layout_height="75sp"
        android:background="@color/colorPrimary"
        android:textColor="@color/colorAccent"
        android:gravity="center"
        android:textSize="10sp"
        android:layout_centerInParent="true"
        />

    <TextView
        android:id="@+id/tv3"
        android:layout_width="75sp"
        android:layout_height="75sp"
        android:background="@color/colorPrimary"
        android:textColor="@color/colorAccent"
        android:gravity="center"
        android:textSize="10sp"
        android:layout_centerVertical="true"
        android:layout_toRightOf="@id/tv2"
        />

    <Button
        android:id="@+id/btnStart"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Start"
        android:layout_centerHorizontal="true"
        android:layout_below="@id/tv2"
        />

</RelativeLayout>
```