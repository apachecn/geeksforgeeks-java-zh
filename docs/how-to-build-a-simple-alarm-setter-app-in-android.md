# 如何在安卓中搭建一个简单的报警设置器 App？

> 原文:[https://www . geeksforgeeks . org/如何构建一个简单的警报设置器-安卓中的应用/](https://www.geeksforgeeks.org/how-to-build-a-simple-alarm-setter-app-in-android/)

在本文中，我们将看到如何构建一个非常有趣的名为**报警设置器的应用程序。**报警在我们的日常生活中起着至关重要的作用。如今闹钟已经成为我们的叫醒助手。每部手机都与一个报警应用程序相关联。我们将使用 android studio 创建这个应用程序。[安卓工作室](https://www.geeksforgeeks.org/android-studio-main-window/)为安卓手机、平板电脑、安卓穿戴、安卓电视和安卓汽车提供了一个很好的统一环境来构建应用，因为它提供了大量的应用构建功能，并且非常容易使用。下面给出了一个示例视频，以了解我们将在本文中做什么。请注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-577325-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210320163745/GFG_alarm.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210320163745/GFG_alarm.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210320163745/GFG_alarm.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。在这个文件中，我们添加了两个项目**【时间选择】**和**【切换按钮】**。**时间选择器**用于捕捉报警时间，增加**切换按钮**用于设置报警开或关。最初，ToggleButton 设置为 off。当设置警报时，它被设置为开。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <!--Added Time picker just to pick the alarm time-->
    <!--gravity is aligned to center-->
    <TimePicker
        android:id="@+id/timePicker"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center" />

    <!--Added Toggle Button to set the alarm on or off-->
    <!--ByDefault toggleButton is set to false-->
    <ToggleButton
        android:id="@+id/toggleButton"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:layout_margin="20dp"
        android:checked="false"
        android:onClick="OnToggleClicked" />

    <!--"OnToggleClicked" method will be implemented in MainActivity.java -->

</LinearLayout>
```

**第三步:使用****MainActivity.java 文件**

去**MainActivity.java**班。在 MainActivity.java 类中，实现了 onToggleClicked()方法，其中当前的小时和分钟是使用日历设置的。报警服务是使用 AlarmManager 类实现的。闹钟的设置是这样的，它会反复响铃和振动，直到拨动按钮关闭。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.app.AlarmManager;
import android.app.PendingIntent;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.TimePicker;
import android.widget.Toast;
import android.widget.ToggleButton;

import androidx.appcompat.app.AppCompatActivity;

import java.util.Calendar;

public class MainActivity extends AppCompatActivity {
    TimePicker alarmTimePicker;
    PendingIntent pendingIntent;
    AlarmManager alarmManager;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        alarmTimePicker = (TimePicker) findViewById(R.id.timePicker);
        alarmManager = (AlarmManager) getSystemService(ALARM_SERVICE);

    }

    // OnToggleClicked() method is implemented the time functionality
    public void OnToggleClicked(View view) {
        long time;
        if (((ToggleButton) view).isChecked()) {
            Toast.makeText(MainActivity.this, "ALARM ON", Toast.LENGTH_SHORT).show();
            Calendar calendar = Calendar.getInstance();

            // calendar is called to get current time in hour and minute
            calendar.set(Calendar.HOUR_OF_DAY, alarmTimePicker.getCurrentHour());
            calendar.set(Calendar.MINUTE, alarmTimePicker.getCurrentMinute());

            // using intent i have class AlarmReceiver class which inherits
            // BroadcastReceiver
            Intent intent = new Intent(this, AlarmReceiver.class);

            // we call broadcast using pendingIntent
            pendingIntent = PendingIntent.getBroadcast(this, 0, intent, 0);

            time = (calendar.getTimeInMillis() - (calendar.getTimeInMillis() % 60000));
            if (System.currentTimeMillis() > time) {
                // setting time as AM and PM
                if (calendar.AM_PM == 0)
                    time = time + (1000 * 60 * 60 * 12);
                else
                    time = time + (1000 * 60 * 60 * 24);
            }
            // Alarm rings continuously until toggle button is turned off
            alarmManager.setRepeating(AlarmManager.RTC_WAKEUP, time, 10000, pendingIntent);
            // alarmManager.set(AlarmManager.RTC_WAKEUP, System.currentTimeMillis() + (time * 1000), pendingIntent);
        } else {
            alarmManager.cancel(pendingIntent);
            Toast.makeText(MainActivity.this, "ALARM OFF", Toast.LENGTH_SHORT).show();
        }
    }
}
```

**步骤 4:使用广播接收器(警报接收器)类**

在**MainActivity.java**类所在的位置创建一个名为**“alarmreceiver . java”**的新 Java 类。在这个类中**对 Receive()** 方法进行了实现。在这里，我们增加了振动功能和一个默认铃声，当警报时间被安排时，铃声开始振动并响起。以下是**AlarmReceiver.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.BroadcastReceiver;
import android.content.Context;
import android.content.Intent;
import android.media.Ringtone;
import android.media.RingtoneManager;
import android.net.Uri;
import android.os.Build;
import android.os.Vibrator;
import android.widget.Toast;

import androidx.annotation.RequiresApi;

public class AlarmReceiver extends BroadcastReceiver {
    @RequiresApi(api = Build.VERSION_CODES.Q)
    @Override
    // implement onReceive() method
    public void onReceive(Context context, Intent intent) {

        // we will use vibrator first
        Vibrator vibrator = (Vibrator) context.getSystemService(context.VIBRATOR_SERVICE);
        vibrator.vibrate(4000);

        Toast.makeText(context, "Alarm! Wake up! Wake up!", Toast.LENGTH_LONG).show();
        Uri alarmUri = RingtoneManager.getDefaultUri(RingtoneManager.TYPE_ALARM);
        if (alarmUri == null) {
            alarmUri = RingtoneManager.getDefaultUri(RingtoneManager.TYPE_NOTIFICATION);
        }

        // setting default ringtone
        Ringtone ringtone = RingtoneManager.getRingtone(context, alarmUri);

        // play ringtone
        ringtone.play();
    }
}
```