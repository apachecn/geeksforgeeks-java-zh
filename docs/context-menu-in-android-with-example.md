# 安卓中的上下文菜单，示例

> 原文:[https://www . geeksforgeeks . org/带示例的安卓上下文菜单/](https://www.geeksforgeeks.org/context-menu-in-android-with-example/)

在安卓系统中，有三种类型的[菜单](https://www.geeksforgeeks.org/android-menus/)可用于定义安卓应用程序中的一组选项和动作。安卓应用程序中的菜单列表如下:

1.  Android 选项菜单
2.  安卓上下文菜单
3.  android 弹出菜单

在本文中，我们来讨论一下**上下文菜单**的细节。在安卓系统中，上下文菜单就像一个浮动菜单，当用户长时间按下或点击一个项目时就会出现，有利于实现定义特定内容或参考框架效果的功能。安卓上下文菜单类似于 Windows 或 Linux 中的右键菜单。在安卓系统中，上下文菜单提供了改变用户界面中特定元素或上下文框架的操作，并且可以为任何视图提供上下文菜单。上下文菜单将不支持任何对象快捷方式和对象图标。注意，我们将使用 **Java** 语言来实现这个项目。下面给出了一个示例 GIF，以了解我们将在本文中做什么。

![](img/0fd796ef165e227561384b2186b2555d.png)

### 例子

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

打开**RES->Layout->activity _ main . XML**并编写以下代码。在这个文件中只添加一个[文本视图](https://www.geeksforgeeks.org/textview-widget-in-android-using-java-with-examples/)来显示一个简单的文本。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>

<!--Relative Layout to display all the details-->
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/relLayout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#fff"
    android:padding="16dp"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="20dp"
        android:text="Long press me!"
        android:textColor="#000"
        android:textSize="20sp"
        android:textStyle="bold" />

</RelativeLayout>
```

**步骤 3:使用 Mainactivity.java 文件**

打开 **app - > Java - >包->Mainactivity.java**文件。在这一步中，添加代码以显示上下文菜单。无论何时，应用程序都会在文本上长时间点击，并显示选项数量，以选择特定用途的选项。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.graphics.Color;
import android.os.Bundle;
import android.view.ContextMenu;
import android.view.MenuItem;
import android.view.View;
import android.widget.RelativeLayout;
import android.widget.TextView;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    TextView textView;
    RelativeLayout relativeLayout;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Link those objects with their respective id's
        // that we have given in .XML file
        textView = (TextView) findViewById(R.id.textView);
        relativeLayout = (RelativeLayout) findViewById(R.id.relLayout);

        // here you have to register a view for context menu
        // you can register any view like listview, image view,
        // textview, button etc
        registerForContextMenu(textView);

    }

    @Override
    public void onCreateContextMenu(ContextMenu menu, View v, ContextMenu.ContextMenuInfo menuInfo) {
        super.onCreateContextMenu(menu, v, menuInfo);
        // you can set menu header with title icon etc
        menu.setHeaderTitle("Choose a color");
        // add menu items
        menu.add(0, v.getId(), 0, "Yellow");
        menu.add(0, v.getId(), 0, "Gray");
        menu.add(0, v.getId(), 0, "Cyan");
    }

    // menu item select listener
    @Override
    public boolean onContextItemSelected(MenuItem item) {

        if (item.getTitle() == "Yellow") {
            relativeLayout.setBackgroundColor(Color.YELLOW);
        } else if (item.getTitle() == "Gray") {
            relativeLayout.setBackgroundColor(Color.GRAY);
        } else if (item.getTitle() == "Cyan") {
            relativeLayout.setBackgroundColor(Color.CYAN);
        }

        return true;
    }
}
```

### **输出:在仿真器上运行**

现在，使用 USB 电缆或在仿真器中连接设备，并启动应用程序。用户将看到一个文本。现在长按文本将生成菜单选项，并选择其中一个来执行特定功能。

<video class="wp-video-shortcode" id="video-491431-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200922011103/context.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200922011103/context.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200922011103/context.mp4)</video>