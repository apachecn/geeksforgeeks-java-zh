# 将 OnTouchListener 添加到 ImageView，在 Android 中执行语音到文本的转换

> 原文:[https://www . geesforgeks . org/add-ontouchlistener-to-imageview-to-performance-voice-text-in-Android/](https://www.geeksforgeeks.org/add-ontouchlistener-to-imageview-to-perform-speech-to-text-in-android/)

**语音转文本**是一个特性，通常意味着用户说的任何话都会转换成文本。这个特性对于用户来说是一个非常常见和有用的特性。在像谷歌搜索这样实现搜索功能的地方，也可以在像谷歌键盘这样的应用程序中实现，因为它给用户带来了很好的体验。因此，在本文中，我们将使用[的 OnTouchListener 实现语音到文本的转换，并将输入文本存储在](https://www.geeksforgeeks.org/imageview-in-android-with-example/)[编辑文本](https://www.geeksforgeeks.org/edittext-widget-in-android-using-java-with-examples/)中。

### 我们将在本文中构建什么？

在本文中，我们将开发一个示例应用程序，它的主活动中有一个麦克风的图像视图和一个编辑文本，通过使用图像视图的 OnTouchListener，我们将以语音到文本的形式向编辑文本提供输入。下面给出了一个示例 GIF，以了解我们将在本文中做什么。注意，我们将使用 **Java** 语言来实现这个项目。

### 逐步实施

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

现在，转到**应用程序> res >布局> activity_main.xml** 并将下面编写的代码粘贴到 **activity_main.xml** 文件中。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <!--EditText to show the the recorded text-->
    <EditText
        android:id="@+id/edit_text"
        android:layout_width="match_parent"
        android:layout_height="52dp"
        android:layout_margin="12dp"
        android:layout_marginTop="600dp"
        android:hint="Enter here"
        android:textColor="#0F9D58" />

    <!--ImageView to use as a button-->
    <ImageView
        android:id="@+id/microphone"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="400dp"
        app:srcCompat="@drawable/microphone" />

</LinearLayout>
```

**步骤 3:使用 MainActivity.java 文件**

转到 **app > java >包名>MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.content.Intent;
import android.os.Bundle;
import android.speech.RecognitionListener;
import android.speech.RecognizerIntent;
import android.speech.SpeechRecognizer;
import android.view.MotionEvent;
import android.view.View;
import android.widget.EditText;
import androidx.appcompat.app.AppCompatActivity;
import java.util.ArrayList;
import java.util.Locale;

public class MainActivity extends AppCompatActivity {

    // declare editText
    EditText editText;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // definition of editText using method findViewById()
        editText = findViewById(R.id.edit_text);

        // initializing mSpeechRecognizer using SpeechRecognizer class
        final SpeechRecognizer mSpeechRecognizer = SpeechRecognizer.createSpeechRecognizer(this);
        final Intent mSpeechRecognizerIntent = new Intent(RecognizerIntent.ACTION_RECOGNIZE_SPEECH);

        mSpeechRecognizerIntent.putExtra(RecognizerIntent.EXTRA_LANGUAGE_MODEL, RecognizerIntent.LANGUAGE_MODEL_FREE_FORM);
        mSpeechRecognizerIntent.putExtra(RecognizerIntent.EXTRA_LANGUAGE, Locale.getDefault());

        // various methods of RecognitionListener class
        mSpeechRecognizer.setRecognitionListener(new RecognitionListener() {
            @Override
            public void onReadyForSpeech(Bundle bundle) {

            }

            @Override
            public void onBeginningOfSpeech() {

            }

            @Override
            public void onRmsChanged(float v) {

            }

            @Override
            public void onBufferReceived(byte[] bytes) {

            }

            @Override
            public void onEndOfSpeech() {

            }

            @Override
            public void onError(int i) {

            }

            @Override
            public void onResults(Bundle bundle) {

                // getting all the matches
                ArrayList<String> matches = bundle.getStringArrayList(SpeechRecognizer.RESULTS_RECOGNITION);

                // displaying the first match
                if (matches != null)
                    editText.setText(matches.get(0));
            }

            @Override
            public void onPartialResults(Bundle bundle) {

            }

            @Override
            public void onEvent(int i, Bundle bundle) {

            }
        });

        // set OnTouchListener to imageView named microphone
        findViewById(R.id.microphone).setOnTouchListener(new View.OnTouchListener() {
            @Override
            public boolean onTouch(View view, MotionEvent motionEvent) {
                switch (motionEvent.getAction()) {

                    // case MotionEvent.ACTION_UP run when user will remove
                    // his/her finger from microphone imageView
                    case MotionEvent.ACTION_UP:

                        mSpeechRecognizer.stopListening();
                        editText.setHint(" ");
                        break;

                    // case MotionEvent.ACTION_UP run when user will put his/her
                    // finger from microphone imageView
                    case MotionEvent.ACTION_DOWN:

                        mSpeechRecognizer.startListening(mSpeechRecognizerIntent);
                        editText.setText("");
                        editText.setHint("");
                        break;
                }
                return false;
            }
        });
    }
}
```

**第 4 步:使用 AndroidManifest.xml 文件**

最后，转到**应用程序>清单> AndroidManifest.xml** 文件，并在那里添加下面写的权限。

## 可扩展标记语言

```java
<uses-permission android:name="android.permission.RECORD_AUDIO" />
```

仅此而已，现在应用程序已准备好安装在设备上。下面是应用程序的输出。

**输出:**

<video class="wp-video-shortcode" id="video-581033-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210330145210/Add-OnTouchListener-to-ImageView-to-perform-Speech-to-Text-in-Android.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210330145210/Add-OnTouchListener-to-ImageView-to-perform-Speech-to-Text-in-Android.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210330145210/Add-OnTouchListener-to-ImageView-to-perform-Speech-to-Text-in-Android.mp4)</video>