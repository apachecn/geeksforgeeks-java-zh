# 如何在安卓中禁用日期选择器中的上一个或未来日期？

> 原文:[https://www . geesforgeks . org/如何禁用安卓中的日期选择器中的先前或未来日期/](https://www.geeksforgeeks.org/how-to-disable-previous-or-future-dates-in-datepicker-in-android/)

在本文中，我们将在日期选择器中禁用以前或将来的日期。大多数时候，当我们在安卓系统中使用日期选择器时，我们会看到其中的所有日期都是启用的。我们可以选择任何一个日期。但是在这里，我们将看到如何禁用过去或未来的日期。当我们向某人分配任务时，禁用“过去日期”会很有用。那么所选日期必须在未来。当我们询问某人的出生日期时，禁用“以前的日期”会很有用。那么所选日期必须在过去。让我们实现这个特性。

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

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
    android:orientation="vertical"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/editext"
        android:layout_width="match_parent"
        android:layout_height="wrap_content" />

</LinearLayout>
```

**步骤 3:使用 MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。

**最大日期:**

用 **getDatePicker()** 从 DatePicker 日志中获取日期选择器。使用**设置最大日期()**将最大日期设置为当前日期:

> **注:**要求 API 等级 11。

```
datePicker.getDatePicker().setMaxDate(calendar.getTimeInMillis());
```

以下是**MainActivity.java**文件的代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.app.DatePickerDialog;
import android.os.Build;
import android.os.Bundle;
import android.view.View;
import android.widget.EditText;

import androidx.annotation.RequiresApi;
import androidx.appcompat.app.AppCompatActivity;

import java.util.Calendar;

public class MainActivity extends AppCompatActivity {

    EditText editText;
    DatePickerDialog datePicker;

    @RequiresApi(api = Build.VERSION_CODES.N)
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initialising the calendar
        final Calendar calendar = Calendar.getInstance();

        // initialising the layout
        editText = findViewById(R.id.editext);
        final int day = calendar.get(Calendar.DAY_OF_MONTH);
        final int year = calendar.get(Calendar.YEAR);
        final int month = calendar.get(Calendar.MONTH);

        // initialising the datepickerdialog
        datePicker = new DatePickerDialog(MainActivity.this);

        // click on edittext to set the value
        editText.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                datePicker = new DatePickerDialog(MainActivity.this, new DatePickerDialog.OnDateSetListener() {
                    @Override
                    public void onDateSet(android.widget.DatePicker view, int year, int month, int dayOfMonth) {
                        // adding the selected date in the edittext
                        editText.setText(dayOfMonth + "/" + (month + 1) + "/" + year);
                    }
                }, year, month, day);

                // set maximum date to be selected as today
                datePicker.getDatePicker().setMaxDate(calendar.getTimeInMillis());

                // show the dialog
                datePicker.show();
            }
        });
    }
}
```

**最小日期:**

同样，用 **getDatePicker()** 从 datepickerlog 获取日期选择器。使用**设置日期()**:**T5 将最小日期设置为当前日期**

```
datePicker.getDatePicker().setMinDate(calendar.getTimeInMillis());
```

以下是**MainActivity.java**文件的代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.app.DatePickerDialog;
import android.os.Build;
import android.os.Bundle;
import android.view.View;
import android.widget.EditText;

import androidx.annotation.RequiresApi;
import androidx.appcompat.app.AppCompatActivity;

import java.util.Calendar;

public class MainActivity extends AppCompatActivity {

    EditText editText;
    DatePickerDialog datePicker;

    @RequiresApi(api = Build.VERSION_CODES.N)
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initialising the calendar
        final Calendar calendar = Calendar.getInstance();

        // initialising the layout
        editText = findViewById(R.id.editext);
        final int day = calendar.get(Calendar.DAY_OF_MONTH);
        final int year = calendar.get(Calendar.YEAR);
        final int month = calendar.get(Calendar.MONTH);

        // initialising the datepickerdialog
        datePicker = new DatePickerDialog(MainActivity.this);

        // click on edittext to set the value
        editText.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                datePicker = new DatePickerDialog(MainActivity.this, new DatePickerDialog.OnDateSetListener() {
                    @Override
                    public void onDateSet(android.widget.DatePicker view, int year, int month, int dayOfMonth) {
                        // adding the selected date in the edittext
                        editText.setText(dayOfMonth + "/" + (month + 1) + "/" + year);
                    }
                }, year, month, day);

                // set maximum date to be selected as today
                datePicker.getDatePicker().setMinDate(calendar.getTimeInMillis());

                // show the dialog
                datePicker.show();
            }
        });
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-595106-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210421000407/mindate.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210421000407/mindate.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210421000407/mindate.mp4)</video>