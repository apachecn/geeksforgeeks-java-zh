# 如何在安卓系统中实现多选下拉？

> 原文:[https://www . geesforgeks . org/如何实现-多选-安卓下拉菜单/](https://www.geeksforgeeks.org/how-to-implement-multiselect-dropdown-in-android/)

在本文中，我们将看到如何在 android studio 中制作一个 MultiSelect DrOp，并从下拉列表中选择多个项目。多选下拉菜单的优点。

*   它是列表框的一个很好的替代品，因为它使用更少的空间，并且可以完成与列表框相同的工作，并且为用户界面提供了良好的外观。
*   下拉列表是大多数用户熟悉的选择机制，因为它们在网络和安卓应用中都被广泛使用。
*   用户可以选择他/她喜欢的多个项目。

### 我们将在本文中构建什么？

在本文中，我们将使用一个文本视图，并且我们将在那个[文本视图](https://www.geeksforgeeks.org/textview-widget-in-android-using-java-with-examples/)上设置一个 onClickListener，这样每当用户点击它时，下拉列表就会出现。在下拉列表中，我们将提供选择和多个项目、清除所选项目的功能，以及取消选择过程的[按钮](https://www.geeksforgeeks.org/button-in-kotlin/)。注意，我们将使用 **Java** 语言来实现这个应用程序。下面给出了一个示例视频，以了解我们将在本文中做什么。

<video class="wp-video-shortcode" id="video-650587-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210723110134/Screenrecorder-2021-07-23-10-41-18-942.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210723110134/Screenrecorder-2021-07-23-10-41-18-942.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210723110134/Screenrecorder-2021-07-23-10-41-18-942.mp4)</video>

### 逐步实施

**第一步:创建新项目**

*   打开一个新项目。
*   我们将使用 Java 语言来处理空活动。保持所有其他选项不变。
*   您可以在方便的时候更改项目的名称。
*   将有两个名为 **activity_main.xml 和 MainActivity.java**的默认文件。

如果你不知道如何在安卓工作室创建新项目，那么你可以参考[如何在安卓工作室创建/启动新项目？](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)

**第二步:处理 activity_main.xml 文件**

在这里，我们将设计应用程序的用户界面。我们将在他们各自的作品中使用以下组件:

*   文本视图:允许用户点击它，以便出现一个下拉列表，并显示其中的选定项目。
*   下拉箭头:向用户指示单击后将完成某些操作。

在 **activity_main.xml** 文件中使用以下代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<!-- Relative layout as parent layout-->
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="16dp"
    tools:context=".MainActivity">

    <!-- text view to display selected items-->
    <TextView
        android:id="@+id/textView"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:background="@android:drawable/editbox_background"
        android:drawableRight="@android:drawable/arrow_down_float"
        android:drawablePadding="16dp"
        android:hint="Select Language"
        android:padding="12dp" />

</RelativeLayout>
```

执行上述代码后，activity_main.xml 文件的设计如下所示。

![](img/bfe506c1aa8e092c7f0fb8b97227b33f.png)

**第三步:使用 MainActivity.java 文件**

转到**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
import android.content.DialogInterface;
import android.os.Bundle;
import android.view.View;
import android.widget.TextView;

import androidx.appcompat.app.AlertDialog;
import androidx.appcompat.app.AppCompatActivity;

import java.util.ArrayList;
import java.util.Collections;

public class MainActivity extends AppCompatActivity {

    // initialize variables
    TextView textView;
    boolean[] selectedLanguage;
    ArrayList<Integer> langList = new ArrayList<>();
    String[] langArray = {"Java", "C++", "Kotlin", "C", "Python", "Javascript"};

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // assign variable
        textView = findViewById(R.id.textView);

        // initialize selected language array
        selectedLanguage = new boolean[langArray.length];

        textView.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

                // Initialize alert dialog
                AlertDialog.Builder builder = new AlertDialog.Builder(MainActivity.this);

                // set title
                builder.setTitle("Select Language");

                // set dialog non cancelable
                builder.setCancelable(false);

                builder.setMultiChoiceItems(langArray, selectedLanguage, new DialogInterface.OnMultiChoiceClickListener() {
                    @Override
                    public void onClick(DialogInterface dialogInterface, int i, boolean b) {
                        // check condition
                        if (b) {
                            // when checkbox selected
                            // Add position  in lang list
                            langList.add(i);
                            // Sort array list
                            Collections.sort(langList);
                        } else {
                            // when checkbox unselected
                            // Remove position from langList
                            langList.remove(i);
                        }
                    }
                });

                builder.setPositiveButton("OK", new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialogInterface, int i) {
                        // Initialize string builder
                        StringBuilder stringBuilder = new StringBuilder();
                        // use for loop
                        for (int j = 0; j < langList.size(); j++) {
                            // concat array value
                            stringBuilder.append(langArray[langList.get(j)]);
                            // check condition
                            if (j != langList.size() - 1) {
                                // When j value  not equal 
                                // to lang list size - 1
                                // add comma
                                stringBuilder.append(", ");
                            }
                        }
                        // set text on textView
                        textView.setText(stringBuilder.toString());
                    }
                });

                builder.setNegativeButton("Cancel", new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialogInterface, int i) {
                        // dismiss dialog
                        dialogInterface.dismiss();
                    }
                });
                builder.setNeutralButton("Clear All", new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialogInterface, int i) {
                        // use for loop
                        for (int j = 0; j < selectedLanguage.length; j++) {
                            // remove all selection
                            selectedLanguage[j] = false;
                            // clear language list
                            langList.clear();
                            // clear text view value
                            textView.setText("");
                        }
                    }
                });
                // show dialog
                builder.show();
            }
        });
    }
}
```

**恭喜你！我们已经在 android studio 中成功实现了 MultiSelect 下拉菜单。这是我们应用程序的最终输出。**

****输出:****

**<video class="wp-video-shortcode" id="video-650587-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210723110134/Screenrecorder-2021-07-23-10-41-18-942.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210723110134/Screenrecorder-2021-07-23-10-41-18-942.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210723110134/Screenrecorder-2021-07-23-10-41-18-942.mp4)</video>**