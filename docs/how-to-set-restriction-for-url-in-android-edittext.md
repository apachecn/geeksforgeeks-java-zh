# 如何在安卓编辑文本中设置网址限制？

> 原文:[https://www . geeksforgeeks . org/如何设置 android 中 url 的限制-edittext/](https://www.geeksforgeeks.org/how-to-set-restriction-for-url-in-android-edittext/)

在本文中，我们将在网址的编辑文本中设置限制。每当我们创建任何形式，我们想得到用户的投资组合网站，或者即使我们想限制用户写唯一的网址，那么我们可以使用这个功能。这使得用户对用户只写网址。

### **逐级**逐级**实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** ，并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。我们将在这个文件中创建一个简单的[编辑文本](https://www.geeksforgeeks.org/edittext-widget-in-android-using-java-with-examples/)。

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
        android:id="@+id/aurl"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Enter Url" />

</LinearLayout>
```

**第三步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.os.Bundle;
import android.text.Editable;
import android.text.TextWatcher;
import android.util.Patterns;
import android.widget.EditText;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText addurl;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        addurl = findViewById(R.id.aurl);

        // when we add text in the edit text 
        // it will check for the pattern of text
        addurl.addTextChangedListener(new TextWatcher() {
            @Override
            public void beforeTextChanged(CharSequence s, int start, int count, int after) {

            }

            // whenever text size changes it will check
            @Override
            public void onTextChanged(CharSequence s, int start, int before, int count) {
                // if text written matches the pattern then
                // it will show a toast of pattern matches
                if (Patterns.WEB_URL.matcher(addurl.getText().toString()).matches()) {
                    Toast.makeText(MainActivity.this, "Pattern Matches", Toast.LENGTH_SHORT).show();
                } else {
                    // otherwise show error of invalid url
                    addurl.setError("Invalid Url");
                }
            }

            @Override
            public void afterTextChanged(Editable s) {

            }
        });
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-590680-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210405001950/urlpattern.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210405001950/urlpattern.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210405001950/urlpattern.mp4)</video>