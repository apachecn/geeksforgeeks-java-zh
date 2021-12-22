# Java 小程序|数字秒表

> 原文:[https://www . geesforgeks . org/Java-applet-digital-秒表/](https://www.geeksforgeeks.org/java-applet-digital-stopwatch/)

本文将提供一个用 Java Applet、AWT 和 Thread 创建一种秒表的实例。

我们将使用所有这些库来制作秒表的工作模型。图形用户界面应具有 3 个交互按钮，即开始(启动时间)、复位(将时间复位为默认值)和停止(停止计时器)。

借助 Java 中的 actionListener，我们可以了解在什么时候按下哪个按钮。

1.  当按下启动按钮时，我们启动计时器。当未按下复位或停止按钮时，我们将保持计时器运行，即我们将每 1 毫秒更改一次计时器的值(hh:mm:ss:ms)，并更新屏幕。
2.  当按下复位按钮时，我们将停止计时器，并将其设置为默认值(00:00:00:000)。
3.  当按下停止按钮时，我们用它的值停止计时器。

**下面是数字秒表**的实现

```
// Java program to illustrate
// digital stop watch
// using Applets

// importing required packages
import java.applet.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class GeeksforGeeks extends Applet implements Runnable, ActionListener {

// Panel to keep all the buttons and labels
    Panel p;
    Label display;

    // Button
    Button start, stop, reset;

    // Time
    int hour, minute, second, millisecond;

    // string to be displayed on the label
    String disp;

    // State of stopwatch on/off
    boolean on;

    // initialization
    public void init()
    {
        // initially off
        on = false;

        p = new Panel();
        // Setting layout of the panel
        p.setLayout(new GridLayout(4, 1, 6, 10));

        // initial time 00 : 00 : 00 : 000
        hour = minute = second = millisecond = 0;

        // Label
        display = new Label();
        disp = "00 : 00 : 00 : 000";
        display.setText(disp);
        p.add(display);

        // Start button
        start = new Button("Start");
        start.addActionListener((ActionListener) this);
        p.add(start);

        // Reset button
        reset = new Button("Reset");
        reset.addActionListener((ActionListener) this);
        p.add(reset);

        // Stop button
        stop = new Button("Stop");
        stop.addActionListener((ActionListener) this);
        p.add(stop);

        add(p);

        // starting thread
        new Thread(this, "StopWatch").start();
    }

    // Reset Function
    // reset to default value
    public void reset()
    {
        try {
            Thread.sleep(1);
        }
        catch (Exception e) {
            System.out.println(e);
        }
        hour = minute = second = millisecond = 0;
    }

    // update function
    // update the timer
    public void update()
    {
        millisecond++;
        if (millisecond == 1000) {
            millisecond = 0;
            second++;
            if (second == 60) {
                second = 0;
                minute++;
                if (minute == 60) {
                    minute = 0;
                    hour++;
                }
            }
        }
    }

    // changing label
    public void changeLabel()
    {

        // Properly formatting the display of the timer
        if (hour < 10)
            disp = "0" + hour + " : ";
        else
            disp = hour + " : ";

        if (minute < 10)
            disp += "0" + minute + " : ";
        else
            disp += minute + " : ";

        if (second < 10)
            disp += "0" + second + " : ";
        else
            disp += second + " : ";

        if (millisecond < 10)
            disp += "00" + millisecond;
        else if (millisecond < 100)
            disp += "0" + millisecond;
        else
            disp += millisecond;

        display.setText(disp);
    }

    // thread.run function
    public void run()
    {

        // while the stopwatch is on
        while (on) {
            try {
                // pause 1 millisecond
                Thread.sleep(1);
                // update the time
                update();
                // changeLabel
                changeLabel();
            }
            catch (InterruptedException e) {
                System.out.println(e);
            }
        }
    }

    // actionPerformed
    // To listen to the actions on the buttons
    public void actionPerformed(ActionEvent e)
    {

        // start a thread when start button is clicked
        if (e.getSource() == start) {
            // stopwatch is on
            on = true;
            new Thread(this, "StopWatch").start();
        }

        // reset
        if (e.getSource() == reset) {
            // stopwatch off
            on = false;
            reset();
            changeLabel();
        }

        if (e.getSource() == stop) {
            // stopwatch off
            on = false;
        }
    }
}
```

**输出:**

[见此处](https://media.geeksforgeeks.org/wp-content/uploads/simplescreenrecorder-2018-06-08_00.03.22.mp4)