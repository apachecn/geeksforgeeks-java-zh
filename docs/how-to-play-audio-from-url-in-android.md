# 如何在安卓中从 URL 播放音频？

> 原文:[https://www . geesforgeks . org/how-play-audio-from-URL-in-Android/](https://www.geeksforgeeks.org/how-to-play-audio-from-url-in-android/)

许多应用程序需要在应用程序中添加音频功能，并且有太多的音频文件需要我们在应用程序中播放。如果我们在应用程序中存储这么多音频文件，那么它会增加应用程序的大小，并且由于应用程序的巨大大小，这可能会减少用户群。因此，解决这个问题的更好方法是将音频文件存储在数据库中，并从它们唯一的网址访问它们。在本文中，我们将看一下在 Android 中从 URL 播放音频文件。

### 我们将在这个应用程序中构建什么？

我们将建立一个简单的应用程序，其中我们将显示两个按钮播放和暂停我们的音频。我们将从网址加载音频。下面是视频，我们将在其中看到我们将在本文中构建的内容。现在让我们转向实现。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-544506-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210113122113/Screenrecorder-2021-01-13-12-19-24-250.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210113122113/Screenrecorder-2021-01-13-12-19-24-250.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210113122113/Screenrecorder-2021-01-13-12-19-24-250.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 activity_main.xml 文件**

转到 **activity_main.xml** 文件，参考以下代码。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <!--Button for playing audio-->
    <Button
        android:id="@+id/idBtnPlay"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:text="Play Audio file"
        android:textAllCaps="false" />

    <!--Button for pausing the audio-->
    <Button
        android:id="@+id/idBtnPause"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_below="@id/idBtnPlay"
        android:layout_centerInParent="true"
        android:text="Pause Audio"
        android:textAllCaps="false" />

</RelativeLayout>
```

**第三步:向 AndroidManifest.xml 文件**添加权限

当我们在安卓中播放来自网址的音频时。所以我们必须添加互联网权限来加载网址。将以下权限添加到 **AndroidManifest.xml** 文件中。

## 可扩展标记语言

```java
<!-- Permissions of internet -->
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

**步骤 4:使用 MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.media.AudioManager;
import android.media.MediaPlayer;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

import java.io.IOException;

public class MainActivity extends AppCompatActivity {

    // creating a variable for 
    // button and media player
    Button playBtn, pauseBtn;
    MediaPlayer mediaPlayer;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initializing our buttons
        playBtn = findViewById(R.id.idBtnPlay);
        pauseBtn = findViewById(R.id.idBtnPause);

        // setting on click listener for our play and pause buttons.
        playBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // calling method to play audio.
                playAudio();
            }
        });

        pauseBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // checking the media player 
                // if the audio is playing or not.
                if (mediaPlayer.isPlaying()) {
                    // pausing the media player if media player 
                    // is playing we are calling below line to
                    // stop our media player.
                    mediaPlayer.stop();
                    mediaPlayer.reset();
                    mediaPlayer.release();

                    // below line is to display a message 
                    // when media player is paused.
                    Toast.makeText(MainActivity.this, "Audio has been paused", Toast.LENGTH_SHORT).show();
                } else {
                    // this method is called when media 
                    // player is not playing.
                    Toast.makeText(MainActivity.this, "Audio has not played", Toast.LENGTH_SHORT).show();
                }
            }
        });
    }

    private void playAudio() {

        String audioUrl = "https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3";

        // initializing media player
        mediaPlayer = new MediaPlayer();

        // below line is use to set the audio 
        // stream type for our media player.
        mediaPlayer.setAudioStreamType(AudioManager.STREAM_MUSIC);

        // below line is use to set our 
        // url to our media player.
        try {
            mediaPlayer.setDataSource(audioUrl);
            // below line is use to prepare
            // and start our media player.
            mediaPlayer.prepare();
            mediaPlayer.start();

        } catch (IOException e) {
            e.printStackTrace();
        }
        // below line is use to display a toast message.
        Toast.makeText(this, "Audio started playing..", Toast.LENGTH_SHORT).show();
    }
}
```

添加代码后，现在运行您的应用程序并查看应用程序的输出。

### **输出:**

> **注意:**点击播放按钮后等待一段时间，因为我们正在从网址加载音频文件。所以加载我们的音频文件需要一点时间。

<video class="wp-video-shortcode" id="video-544506-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210113122113/Screenrecorder-2021-01-13-12-19-24-250.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210113122113/Screenrecorder-2021-01-13-12-19-24-250.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210113122113/Screenrecorder-2021-01-13-12-19-24-250.mp4)</video>