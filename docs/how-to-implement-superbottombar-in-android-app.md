# 如何在安卓 App 中实现 SuperBottomBar？

> 原文:[https://www . geeksforgeeks . org/how-implement-super bottombar in-Android-app/](https://www.geeksforgeeks.org/how-to-implement-superbottombar-in-android-app/)

在本文中，我们将实现像 Spotify 中那样的底部导航。我们都遇到过有底部导航栏的应用程序。一些流行的例子包括 Instagram、Snapchat 等。在本文中，让我们学习如何在安卓应用程序中实现一个简单时尚的超级底部工具栏功能底部导航栏。关于创建基本底部导航栏，请参考安卓系统中的[底部导航栏](https://www.geeksforgeeks.org/bottom-navigation-bar-in-android/)。

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:添加依赖和 JitPack 存储库**

导航到**渐变脚本>构建.渐变(模块:应用)**，并在依赖项部分添加以下依赖项。

> 实现' com . github . ertugrulkaragoz:SuperBottomBar:0.4 '

将 JitPack 存储库添加到构建文件中。将其添加到 allprojects{ }部分内存储库末尾的 root build.gradle 中。

> *所有项目{*
> 
> *存储库{*
> 
> *……*
> 
> *maven { URL " https://jitpack . io " }*
> 
> *}*
> 
> *}*

添加这个依赖项后，同步您的项目，现在我们将开始实现它。

**第三步:使用菜单文件**

参考[如何在安卓工作室](https://www.geeksforgeeks.org/how-to-create-menu-folder-menu-file-in-android-studio/)创建菜单文件夹&菜单文件，创建菜单文件。下面是**菜单. xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android">
    <item
        android:id="@+id/home_super_bottom_bar"
        android:icon="@drawable/ic_home_black_24dp"
        android:title="Home" />

    <item
        android:id="@+id/radio_super_bottom_bar"
        android:icon="@drawable/ic_message_black_24dp"
        android:title="Chat" />

    <item
        android:id="@+id/search_super_bottom_bar"
        android:icon="@drawable/ic_search_black_24dp"
        android:title="Search" />

    <item
        android:id="@+id/library_super_bottom_bar"
        android:icon="@drawable/ic_library_books_black_24dp"
        android:title="Book" />

    <item
        android:id="@+id/profile_super_bottom_bar"
        android:icon="@drawable/ic_person_black_24dp"
        android:title="Profile" />

</menu>
```

**第 4 步:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="bottom"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <me.ertugrul.lib.SuperBottomBar
        android:id="@+id/bottomBar"
        android:layout_width="match_parent"
        android:layout_height="55dp"
        app:sbb_menu="@menu/menu" />

</LinearLayout>
```

**第五步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。我们刚刚为底部栏设置了一个监听器。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.os.Bundle;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

import me.ertugrul.lib.OnItemSelectedListener;
import me.ertugrul.lib.SuperBottomBar;

public class MainActivity extends AppCompatActivity {

    SuperBottomBar botttomBar;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initialise the layout
        botttomBar = findViewById(R.id.bottomBar);

        // when we click on any item the show the toast message as selected
        botttomBar.setOnItemSelectListener(new OnItemSelectedListener() {
            @Override
            public void onItemSelect(int i) {
                Toast.makeText(MainActivity.this, "Selected", Toast.LENGTH_LONG).show();
            }
        });
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-592813-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210413170933/superb.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210413170933/superb.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210413170933/superb.mp4)</video>