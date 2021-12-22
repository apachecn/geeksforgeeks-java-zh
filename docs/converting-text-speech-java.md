# 在 Java 中将文本转换为语音

> 原文:[https://www.geeksforgeeks.org/converting-text-speech-java/](https://www.geeksforgeeks.org/converting-text-speech-java/)

**Java 语音 API:**Java 语音 API 允许 Java 应用程序将语音技术融入其用户界面。它定义了一个跨平台的应用编程接口来支持命令和控制识别器、听写系统和语音合成器。

Java 语音支持语音合成，这意味着机器在书面输入的基础上生成口语的过程。

重要的是要记住，Java 语音只是一个规范，即不包括任何实现。因此，第三方提供了实现。javax .语音包定义了识别器、合成器和其他语音引擎的通用功能。软件包 **javax.speech.synthesis** 扩展了合成器的基本功能。

我们将理解 java API 将文本转换为语音需要什么

1.  **引擎:**引擎界面在语音包中提供。“语音引擎”是设计用于处理语音输入或语音输出的系统的通称。

    ```java
    import javax.speech.Engine;
    ```

2.  **Central:** Central 提供定位、选择和创建语音识别器和语音合成器的功能。

    ```java
    import javax.speech.Central;
    ```

3.  **合成器模式描述符:**合成器模式描述符用特定于语音合成器的属性扩展了引擎模式描述符。

    ```java
    import javax.speech.synthesis.SynthesizerModeDesc;
    ```

4.  **合成器:**合成器界面提供语音合成功能的主要访问。合成器模式描述增加了两个属性:合成器声音提供的声音列表当合成器启动时要加载的声音。

    ```java
    import javax.speech.synthesis.Synthesizer;
    ```

下面是一个 Java 语音合成的开源实现，名为 [FreeTTS](https://freetts.sourceforge.io/docs/index.php) 以步骤的形式:

*   从[这里](http://sourceforge.net/project/showfiles.php?group_id=42080)下载 zip 文件夹形式的 FreeTTS
*   提取 zip 文件并转到

    ```java
    freetts-1.2.2-bin/freetts-1.2/lib/jsapi.exe
    ```

*   打开**jsapi.exe**文件并安装。
*   这将创建一个名为 **jsapi.jar** 的 jar 文件。这是包含要包含在项目中的 FreeTTS 库的 JAR 库。
*   在集成开发环境中创建一个新的 Java 项目。
*   将这个 [jsapi.jar 文件](https://www.geeksforgeeks.org/jar-files-java/)包含到您的项目中。
*   现在将下面的代码复制到您的项目中
*   执行项目以获得低于预期的输出。

以下是上述项目的代码:

```java
// Java code to convert text to speech

import java.util.Locale;
import javax.speech.Central;
import javax.speech.synthesis.Synthesizer;
import javax.speech.synthesis.SynthesizerModeDesc;

public class TextSpeech {

    public static void main(String[] args)
    {

        try {
            // Set property as Kevin Dictionary
            System.setProperty(
                "freetts.voices",
                "com.sun.speech.freetts.en.us"
                    + ".cmu_us_kal.KevinVoiceDirectory");

            // Register Engine
            Central.registerEngineCentral(
                "com.sun.speech.freetts"
                + ".jsapi.FreeTTSEngineCentral");

            // Create a Synthesizer
            Synthesizer synthesizer
                = Central.createSynthesizer(
                    new SynthesizerModeDesc(Locale.US));

            // Allocate synthesizer
            synthesizer.allocate();

            // Resume Synthesizer
            synthesizer.resume();

            // Speaks the given text
            // until the queue is empty.
            synthesizer.speakPlainText(
                "GeeksforGeeks", null);
            synthesizer.waitEngineState(
                Synthesizer.QUEUE_EMPTY);

            // Deallocate the Synthesizer.
            synthesizer.deallocate();
        }

        catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**输出:**

**参考文献:**

*   [https://docs . Oracle . com/CD/e 17802 _ 01/products/Java-media/speech/FOrdeveloper/jsapi-doc/javax/speech/package-summary . html](https://docs.oracle.com/cd/E17802_01/products/products/java-media/speech/forDevelopers/jsapi-doc/javax/speech/package-summary.html)
*   [https://www . javatpoint . com/q/5931/Java-用于将音频转换为文本和视频转换为音频的代码](https://www.javatpoint.com/q/5931/java-code-for-converting-audio-to-text-and-video-to-audio)
*   [http://www.oracle.com/technetwork/java/jsapifaq-135248.html](http://www.oracle.com/technetwork/java/jsapifaq-135248.html)

**相关文章:**[Python 中的文字转语音](https://www.geeksforgeeks.org/convert-text-speech-python/)

本文由**阿卡什·莎兰**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。