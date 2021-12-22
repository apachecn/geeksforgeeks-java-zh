# 安卓中的 MediaMetadataRetriever 类，示例

> 原文:[https://www . geeksforgeeks . org/mediametadata retriever-带示例的安卓类/](https://www.geeksforgeeks.org/mediametadataretriever-class-in-android-with-examples/)

一个 **MediaMetadataRetriever** 类提供了从输入媒体文件中检索帧和元数据的统一接口。它位于**安卓媒体包**下。例如:**检索歌曲名称、艺术家姓名、视频的宽度或高度、视频格式/mime 类型、媒体持续时间、媒体修改日期等**。MediaMetadataRetriever 类提供了大量的常量/键。这些常量用于检索媒体信息。尽管从名称上看，许多常量所做的工作是显而易见的，但这里还是对 MediaMetadataRetriever 类中的每个常量做了一个小小的描述。

### **媒体元数据检索器**类的重要常数

<figure class="table">

| 

常量类型

 | 

常数名称

 | 

描述

 |
| --- | --- | --- |
| （同 Internationalorganizations）国际组织 | 元数据 _ 密钥 _ 相册 | 用于检索数据源相册标题信息的元数据键。 |
| （同 Internationalorganizations）国际组织 | METADATA_KEY_ALBUMARTIST | 用于检索与数据源关联的表演者或艺术家信息的元数据关键字。 |
| （同 Internationalorganizations）国际组织 | 元数据 _ 关键 _ 艺术家 | 用于检索数据源艺术家信息的元数据键。 |
| （同 Internationalorganizations）国际组织 | 元数据 _ 密钥 _ 作者 | 用于检索数据源作者信息的元数据键。 |
| （同 Internationalorganizations）国际组织 | 元数据 _ 密钥 _ 光盘 _ 曲目 _ 编号 | 元数据键，用于检索描述音频数据源在其原始录音中的顺序的数字字符串。 |
| （同 Internationalorganizations）国际组织 | METADATA _ KEY _ COMPILATION | 检索音乐专辑编辑状态的元数据键。 |
| （同 Internationalorganizations）国际组织 | METADATA_KEY_COMPOSER | 用于检索数据源的编写器信息的元数据键。 |
| （同 Internationalorganizations）国际组织 | 元数据 _ 关键 _ 日期 | 用于检索数据源创建或修改日期的元数据关键字。 |
| （同 Internationalorganizations）国际组织 | 元数据 _ 密钥 _ 光盘 _ 号码 | 用于检索描述音频数据源来自集合的哪一部分的数字字符串的元数据键。 |
| （同 Internationalorganizations）国际组织 | 元数据 _ 关键 _ 持续时间 | 用于检索数据源回放持续时间的元数据键。 |

</figure>

<figure class="table">

| 

常量类型

 | 

常数名称

 | 

描述

 |
| --- | --- | --- |
| （同 Internationalorganizations）国际组织 | 元数据 _ 关键 _ 流派 | 用于检索数据源的内容类型或流派的元数据键。 |
| （同 Internationalorganizations）国际组织 | 元数据 _ 密钥 _MIMETYPE | 用于检索数据源 mime 类型的元数据键。 |
| （同 Internationalorganizations）国际组织 | 元数据 _ 关键 _ 数字 _ 轨迹 | 元数据键，用于检索数据源(如 mp4 或 3gpp 文件)中的音轨数量，如音频、视频、文本。 |
| （同 Internationalorganizations）国际组织 | 元数据 _ 关键 _ 标题 | 检索数据源标题的元数据键。 |
| （同 Internationalorganizations）国际组织 | METADATA_KEY_WRITER | 用于检索数据源的作者(如作词人)信息的元数据键。 |
| （同 Internationalorganizations）国际组织 | 元数据 _ 关键 _ 年份 | 用于检索数据源创建或修改年份的元数据关键字。 |
| （同 Internationalorganizations）国际组织 | 选项 _ 最近 | 此选项与 getFrameAtTime(long，int)一起使用，以检索与最接近或在给定时间的数据源相关联的帧(不一定是关键帧)。 |
| （同 Internationalorganizations）国际组织 | 选项最接近同步 | 此选项与 getFrameAtTime(long，int)一起使用，以检索与最接近(在时间上)或给定时间的数据源相关联的同步(或关键)帧。 |
| （同 Internationalorganizations）国际组织 | 选项 _ 下一个 _ 同步 | 此选项与 getFrameAtTime(long，int)一起使用，以检索与数据源相关联的同步(或关键)帧，该数据源位于给定时间之后或此时。 |
| （同 Internationalorganizations）国际组织 | 选项 _ 先前 _ 同步 | 此选项与 getFrameAtTime(long，int)一起使用，以检索与位于给定时间之前或之时的数据源相关联的同步(或关键)帧。 |

</figure>

### 媒体元数据检索器类中可用的方法

<figure class="table">

| 

方法类型

 | 

方法

 |
| --- | --- |
| 线 | extractMetadata(int keyCode)在 setDataSource()之后调用此方法。 |
| 字节[] | getEmbeddedPicture()

在 setDataSource()之后调用此方法。 |
| 位图 | getFrameAtTime（long timeUs， int option）在 setDataSource()之后调用此方法。 |
| 位图 | getFrameAtTime（longtimeUs）在 setDataSource()之后调用此方法。 |
| 位图 | getFrameAtTime()在 setDataSource()之后调用此方法。 |
| 空的 | 发布()当一个人处理完对象时调用它。此方法释放内部分配的内存。 |
| 空的 | 设置数据源(文件描述符 fd，长偏移量，长长度)设置要使用的数据源(文件描述符)。 |
| 空的 | 设置数据源(字符串路径)设置要使用的数据源(文件路径名)。 |
| 空的 | setDataSource（FileDescriptor fd）设置要使用的数据源(文件描述符)。 |
| 空的 | 设置数据源(上下文上下文，Uri uri)将数据源设置为内容 Uri。 |
| 空的 | 关闭()关闭此资源，放弃所有底层资源。

此方法在由管理的对象上自动调用资源尝试语句。 |

</figure>

### 例子

**1。获取 mp3 时长**

下面是 Java 中获取 mp3 时长的示例代码片段。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// load data file
// filePath is of type String which holds the path of file
MediaMetadataRetriever metaRetriever = new MediaMetadataRetriever();
metaRetriever.setDataSource(filePath);

// get mp3 info
String duration = metaRetriever.extractMetadata(MediaMetadataRetriever.METADATA_KEY_DURATION);
long dur = Long.parseLong(duration);

// convert duration to minute:seconds
String seconds = String.valueOf((dur % 60000) / 1000);
String minutes = String.valueOf(dur / 60000);
String out = minutes + ":" + seconds;
if (seconds.length() == 1) {
    txtTime.setText("0" + minutes + ":0" + seconds);
}
else {
    txtTime.setText("0" + minutes + ":" + seconds);
}

// close object
metaRetriever.release();
```

**2。检测视频的方向**

下面是一个视频样本

<video class="wp-video-shortcode" id="video-510618-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201029232352/Screenrecorder-2020-10-29-22-42-58-217.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201029232352/Screenrecorder-2020-10-29-22-42-58-217.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201029232352/Screenrecorder-2020-10-29-22-42-58-217.mp4)</video>

下面是 Java 中检测视频方向的示例代码片段

## Java 语言(一种计算机语言，尤用于创建网站)

```java
MediaMetadataRetriever m = new MediaMetadataRetriever();

// load data file
m.setDataSource(path);

// getting the bitmap of a frame from video
Bitmap thumbnail = m.getFrameAtTime();

if (Build.VERSION.SDK_INT >= 17) {
    String s = m.extractMetadata(MediaMetadataRetriever.METADATA_KEY_VIDEO_ROTATION);
}

// Another way of determining whether the video is Landscape or portrait
MediaMetadataRetriever retriever = new MediaMetadataRetriever();
retriever.setDataSource(inputPath);
video_width = Integer.valueOf(retriever.extractMetadata(MediaMetadataRetriever.METADATA_KEY_VIDEO_WIDTH));
video_height = Integer.valueOf(retriever.extractMetadata(MediaMetadataRetriever.METADATA_KEY_VIDEO_HEIGHT));

// close object
retriever.release();

// If the width is bigger than the height then it means that
// the video was taken in landscape mode and vice versa.
if ((video_width > video_height)) {
    // landscape
}
else {
    // portrait
}
```

**3。在音乐应用程序中设置专辑封面和专辑标题**

下面是一个示例图像

![](img/cd142838b6691f263499569bda33e25d.png)

以下是在音乐应用程序中设置专辑封面和专辑标题的 Java 示例代码片段。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
MediaMetadataRetriever retriever = new MediaMetadataRetriever();
retriever.setDataSource(filePath);

// getting the embedded picture from media
byte[] art = retriever.getEmbeddedPicture();

if (art != null) {
    // Convert the byte array to a bitmap
    imgAlbum.setImageBitmap(BitmapFactory.decodeByteArray(art, 0, art.length));
}
else {
    imgAlbum.setImageResource(R.drawable.no_image);
}
// close object
retriever.release();
```

**4。做一个像抖音一样的作物视频活动**

下面是一个视频样本

<video class="wp-video-shortcode" id="video-510618-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201107121326/Video.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20201107121326/Video.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201107121326/Video.mp4)</video>

下面是用 Java 编写的类似抖音的 CropVideo 活动的示例代码片段。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
try {
    MediaMetadataRetriever mediaMetadataRetriever = new MediaMetadataRetriever();
    mediaMetadataRetriever.setDataSource(context, videoUri);

    // Retrieve media data use microsecond
    long interval = (endPosition - startPosition) / (totalThumbsCount - 1);
    for (long i = 0; i < totalThumbsCount; ++i) {
        long frameTime = startPosition + interval * i;
        Bitmap bitmap = mediaMetadataRetriever.getFrameAtTime(frameTime * 1000, MediaMetadataRetriever.OPTION_CLOSEST_SYNC);
        if (bitmap == null)
            continue;
        try {
            bitmap = Bitmap.createScaledBitmap(bitmap, THUMB_WIDTH, THUMB_HEIGHT, false);
        }
        catch (final Throwable t) {
            t.printStackTrace();
        }
        // add bitmaps to the recyclerview here…
    }
    mediaMetadataRetriever.release();
}
catch (final Throwable e) {
    Thread.getDefaultUncaughtExceptionHandler().uncaughtException(Thread.currentThread(), e);
}
```

> **注:**
> 
> 1.  始终检查非法文件路径。
> 2.  处理空位图条件。可能会出现介质没有返回有效位图的情况。
> 3.  帧索引必须是有效帧的索引。可以通过 METADATA_KEY_VIDEO_FRAME_COUNT 键查询可检索的总帧数。
> 4.  在给定时间位置检索帧时，不能保证数据源在该位置有帧。当这种情况发生时，附近的帧将被返回。如果时间为负，时间位置和选项将被忽略，并且可以返回实现认为有代表性的任何帧。
> 5.  setDataSource()，在调用此类中的其他方法之前调用此方法。这种方法可能很耗时。

**参考链接:**[https://developer . Android . com/Reference/Android/media/mediametadata retriever](https://developer.android.com/reference/android/media/MediaMetadataRetriever)