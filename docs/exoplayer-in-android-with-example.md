# 安卓中的 ExoPlayer 示例

> 原文:[https://www . geesforgeks . org/exo player-in-Android-with-example/](https://www.geeksforgeeks.org/exoplayer-in-android-with-example/)

**explayerview**是 **YouTube、网飞**等众多应用以及众多视频流媒体平台中使用最多的 UI 组件之一。ExoPlayerView 用于安卓应用中的音频和视频流。许多谷歌应用程序使用 ExoPlayerView 来传输音频和视频。ExoPlayer 是一个媒体播放器库，它提供了一种播放音频和视频的方法，其中有很多定制。这是一个替代方案，用于在安卓系统中与 MediaPlayer 一起播放视频和音频。ExoPlayer 是一个库，是安卓系统上播放音频和视频的最佳替代来源。该库还将帮助您根据我们的要求定制您的媒体播放器。

### 使用 ExoPlayer 的优势

*   ExoPlayer 提供了对播放列表的支持，通过它，您可以剪辑或合并您的媒体。
*   在 ExoPlayer 的帮助下，可以直接从网上获取音频、视频等媒体文件，在 ExoPlayer 内部播放。
*   它提供视频和音频文件的平滑加密和流式传输。
*   ExoPlayer 为您提供了根据需求定制媒体播放器的能力。

### ExoPlayer 与 MediaPlayer

<figure class="table">

| 

外接播放器

 | 

媒体播放机

 |
| --- | --- |
| ExoPlayer 支持 HTTP 上的动态流。 | MediaPlayer 不支持通过 HTTP 进行动态支持。 |
| 它为播放的视频提供流畅的流和加密。 | MediaPlayer 不为视频提供流畅的流和加密。 |
| ExoPlayer 提供了剪辑或合并媒体文件的支持。 | MediaPlayer 不支持媒体文件的剪辑和合并。 |
| ExoPlayer 可以根据我们的要求进行定制。 | MediaPlayer 无法根据我们的要求进行定制。 |
| ExoPlayer 能够直接从服务器流式传输音频和视频文件，无需下载。 | 媒体播放器无法直接从服务器播放音频和视频文件。 |
| ExoPlayer 是在 API 16 级发布的，它在 API 16 级以下的设备上不会工作。 | Media Player 是在 API 级别 1 中发布的，它适用于所有设备。 |
| ExoPlayer 轻松处理音频和视频文件的缓冲。 | 媒体播放器无法处理音频和视频的缓冲。 |

</figure>

## 安卓系统中 ExoPlayer 的分步实现

我们将创建一个简单的视频播放器应用程序，我们将从一个网址获取视频，并在我们的 ExoPlayer 中播放该视频。请注意，我们正在使用 **JAVA** 在安卓系统中实现 ExoPlayer。

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第 2 步:向 build.gradle(模块:应用)添加依赖关系**

导航到**渐变脚本>构建.渐变(模块:应用)**，并在依赖项部分添加以下依赖项。

> exoplayer 的依赖关系
> 
> 实现' com . Google . Android . exo player:exo player:r 2 . 4 . 0 '
> 
> //获取 exoplayer 中的核心支持。
> 
> 实现' com . Google . Android . exo player:exo player-core:r 2 . 4 . 0 '
> 
> //用于在我们的 exoplayer 中添加 dash 支持。
> 
> 实现' com . Google . Android . exo player:exo player-dash:r 2 . 4 . 0 '
> 
> //用于在 exoplayer 中添加 hls 支持。
> 
> 实现' com . Google . Android . exo player:exo player-HLS:r 2 . 4 . 0 '
> 
> //在我们的 exoplayer 中实现流畅的视频流。
> 
> 实现' com . Google . Android . exo player:exo player-smooth streaming:r 2 . 4 . 0 '
> 
> //用于生成 exoplayer 的默认 ui
> 
> 实现' com . Google . Android . exo player:exo player-ui:r 2 . 4 . 0 '

添加此依赖关系后**同步**项目。

**第三步:在你的清单文件**中添加互联网权限

导航到**应用程序>清单文件夹**，并为其写下以下权限。

**第 4 步:使用 activity_main.xml**

现在我们将开始在我们的 XML 文件中实现我们的 ExoPlayerView。导航至**应用程序> res >布局> activity_main.xml** 。在该文件中添加以下代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--Widget for exoplayer view-->
    <com.google.android.exoplayer2.ui.SimpleExoPlayerView
        android:id="@+id/idExoPlayerVIew"
        android:layout_width="match_parent"
        android:layout_height="500dp" />

</RelativeLayout>
```

**步骤 5:使用 MainActivity.java 文件**

导航至**应用程序> java >您的应用程序包名称>MainActivity.java**文件。在该文件中添加以下代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.net.Uri;
import android.os.Bundle;
import android.util.Log;

import androidx.appcompat.app.AppCompatActivity;

import com.google.android.exoplayer2.ExoPlayerFactory;
import com.google.android.exoplayer2.SimpleExoPlayer;
import com.google.android.exoplayer2.extractor.DefaultExtractorsFactory;
import com.google.android.exoplayer2.extractor.ExtractorsFactory;
import com.google.android.exoplayer2.source.ExtractorMediaSource;
import com.google.android.exoplayer2.source.MediaSource;
import com.google.android.exoplayer2.trackselection.AdaptiveTrackSelection;
import com.google.android.exoplayer2.trackselection.DefaultTrackSelector;
import com.google.android.exoplayer2.trackselection.TrackSelector;
import com.google.android.exoplayer2.ui.SimpleExoPlayerView;
import com.google.android.exoplayer2.upstream.BandwidthMeter;
import com.google.android.exoplayer2.upstream.DefaultBandwidthMeter;
import com.google.android.exoplayer2.upstream.DefaultHttpDataSourceFactory;

public class MainActivity extends AppCompatActivity {

    // creating a variable for exoplayerview.
    SimpleExoPlayerView exoPlayerView;

    // creating a variable for exoplayer
    SimpleExoPlayer exoPlayer;

    // url of video which we are loading.
    String videoURL = "https://media.geeksforgeeks.org/wp-content/uploads/20201217163353/Screenrecorder-2020-12-17-16-32-03-350.mp4";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        exoPlayerView = findViewById(R.id.idExoPlayerVIew);
        try {

            // bandwisthmeter is used for 
            // getting default bandwidth
            BandwidthMeter bandwidthMeter = new DefaultBandwidthMeter();

            // track selector is used to navigate between 
            // video using a default seekbar.
            TrackSelector trackSelector = new DefaultTrackSelector(new AdaptiveTrackSelection.Factory(bandwidthMeter));

            // we are adding our track selector to exoplayer.
            exoPlayer = ExoPlayerFactory.newSimpleInstance(this, trackSelector);

            // we are parsing a video url
            // and parsing its video uri.
            Uri videouri = Uri.parse(videoURL);

            // we are creating a variable for datasource factory
            // and setting its user agent as 'exoplayer_view'
            DefaultHttpDataSourceFactory dataSourceFactory = new DefaultHttpDataSourceFactory("exoplayer_video");

            // we are creating a variable for extractor factory
            // and setting it to default extractor factory.
            ExtractorsFactory extractorsFactory = new DefaultExtractorsFactory();

            // we are creating a media source with above variables 
            // and passing our event handler as null,
            MediaSource mediaSource = new ExtractorMediaSource(videouri, dataSourceFactory, extractorsFactory, null, null);

            // inside our exoplayer view 
            // we are setting our player
            exoPlayerView.setPlayer(exoPlayer);

            // we are preparing our exoplayer
            // with media source.
            exoPlayer.prepare(mediaSource);

            // we are setting our exoplayer
            // when it is ready.
            exoPlayer.setPlayWhenReady(true);

        } catch (Exception e) {
            // below line is used for 
            // handling our errors.
            Log.e("TAG", "Error : " + e.toString());
        }
    }
}
```

> **注:**我们在这个项目中使用了[这个](https://media.geeksforgeeks.org/wp-content/uploads/20201217163353/Screenrecorder-2020-12-17-16-32-03-350.mp4)视频。

### 输出:

<video class="wp-video-shortcode" id="video-532569-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201217192146/Screenrecorder-2020-12-17-19-17-36-828.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201217192146/Screenrecorder-2020-12-17-19-17-36-828.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201217192146/Screenrecorder-2020-12-17-19-17-36-828.mp4)</video>

**查看项目:**[https://github . com/ChaitanyaMunje/qrcode generator/tree/exo player](https://github.com/ChaitanyaMunje/QRCodeGenerator/tree/ExoPlayer)