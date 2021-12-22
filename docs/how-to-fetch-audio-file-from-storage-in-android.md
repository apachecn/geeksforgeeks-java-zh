# 如何在安卓中从存储中获取音频文件？

> 原文:[https://www . geesforgeks . org/如何从安卓存储中获取音频文件/](https://www.geeksforgeeks.org/how-to-fetch-audio-file-from-storage-in-android/)

当用户在您的应用程序中上传或发送音频文件时，需要从手机存储器中选择音频文件。所以这篇文章主要集中在从你的手机存储器中获取音频文件作为 URI。

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

我们的应用程序的 XML 布局包含一个文本视图，如果我们点击它，我们可以从我们的存储中选择一个音频文件，然后当我们选择它时，文本视图的文本变为音频选择。使用以下代码实现 XML 布局。

## 可扩展标记语言

```
<androidx.constraintlayout.widget.ConstraintLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#000022"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/select_Audio"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_gravity="center"
        android:gravity="center"
        android:text="Click to Select an Audio"
        android:textColor="#CAC6C6"
        android:textSize="16sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.5"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        tools:ignore="MissingConstraints" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

**第三步:使用 MainActivity.java 文件**

在这里，我们触发“音频”类型的意图，并将动作作为**动作 _ 获取 _ 内容。** 转到**文件，参考以下代码。下面是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
import android.content.Intent;
import android.net.Uri;
import android.os.Bundle;
import android.view.View;
import android.widget.TextView;

import androidx.annotation.Nullable;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    private final int PICK_AUDIO = 1;
    Uri AudioUri;
    TextView select_Audio;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        select_Audio = findViewById(R.id.select_Audio);

        // SETTING ONCLICK LISTENER ------ ON TEXT VIEW CLICK TO TAKE AUDIO INPUT
        select_Audio.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Intent audio = new Intent();
                audio.setType("audio/*");
                audio.setAction(Intent.ACTION_OPEN_DOCUMENT);
                startActivityForResult(Intent.createChooser(audio, "Select Audio"), PICK_AUDIO);

            }
        });
    }

    public void onActivityResult(int requestCode, int resultCode, @Nullable Intent data) {

        super.onActivityResult(requestCode, resultCode, data);

        if (requestCode == PICK_AUDIO && resultCode == RESULT_OK) {
            // Audio is Picked in format of URI
            AudioUri = data.getData();
            select_Audio.setText("Audio Selected");
        }
    }
}
```