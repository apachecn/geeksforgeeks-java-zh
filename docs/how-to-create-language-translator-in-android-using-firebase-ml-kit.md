# 如何使用 Firebase ML 工具包在安卓系统中创建语言翻译器？

> 原文:[https://www . geesforgeks . org/如何使用 firebase-ml-kit 创建安卓语言翻译器/](https://www.geeksforgeeks.org/how-to-create-language-translator-in-android-using-firebase-ml-kit/)

在前一篇文章中，我们已经看到了在安卓中使用[语言检测器使用 Firebase ML 工具包](https://www.geeksforgeeks.org/how-to-create-language-detector-in-android-using-firebase-ml-kit/)。在本文中，我们将看一下在安卓系统中使用 Firebase ML 工具包在安卓系统中实现**语言翻译器**。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将显示一个[编辑文本](https://www.geeksforgeeks.org/edittext-widget-in-android-using-java-with-examples/)字段，我们将向该**文本字段**添加任何输入。与此同时，我们将显示一个[按钮](https://www.geeksforgeeks.org/button-in-kotlin/)，将该文本翻译成德语。点击该按钮后，我们的文本将被翻译成德语，我们可以在文本视图中看到。下面给出一个视频示例，来了解一下 我们在本文中要做什么 。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-560415-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210211162847/Screenrecorder-2021-02-11-16-18-41-56.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210211162847/Screenrecorder-2021-02-11-16-18-41-56.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210211162847/Screenrecorder-2021-02-11-16-18-41-56.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:将你的应用连接到 Firebase**

在 Android Studio 中创建新项目后，将您的应用程序连接到 Firebase。用于将您的应用程序连接到 firebase。导航到顶部栏上的工具。之后点击 Firebase。右侧将打开一个新窗口。在该窗口中，单击 Firebase ML，然后单击在安卓系统中使用 Firebase ML 工具包。你可以在下面的截图中看到这个选项。

![](img/8bb9fea32a255b2eb794f1edcbd4658b.png)

点击此选项后，您将看到下面的屏幕。在此屏幕上，点击**连接到 Firebase** 选项，将您的应用程序连接到 Firebase。点击连接选项，将你的应用程序连接到 Firebase，并将下面的依赖项添加到你的 [build.gradle](https://www.geeksforgeeks.org/android-build-gradle/) 文件中。

**第三步:添加语言翻译的依赖项，建立. gradle 文件**

导航至 **Gradle 脚本> build.gradle(模块:app)** 并在依赖项部分添加以下依赖项。

> firebase 核心的依赖关系。
> 
> 实现' com . Google . firebase:firebase-core:15 . 0 . 2 '
> 
> //下面两个依赖项用于语言检测
> 
> 实现' com . Google . firebase:firebase-ml-自然语言:22.0.0 '
> 
> 实现' com . Google . firebase:firebase-ml-自然语言-翻译-模型:20.0.8 '

**第四步:在你的安卓应用中添加访问互联网的权限**

导航到**应用程序> AndroidManifest.xml** 文件，并在其中添加以下代码。代码中添加了注释，以便更详细地了解。

## 可扩展标记语言

```
<!--permission for internet-->
<uses-permission android:name="android.permission.INTERNET"/>
```

**第 5 步:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--edit text to enter your input-->
    <EditText
        android:id="@+id/idEdtLanguage"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="50dp"
        android:hint="Enter your name to translate"
        android:padding="4dp"
        android:textColor="@color/black"
        android:textSize="20sp" />

    <!--button to translate language of the input text-->
    <Button
        android:id="@+id/idBtnTranslateLanguage"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/idTVTranslatedLanguage"
        android:layout_centerInParent="true"
        android:text="Translate language" />

    <!--text view to display the translated text-->
    <TextView
        android:id="@+id/idTVTranslatedLanguage"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idEdtLanguage"
        android:layout_centerHorizontal="true"
        android:layout_margin="20dp"
        android:gravity="center_horizontal"
        android:text="Translated language"
        android:textAlignment="center"
        android:textSize="20sp" />

</RelativeLayout>
```

**第 6 步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;

import androidx.annotation.NonNull;
import androidx.appcompat.app.AppCompatActivity;

import com.google.android.gms.tasks.OnFailureListener;
import com.google.android.gms.tasks.OnSuccessListener;
import com.google.firebase.ml.common.modeldownload.FirebaseModelDownloadConditions;
import com.google.firebase.ml.naturallanguage.FirebaseNaturalLanguage;
import com.google.firebase.ml.naturallanguage.translate.FirebaseTranslateLanguage;
import com.google.firebase.ml.naturallanguage.translate.FirebaseTranslator;
import com.google.firebase.ml.naturallanguage.translate.FirebaseTranslatorOptions;

public class MainActivity extends AppCompatActivity {

    // creating variables for our image view, 
    // text view and two buttons.
    private EditText edtLanguage;
    private TextView translateLanguageTV;
    private Button translateLanguageBtn;

    // create a variable for our 
    // firebase language translator.
    FirebaseTranslator englishGermanTranslator;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // on below line we are creating our firebase translate option.
        FirebaseTranslatorOptions options =
                new FirebaseTranslatorOptions.Builder()
                        // below line we are specifying our source language.
                        .setSourceLanguage(FirebaseTranslateLanguage.EN)
                        // in below line we are displaying our target language.
                        .setTargetLanguage(FirebaseTranslateLanguage.DE)
                        // after that we are building our options.
                        .build();
        // below line is to get instance
        // for firebase natural language.
        englishGermanTranslator = FirebaseNaturalLanguage.getInstance().getTranslator(options);

        // on below line we are initializing our variables.
        edtLanguage = findViewById(R.id.idEdtLanguage);
        translateLanguageTV = findViewById(R.id.idTVTranslatedLanguage);
        translateLanguageBtn = findViewById(R.id.idBtnTranslateLanguage);

        // adding on click listener for button
        translateLanguageBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // calling method to download language 
                // modal to which we have to translate.
                String string = edtLanguage.getText().toString();
                downloadModal(string);
            }
        });
    }

    private void downloadModal(String input) {
        // below line is use to download the modal which
        // we will require to translate in german language
        FirebaseModelDownloadConditions conditions = new FirebaseModelDownloadConditions.Builder().requireWifi().build();

        // below line is use to download our modal.
        englishGermanTranslator.downloadModelIfNeeded(conditions).addOnSuccessListener(new OnSuccessListener<Void>() {
            @Override
            public void onSuccess(Void aVoid) {

                // this method is called when modal is downloaded successfully.
                Toast.makeText(MainActivity.this, "Please wait language modal is being downloaded.", Toast.LENGTH_SHORT).show();

                // calling method to translate our entered text.
                translateLanguage(input);

            }
        }).addOnFailureListener(new OnFailureListener() {
            @Override
            public void onFailure(@NonNull Exception e) {
                Toast.makeText(MainActivity.this, "Fail to download modal", Toast.LENGTH_SHORT).show();
            }
        });
    }

    private void translateLanguage(String input) {
        englishGermanTranslator.translate(input).addOnSuccessListener(new OnSuccessListener<String>() {
            @Override
            public void onSuccess(String s) {
                translateLanguageTV.setText(s);
            }
        }).addOnFailureListener(new OnFailureListener() {
            @Override
            public void onFailure(@NonNull Exception e) {
                Toast.makeText(MainActivity.this, "Fail to translate", Toast.LENGTH_SHORT).show();
            }
        });
    }
}
```

现在运行您的应用程序，并查看应用程序的输出。

### **输出:**

> **注**:第一次使用 app 时。这需要一些时间，因为它会在后台下载模态。我们没有在这个应用程序中添加多种语言支持，因为对于每种语言，我们都必须下载语言转换模型，这样会使应用程序变得更重，并且语言翻译会花费很多时间。

<video class="wp-video-shortcode" id="video-560415-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210211162847/Screenrecorder-2021-02-11-16-18-41-56.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210211162847/Screenrecorder-2021-02-11-16-18-41-56.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210211162847/Screenrecorder-2021-02-11-16-18-41-56.mp4)</video>

**在下方链接查看项目:**[https://github.com/ChinmayMunje/Firebase-ML-Kit](https://github.com/ChinmayMunje/Firebase-ML-Kit)