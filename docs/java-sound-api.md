# Java 声音 API

> 原文:[https://www.geeksforgeeks.org/java-sound-api/](https://www.geeksforgeeks.org/java-sound-api/)

**javaSound** 是 Java 中实现和控制声音媒体的类和接口的集合。它由两个包组成。

*   ***javax . sound . sampled:***这个包提供了一个捕捉、混合数字音频的接口。
*   ***javax . sound . midi:***这个包为 MIDI(乐器数字接口)合成、排序和事件传输提供了一个接口。

**什么是 MIDI？**

我们将在这里探索更多关于 MIDI 的内容。所以 midi 就像一张有 midi 功能的乐器可以演奏的音符表，把它想象成一个 HTML 文档，把有 MIDI 功能的乐器想象成一个网页浏览器。MIDI 文件有关于歌曲应该如何播放的信息，就像吉他弹奏者的说明书一样。midi 设备知道如何读取 MIDI 文件并产生声音。

为了发出真实的声音，我们需要四样东西:

1.  乐器(播放音乐)SEQUENCER
2.  歌曲(要播放的音乐)序列
3.  轨道(保存音符)
4.  音符(实际音乐信息)MIDI 事件

JavaSound API 涵盖了所有这些内容。

> SEQUENCER ⇒ SEQUENCE ⇒ TRACK ⇒ MIDI 事件

**程序:**

**第一步:**获取**序列器**并将其打开

```
// Make a sequencer named player and open it
Sequencer player = MIDISystem.getSequencer();
player.open();
```

**第二步:**新建**序列**

```
// Make a new sequence 
Sequence seq = new Sequence(Sequence.PPQ, 4);
```

**第三步:**从序列中获取新的**轨迹**

```
// Creating new Track
Track t = seq.createTrack();
```

**第 4 步:**用 **MIDIEVENTS** 填充轨道

```
// Filling the Track with MidiEvent and
// giving the Sequence to the Sequencer

t.add(myMidiEvent1);
player.setSequence(seq);

// Play it using start
player.start();
```

**实施:**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate JAva Sounf API

// Importing classes from
// javax.sound package
import javax.sound.midi.*;

// Main class
// MiniMusicApp
public class GFG {

    // Method 1
    // Main driver method
    public static void main(String[] args)
    {
        // Creating object of class inside main()
        GFG minimusic = new GFG();

        // Calling method 2 to play the sound
        minimusic.play();

        // Display message on the console for
        // successful execution of program
        System.out.print(
            "Successfully compiled and executed");
    }

    // Method 2
    // To play the sound
    public void play()
    {

        // Try block to check for exceptions
        try {
            // Getting a sequencer and open it
            Sequencer player = MidiSystem.getSequencer();
            player.open();

            // Making 1a new Sequence
            Sequence seq = new Sequence(Sequence.PPQ, 4);

            // Creating a new track
            Track track = seq.createTrack();

            // Making a Message
            ShortMessage a = new ShortMessage();

            // Put the Instruction in the Message
            a.setMessage(144, 1, 44, 100);

            // Make a new MidiEvent
            MidiEvent noteOn = new MidiEvent(a, 1);

            // Add MidiEvent to the Track
            track.add(noteOn);

            ShortMessage b = new ShortMessage();
            b.setMessage(128, 1, 44, 100);
            MidiEvent noteOff = new MidiEvent(b, 16);
            track.add(noteOff);

            // Giving sequence to Sequencer
            player.setSequence(seq);

            // Start the Sequencer using start() method
            player.start();
        }

        // Catch block to handle exceptions
        catch (Exception ex) {
            // Display the exception on console
            // along with line number
            ex.printStackTrace();
        }
    }
}
```

**输出:**

```
Successfully compiled and executed
```