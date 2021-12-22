# 安卓中隐藏动作栏的不同方法，示例

> 原文:[https://www . geeksforgeeks . org/不同的隐藏方式-带示例的安卓中的动作栏/](https://www.geeksforgeeks.org/different-ways-to-hide-action-bar-in-android-with-examples/)

[动作栏](https://www.geeksforgeeks.org/actionbar-in-android-with-example/)是活动中的主要工具栏，可以显示活动标题、应用程序级导航启示和其他交互项目。虽然，动作栏是安卓应用程序的一个重要功能，但有时我们需要将它隐藏在整个应用程序中，或者某个特定的活动中，或者在某些特定的工作中。本文解释并演示了在[安卓应用程序](https://www.geeksforgeeks.org/android-app-development-fundamentals-for-beginners/)中隐藏动作栏的各种方法。隐藏动作栏有多种方法，如下所示:

## **隐藏动作栏的不同方式**

### **1。使用 styles.xml 对整个应用隐藏动作栏**

如果你想在整个应用程序中隐藏动作栏(从所有活动和片段中隐藏)，那么你可以使用这个方法。只需转到**RES->values->style . XML**并将基础应用程序更改为“**主题。AppCompat.Light.NoActionBar** 。
下面是该方法的代码片段，对**style . XML**进行了更改:

## 可扩展标记语言

```
<resources> 
    <!---Base application theme. -->
    <style name="AppTheme" parent="Theme.AppCompat.Light.NoActionBar"> 

        <!---Customize your theme here.-->
        <item name="colorPrimary">@color/colorPrimary</item> 
        <item name="colorPrimaryDark">@color/colorPrimaryDark</item> 
        <item name="colorAccent">@color/colorAccent</item> 
    </style> 
</resources>
```

### **2。使用 Java 代码隐藏动作栏的任何特定活动**

如果您想隐藏特定活动的动作栏，只需在**MainActivity.java**文件中添加几行代码，如下面的代码片段中所述:

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.support.v7.app.AppCompatActivity; 
import android.view.View; 
import android.os.Bundle;

public class MainActivity extends AppCompatActivity { 

    @Override
    protected void onCreate(Bundle savedInstanceState) 
    { 
        super.onCreate(savedInstanceState); 
        setContentView(R.layout.activity_main); 

        // Take instance of Action Bar 
        // using getSupportActionBar and 
        // if it is not Null 
        // then call hide function 
        if (getSupportActionBar() != null) { 
            getSupportActionBar().hide(); 
        } 
    } 
}
```

### **3。使用窗口管理器进行用户交互时隐藏操作栏**

隐藏操作栏的另一种方法是通过窗口管理器设置窗口管理器标志。这种方法使得用户与应用程序交互时隐藏操作栏变得更加容易。您可以使用下面代码中描述的“设置标志”函数。此外，您必须在活动的*设置内容视图()*之前使用标志。下面是隐藏动作栏的 java 文件:

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.support.v7.app.AppCompatActivity; 
import android.view.View; 
import android.os.Bundle; 

public class MainActivity extends AppCompatActivity { 

    @Override
    protected void onCreate(Bundle savedInstanceState) 
    { 
        super.onCreate(savedInstanceState); 

        // set Windows Flags to Full Screen 
        // using setFlags function 
        getWindow().setFlags( 
            WindowManager.LayoutParams.FLAG_FULLSCREEN, 
            WindowManager.LayoutParams.FLAG_FULLSCREEN); 
        setContentView(R.layout.activity_main); 
    } 
}
```

### **4。使用**尝试捕捉隐藏动作栏，使其不参与任何特定活动

如果您想使用 try-catch 块隐藏 Action Bar，只需在 **app > java >包名>MainActivity.java**文件中添加几行代码，如下面的代码片段中所述。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.os.Bundle;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // try block to hide Action bar
        try {
            this.getSupportActionBar().hide();
        }
        // catch block to handle NullPointerException
        catch (NullPointerException e) {
        }
    }
}
```

### 上述方法的实施

*   **创建一个安卓应用程序，并选择上述任何一种方法来隐藏动作栏。**
*   **定义活动。在这里，我们只需使用[约束布局](https://www.geeksforgeeks.org/android-ui-layouts/)中的[文本视图](https://www.geeksforgeeks.org/textview-widget-in-android-using-java-with-examples/)在屏幕上打印“极客头像”:**
*   **导航到 **app > res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是**activity _ main . XML**文件的代码。**

## **可扩展标记语言**

```
<?xml version="1.0" encoding="utf-8"?> 
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context="com.geeksforgeeks.gfg.MainActivity"> 

    <TextView
        android:id="@+id/textView"
        android:layout_width="129dp"
        android:layout_height="55dp"
        android:text="Geeks For Geeks"
        tools:layout_editor_absoluteX="148dp"
        tools:layout_editor_absoluteY="306dp" /> 

</androidx.constraintlayout.widget.ConstraintLayout>
```

*   **按照上面选择的方法复制 Java 代码。**
*   **编译并运行应用程序。**

### ****输出:****

**![](img/0ab6279e4079319a40692b2585bdbb73.png)**