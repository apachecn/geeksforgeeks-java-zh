# 如何使用光标在安卓应用中获取已保存的联系人？

> 原文:[https://www . geeksforgeeks . org/如何使用光标获取安卓应用程序中保存的联系人/](https://www.geeksforgeeks.org/how-to-get-saved-contacts-in-android-application-using-cursor/)

电话联系人对每个人来说都是非常重要的数据来源，因此访问电话联系人是许多应用程序(如 Truecaller)的主要功能，以帮助他们的用户并为他们提供更好的体验。我们在手机中都有一个默认的应用程序来管理联系人，但是如果我们创建自己的应用程序来读取所有保存的联系人并将其显示给用户，会发生什么呢？我们可以使用该应用程序来备份我们的联系人。因此，在本文中，我们将学习如何开发一个读取联系人的应用程序。

> **注意:**一个**光标**是一个包含针对安卓数据库进行的特定查询的结果集的类。这个类有一个应用编程接口，它提供了读取查询返回的列的功能，还有助于遍历结果集的行。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将显示一个[按钮](https://www.geeksforgeeks.org/handling-click-events-button-android/)，当我们点击该按钮时，它会将所有保存的联系人(他们的姓名和号码)添加到我们应用程序的[列表视图](https://www.geeksforgeeks.org/android-listview-in-java-with-example/)中。请注意，我们必须允许我们的应用程序读取我们的电话联系人。我们将使用 **Java** 语言来开发这个项目。

### 逐步实施

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:添加权限**

现在，导航到**应用程序>清单>和安卓清单. xml** 文件，并在下面添加读取联系人的权限。

**步骤 3:使用 activity_main.xml 文件**

现在是时候设计应用程序的布局了。因此，导航到**应用程序> res >布局> activity_main.xml** 并将下面编写的代码粘贴到 **activity_main.xml** 文件中。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/relative_layout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--Button to perform clicking event to 
        access contacts list inside listView-->
    <Button
        android:id="@+id/Button"
        android:layout_width="150dp"
        android:layout_height="52dp"
        android:layout_centerHorizontal="true"
        android:layout_margin="12dp"
        android:background="#0F9D58"
        android:text="Click Here"
        android:textColor="#FFFFFF" />

    <!--ListView to show all saved contacts-->
    <ListView
        android:id="@+id/ListView"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:layout_below="@+id/Button" />

</RelativeLayout>
```

**步骤 4:使用 MainActivity.java 文件**

导航至 **app > java >包名>MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.database.Cursor;
import android.os.Bundle;
import android.provider.ContactsContract;
import android.view.View;
import android.widget.Button;
import android.widget.ListView;

import androidx.appcompat.app.AppCompatActivity;
import androidx.cursoradapter.widget.SimpleCursorAdapter;

public class MainActivity extends AppCompatActivity {
    Cursor cursor;
    ListView listView;
    Button button;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // declaring listView using findViewById()
        listView = findViewById(R.id.ListView);

        // declaring button using findViewById()
        button = findViewById(R.id.Button);

        // set OnClickListener() to the button
        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // calling of getContacts()
                getContacts();
            }
        });
    }

    public void getContacts() {

        // create cursor and query the data
        cursor = getContentResolver().query(ContactsContract.CommonDataKinds.Phone.CONTENT_URI, null, null, null, null);
        startManagingCursor(cursor);

        // data is a array of String type which is
        // used to store Number ,Names and id.
        String[] data = {ContactsContract.CommonDataKinds.Phone.NUMBER, ContactsContract.CommonDataKinds.Phone.DISPLAY_NAME, ContactsContract.CommonDataKinds.Phone._ID};
        int[] to = {android.R.id.text1, android.R.id.text2};

        // creation of adapter using SimpleCursorAdapter class
        SimpleCursorAdapter adapter = new SimpleCursorAdapter(this, android.R.layout.simple_list_item_2, cursor, data, to);

        // Calling setAdaptor() method to set created adapter
        listView.setAdapter(adapter);
        listView.setChoiceMode(ListView.CHOICE_MODE_MULTIPLE);
    }
}
```

恭喜，现在我们的应用程序已经准备好了，所以点击**运行**按钮。这是应用程序的输出视频。

### 输出:

<video class="wp-video-shortcode" id="video-556956-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210201002606/gfg_output3.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210201002606/gfg_output3.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210201002606/gfg_output3.mp4)</video>