# 如何在安卓系统中使用接近传感器？

> 原文:[https://www . geesforgeks . org/如何使用安卓接近传感器/](https://www.geeksforgeeks.org/how-to-use-proximity-sensor-in-android/)

接近传感器是我们几乎每天都在使用的移动设备中的传感器之一。该传感器位于您手机的顶部。传感器用于检测手机附近是否存在任何物体。这种传感器用于许多通话应用中，当用户将手机放在耳朵上收听时，屏幕会自动关闭，以避免通话时不必要的屏幕触摸事件。处理这种情况需要应用程序使用接近传感器。在本文中，我们将看到如何在我们的安卓应用程序中使用接近传感器。

## 接近传感器的实现

下面给出了一个示例视频，以了解我们将在本文中做什么。注意，我们将使用 **Java** 语言来实现这个项目。

### 逐步实施

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在我们的安卓应用**中添加使用接近传感器的权限

在 **AndroidManifest.xml** 文件中添加以下一行。

**步骤 3:使用 activity_main.xml**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/container"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <!--Text view to display sensor status-->
    <TextView
        android:id="@+id/sensorStatusTV"
        android:layout_width="fill_parent"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:textAlignment="center"
        android:textSize="50dp" />

</RelativeLayout>
```

**步骤 4:使用 MainActivity.java 文件**

导航到**应用程序> java >您的应用程序包名称>MainActivity.java**文件。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.Context;
import android.hardware.Sensor;
import android.hardware.SensorEvent;
import android.hardware.SensorEventListener;
import android.hardware.SensorManager;
import android.os.Bundle;
import android.widget.TextView;
import android.widget.Toast;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    // Creating variables for text view, 
    // sensor manager and our sensor.
    TextView sensorStatusTV;
    SensorManager sensorManager;
    Sensor proximitySensor;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        sensorStatusTV = findViewById(R.id.sensorStatusTV);

        // calling sensor service.
        sensorManager = (SensorManager) getSystemService(Context.SENSOR_SERVICE);

        // from sensor service we are 
        // calling proximity sensor
        proximitySensor = sensorManager.getDefaultSensor(Sensor.TYPE_PROXIMITY);

        // handling the case if the proximity 
        // sensor is not present in users device.
        if (proximitySensor == null) {
            Toast.makeText(this, "No proximity sensor found in device.", Toast.LENGTH_SHORT).show();
            finish();
        } else {
            // registering our sensor with sensor manager.
            sensorManager.registerListener(proximitySensorEventListener,
                    proximitySensor,
                    SensorManager.SENSOR_DELAY_NORMAL);
        }
    }

    // calling the sensor event class to detect
    // the change in data when sensor starts working.
    SensorEventListener proximitySensorEventListener = new SensorEventListener() {
        @Override
        public void onAccuracyChanged(Sensor sensor, int accuracy) {
            // method to check accuracy changed in sensor.
        }

        @Override
        public void onSensorChanged(SensorEvent event) {
            // check if the sensor type is proximity sensor.
            if (event.sensor.getType() == Sensor.TYPE_PROXIMITY) {
                if (event.values[0] == 0) {
                    // here we are setting our status to our textview..
                    // if sensor event return 0 then object is closed
                    // to sensor else object is away from sensor.
                    sensorStatusTV.setText("Near");
                } else {
                    sensorStatusTV.setText("Away");
                }
            }
        }
    };
}
```

### 输出:

现在，在您的真实设备上运行该应用程序来测试传感器。测试应用程序时，将任何物体或手移向手机顶部。

<video class="wp-video-shortcode" id="video-530520-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201216001456/Screenrecorder-2020-12-16-00-11-25-335.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201216001456/Screenrecorder-2020-12-16-00-11-25-335.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201216001456/Screenrecorder-2020-12-16-00-11-25-335.mp4)</video>