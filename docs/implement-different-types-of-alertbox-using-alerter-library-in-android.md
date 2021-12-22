# 在安卓中使用 Alerter 库实现不同类型的 AlertBox】

> 原文:[https://www . geeksforgeeks . org/implement-不同类型的 alertbox-使用-alerter-library-in-Android/](https://www.geeksforgeeks.org/implement-different-types-of-alertbox-using-alerter-library-in-android/)

在本文中，我们将实现一个与 AlertBox 相关的非常重要的特性。通常，我们会创建一个 AlertBox 来显示一些重要的内容。在这里，我们将学习如何使用警报库在我们的安卓应用程序中实现该功能。下面给出了一个示例视频，以了解我们将在本文中做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-606092-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210516143437/alerter.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210516143437/alerter.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210516143437/alerter.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:添加依赖和 JitPack 存储库**

导航到**渐变脚本>构建.渐变(模块:应用)**，并在依赖项部分添加以下依赖项。

> 实现' com . tapa do . Android:alert er:2 . 0 . 4 '

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

**步骤 3:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:keepScreenOn="true"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/txt1"
        android:layout_width="match_parent"
        android:layout_height="48dp"
        android:layout_margin="10dp"
        android:background="#fff"
        android:padding="8dp"
        android:text="Simple Alert "
        android:textColor="#000000"
        android:textSize="24dp"
        android:textStyle="bold" />

    <TextView
        android:id="@+id/txt2"
        android:layout_width="match_parent"
        android:layout_height="48dp"
        android:layout_margin="10dp"
        android:background="#fff"
        android:padding="8dp"
        android:text="with Background Color "
        android:textColor="#000000"
        android:textSize="24dp"
        android:textStyle="bold" />

    <TextView
        android:id="@+id/txt3"
        android:layout_width="match_parent"
        android:layout_height="48dp"
        android:layout_margin="10dp"
        android:background="#fff"
        android:padding="8dp"
        android:text="with Icon"
        android:textColor="#000000"
        android:textSize="24dp"
        android:textStyle="bold" />

    <TextView
        android:id="@+id/txt4"
        android:layout_width="match_parent"
        android:layout_height="48dp"
        android:layout_margin="10dp"
        android:background="#fff"
        android:padding="8dp"
        android:text="with On Screen Duration "
        android:textColor="#000000"
        android:textSize="24dp"
        android:textStyle="bold" />

    <TextView
        android:id="@+id/txt5"
        android:layout_width="match_parent"
        android:layout_height="48dp"
        android:layout_margin="10dp"
        android:background="#fff"
        android:padding="8dp"
        android:text="without Title "
        android:textColor="#000000"
        android:textSize="24dp"
        android:textStyle="bold" />

    <TextView
        android:id="@+id/txt6"
        android:layout_width="match_parent"
        android:layout_height="48dp"
        android:layout_margin="10dp"
        android:background="#fff"
        android:padding="8dp"
        android:text="with OnClickListener "
        android:textColor="#000000"
        android:textSize="24dp"
        android:textStyle="bold" />

    <TextView
        android:id="@+id/txt7"
        android:layout_width="match_parent"
        android:layout_height="48dp"
        android:layout_margin="10dp"
        android:background="#fff"
        android:padding="8dp"
        android:text="with Verbose Text"
        android:textColor="#000000"
        android:textSize="24dp"
        android:textStyle="bold" />

    <TextView
        android:id="@+id/txt8"
        android:layout_width="match_parent"
        android:layout_height="48dp"
        android:layout_margin="10dp"
        android:background="#fff"
        android:padding="8dp"
        android:text="with Swipe To Dismiss"
        android:textColor="#000000"
        android:textSize="24dp"
        android:textStyle="bold" />

    <TextView
        android:id="@+id/txt9"
        android:layout_width="match_parent"
        android:layout_height="48dp"
        android:layout_margin="10dp"
        android:background="#fff"
        android:padding="8dp"
        android:text="with Progress Bar"
        android:textColor="#000000"
        android:textSize="24dp"
        android:textStyle="bold" />

    <TextView
        android:id="@+id/txt10"
        android:layout_width="match_parent"
        android:layout_height="48dp"
        android:layout_margin="10dp"
        android:background="#fff"
        android:padding="8dp"
        android:text="with Visibility Callbacks"
        android:textColor="#000000"
        android:textSize="24dp"
        android:textStyle="bold" />

</LinearLayout>
```

**第四步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.os.Bundle;
import android.view.View;
import android.view.WindowManager;
import android.widget.TextView;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

import com.tapadoo.alerter.Alerter;
import com.tapadoo.alerter.OnHideAlertListener;
import com.tapadoo.alerter.OnShowAlertListener;

public class MainActivity extends AppCompatActivity {

    TextView txt1, txt2, txt3, txt4, txt5, txt6, txt7, txt8, txt9, txt10;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        getWindow().addFlags(WindowManager.LayoutParams.FLAG_KEEP_SCREEN_ON);
        txt1 = findViewById(R.id.txt1);
        txt2 = findViewById(R.id.txt2);
        txt3 = findViewById(R.id.txt3);
        txt4 = findViewById(R.id.txt4);
        txt5 = findViewById(R.id.txt5);
        txt6 = findViewById(R.id.txt6);
        txt7 = findViewById(R.id.txt7);
        txt8 = findViewById(R.id.txt8);
        txt9 = findViewById(R.id.txt9);
        txt10 = findViewById(R.id.txt10);

        // click on text to show alert
        txt1.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                simpleAlert();
            }
        });

        // click on text to show alert
        txt2.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                withBackgroundColor();
            }
        });

        // click on text to show alert
        txt3.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                withIcon();
            }
        });

        // click on text to show alert
        txt4.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                withOnScreenDuration();
            }
        });

        // click on text to show alert
        txt5.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                withoutTitle();
            }
        });

        // click on text to show alert
        txt6.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                withOnClickListener();
            }
        });

        // click on text to show alert
        txt7.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                withVerboseText();
            }
        });

        // click on text to show alert
        txt8.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                withSwipeToDismiss();
            }
        });

        // click on text to show alert
        txt9.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                withProgressBar();
            }
        });

        // click on text to show alert
        txt10.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                withVisibilityCallbacks();
            }
        });
    }

    // show simple alert
    public void simpleAlert() {
        Alerter.create(MainActivity.this).setTitle("Geeks For Geeks")
                .setText("A portal for Computer Science Student").show();
    }

    // set background color using setBackgroundColorRes
    public void withBackgroundColor() {
        Alerter.create(this).setTitle("Geeks For Geeks")
                // or setBackgroundColorInt(Color.CYAN)
                .setText("A portal for Computer Science Student").setBackgroundColorRes(R.color.purple_200) 
                .show();
    }

    // without title
    public void withoutTitle() {
        Alerter.create(this)
                .setText("A portal for Computer Science Student").show();

    }

    public void withOnClickListener() {
        Alerter.create(this).setTitle("Geeks For Geeks")
                .setText("A portal for Computer Science Student").setDuration(10000).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                // showing simple toast to user when clicked
                Toast.makeText(MainActivity.this, "You Clicked Me", Toast.LENGTH_LONG).show();
            }
        }).show();
    }

    public void withVerboseText() {
        Alerter.create(this).setTitle("Geeks For Geeks")
                .setText("A portal for Computer Science Student"
                        + "A portal for Computer Science Student" + "A portal for Computer Science Student").show();
    }

    // set icon using setIcon
    public void withIcon() {
        Alerter.create(this).setTitle("Geeks For Geeks")
                // Optional - Removes white tint
                .setText("A portal for Computer Science Student").setIcon(R.drawable.ic_launcher_foreground).setIconColorFilter(0) 
                .show();
    }

    // set screen duration using setDuration
    public void withOnScreenDuration() {
        Alerter.create(this).setTitle("Geeks For Geeks")
                // set the duration in milli seconds
                .setText("A portal for Computer Science Student").setDuration(10000) 
                .show();
    }

    // swipe toast to dismiss
    public void withSwipeToDismiss() {
        Alerter.create(this).setTitle("Geeks For Geeks")
                // enabled swipe to dismiss
                .setText("A portal for Computer Science Student").enableSwipeToDismiss() 
                .show();
    }

    // show progress bar
    public void withProgressBar() {
        Alerter.create(this).setTitle("Geeks For Geeks")
                // enables the progress
                .setText("A portal for Computer Science Student").enableProgress(true) 
                  // set color of the progress
                .setProgressColorRes(R.color.purple_200) 
                .show();
    }

    public void withVisibilityCallbacks() {
        Alerter.create(this).setTitle("Geeks For Geeks")
                .setText("A portal for Computer Science Student").setDuration(10000).setOnShowListener(new OnShowAlertListener() {
            @Override
            public void onShow() {
                // showing simple toast when it is shown
                Toast.makeText(MainActivity.this, "On Show ", Toast.LENGTH_SHORT).show();
            }
        }).setOnHideListener(new OnHideAlertListener() {
            @Override
            public void onHide() {
                // showing simple toast to user when  it is hidden
                Toast.makeText(MainActivity.this, "On Hide ", Toast.LENGTH_SHORT).show();

            }
        }).show();
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-606092-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210516143437/alerter.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210516143437/alerter.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210516143437/alerter.mp4)</video>