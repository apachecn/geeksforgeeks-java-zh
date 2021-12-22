# 获取安卓手机中安装的所有应用列表的不同方法

> 原文:[https://www . geeksforgeeks . org/不同方式获取安装在您的安卓手机中的所有应用列表/](https://www.geeksforgeeks.org/different-ways-to-get-list-of-all-apps-installed-in-your-android-phone/)

在本文中，我们将显示您的安卓手机上安装的所有应用程序的列表。因此，在这里我们将学习如何以三种不同的方式实现该特性。请注意，我们将使用 **Java** 语言来实现这个项目。

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目。](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:layout_gravity="center"
    android:gravity="center"
    android:orientation="vertical"
    android:padding="16sp"
    tools:context=".MainActivity">

    <Button
        android:id="@+id/check"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:onClick="getallapps"
        android:text="Get Installed Apps"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

    <TextView
        android:id="@+id/totalapp"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/check" />

    <ListView
        android:id="@+id/listview"
        android:layout_width="365dp"
        android:layout_height="523dp"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toBottomOf="@+id/totalapp"
        tools:layout_editor_absoluteY="150dp" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

### 方法 1

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.pm.ApplicationInfo;
import android.content.pm.PackageManager;
import android.os.Bundle;
import android.view.View;
import android.widget.ArrayAdapter;
import android.widget.ListView;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

import java.util.List;

public class MainActivity extends AppCompatActivity {

    ListView listView;
    TextView text;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initialise layout
        listView = findViewById(R.id.listview);
        text = findViewById(R.id.totalapp);
    }

    public void getallapps(View view) {
        // get list of all the apps installed
        List<ApplicationInfo> infos = getPackageManager().getInstalledApplications(PackageManager.GET_META_DATA);
        // create a list with size of total number of apps
        String[] apps = new String[infos.size()];
        int i = 0;
        // add all the app name in string list
        for (ApplicationInfo info : infos) {
            apps[i] = info.packageName;
            i++;
        }
        // set all the apps name in list view
        listView.setAdapter(new ArrayAdapter<String>(MainActivity.this, android.R.layout.simple_list_item_1, apps));
        // write total count of apps available.
        text.setText(infos.size() + " Apps are installed");
    }

    @Override
    protected void onStart() {
        super.onStart();

    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-628560-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210611131910/totalapp.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210611131910/totalapp.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210611131910/totalapp.mp4)</video>

### 方法 2

转到**MainActivity.java**文件，参考以下代码。下面是 MainActivity.java 文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.pm.PackageInfo;
import android.os.Bundle;
import android.view.View;
import android.widget.ArrayAdapter;
import android.widget.ListView;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

import java.util.List;

public class MainActivity extends AppCompatActivity {

    ListView listView;
    TextView text;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initialise layout
        listView = findViewById(R.id.listview);
        text = findViewById(R.id.totalapp);
    }

    public void getallapps(View view) {
        // get list of all the apps installed
        List<PackageInfo> packList = getPackageManager().getInstalledPackages(0);
        String[] apps = new String[packList.size()];
        for (int i = 0; i < packList.size(); i++) {
            PackageInfo packInfo = packList.get(i);
            apps[i] = packInfo.applicationInfo.loadLabel(getPackageManager()).toString();
        }
        // set all the apps name in list view
        listView.setAdapter(new ArrayAdapter<String>(MainActivity.this, android.R.layout.simple_list_item_1, apps));
        // write total count of apps available.
        text.setText(packList.size() + " Apps are installed");
    }

    @Override
    protected void onStart() {
        super.onStart();

    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-628560-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210619130230/allapp.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210619130230/allapp.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210619130230/allapp.mp4)</video>

### 方法 3

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.Intent;
import android.content.pm.PackageManager;
import android.content.pm.ResolveInfo;
import android.content.res.Resources;
import android.os.Bundle;
import android.view.View;
import android.widget.ArrayAdapter;
import android.widget.ListView;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

import java.util.ArrayList;
import java.util.List;

public class MainActivity extends AppCompatActivity {

    ListView listView;
    TextView text;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initialise layout
        listView = findViewById(R.id.listview);
        text = findViewById(R.id.totalapp);
    }

    public void getallapps(View view) throws PackageManager.NameNotFoundException {
        final Intent mainIntent = new Intent(Intent.ACTION_MAIN, null);
        mainIntent.addCategory(Intent.CATEGORY_LAUNCHER);

        // get list of all the apps installed
        List<ResolveInfo> ril = getPackageManager().queryIntentActivities(mainIntent, 0);
        List<String> componentList = new ArrayList<String>();
        String name = null;
        int i = 0;

        // get size of ril and create a list
        String[] apps = new String[ril.size()];
        for (ResolveInfo ri : ril) {
            if (ri.activityInfo != null) {
                // get package
                Resources res = getPackageManager().getResourcesForApplication(ri.activityInfo.applicationInfo);
                // if activity label res is found
                if (ri.activityInfo.labelRes != 0) {
                    name = res.getString(ri.activityInfo.labelRes);
                } else {
                    name = ri.activityInfo.applicationInfo.loadLabel(
                            getPackageManager()).toString();
                }
                apps[i] = name;
                i++;
            }
        }
        // set all the apps name in list view
        listView.setAdapter(new ArrayAdapter<String>(MainActivity.this, android.R.layout.simple_list_item_1, apps));
        // write total count of apps available.
        text.setText(ril.size() + " Apps are installed");
    }

    @Override
    protected void onStart() {
        super.onStart();

    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-628560-3" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210619131754/downloadapp.mp4?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/20210619131754/downloadapp.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210619131754/downloadapp.mp4)</video>