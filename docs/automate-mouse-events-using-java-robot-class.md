# 使用 Java 机器人类

自动化鼠标事件

> 原文:[https://www . geesforgeks . org/automate-mouse-events-use-Java-robot-class/](https://www.geeksforgeeks.org/automate-mouse-events-using-java-robot-class/)

Robot 是 java.awt 包的一部分。Robot 类基本上用于生成本机系统输入事件，用于自运行演示、测试自动化和其他使用鼠标和键盘控制的应用程序。
Robot 类生成的事件可以用来控制鼠标、键盘，也可以用来截图屏幕。在本文中，我们将实现 Java Robot，将鼠标移动或拖动到指定位置。
**使用的方法:**

1.  **鼠标移动(int x，int y) :** 将鼠标移动到屏幕的指定位置
2.  **按键(int k) :** 用指定的键码按给定的键
3.  **键释放(int k) :** 用指定的键码释放给定的键
4.  **鼠标按下(int b) :** 按下一个或多个鼠标按钮。
5.  **鼠标释放(int b) :** 释放一个或多个鼠标按钮。

**程序 1:将鼠标从初始位置移动到指定位置的 Java 程序**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to move a mouse from the initial
// location to a specified location
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

class robomouse extends Frame implements ActionListener {
    // Frame
    static JFrame f;

    // textField
    static TextField x, y;

    // default constructor
    robomouse()
    {
    }

    // main function
    public static void main(String args[])
    {
        // object of class
        robomouse rm = new robomouse();

        // create a frame
        f = new JFrame("robomouse");

        // set the frame to close on exit
        f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        // create textfield
        x = new TextField(7);
        y = new TextField(7);

        // create a button
        Button b = new Button("OK");

        // add actionListener
        b.addActionListener(rm);

        // create a panel
        Panel p = new Panel();

        // add items to panel
        p.add(x);
        p.add(y);
        p.add(b);

        f.add(p);

        // setsize of frame
        f.setSize(300, 300);

        f.show();
    }

    // if button is pressed
    public void actionPerformed(ActionEvent e)
    {
        try {
            Robot r = new Robot();
            int xi1, yi1, xi, yi;

            // get initial location
            Point p = MouseInfo.getPointerInfo().getLocation();
            xi = p.x;
            yi = p.y;

            // get x and y points
            xi1 = Integer.parseInt(x.getText());
            yi1 = Integer.parseInt(y.getText());
            int i = xi, j = yi;

            // slowly move the mouse to defined location
            while (i != xi1 || j != yi1) {
                // move the mouse to the other point
                r.mouseMove(i, j);

                if (i < xi1)
                    i++;
                if (j < yi1)
                    j++;

                if (i > xi1)
                    i--;
                if (j > yi1)
                    j--;

                // wait
                Thread.sleep(30);
            }
        }
        catch (Exception evt) {
            System.err.println(evt.getMessage());
        }
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-201628-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/move1-convert-video-online.com_.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/move1-convert-video-online.com_.mp4](https://media.geeksforgeeks.org/wp-content/uploads/move1-convert-video-online.com_.mp4)</video>

**程序 2 : Java 程序将鼠标从一个位置拖动到另一个位置**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
class robomouse1 extends Frame implements ActionListener {
    // Frame
    static JFrame f;

    // textField
    static TextField x, y, x1, y1;

    // default constructor
    robomouse1()
    {
    }

    // main function
    public static void main(String args[])
    {
        // object of class
        robomouse1 rm = new robomouse1();

        // create a frame
        f = new JFrame("robomouse");

        // set the frame to close on exit
        f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        // create textfield
        x = new TextField(7);
        y = new TextField(7);

        x1 = new TextField(7);
        y1 = new TextField(7);

        // create a button
        Button b = new Button("OK");

        // add actionListener
        b.addActionListener(rm);

        // create a panel
        Panel p = new Panel();

        // create labels
        Label l, l1;

        l = new Label("from");
        l1 = new Label("to");

        // add items to panel
        p.add(l);
        p.add(x);
        p.add(y);
        p.add(l1);
        p.add(x1);
        p.add(y1);
        p.add(b);

        f.add(p);

        // setsize of frame
        f.setSize(600, 300);

        f.show();
    }

    // if button is pressed
    public void actionPerformed(ActionEvent e)
    {
        try {
            Robot r = new Robot();
            int xi, yi, xi1, yi1;

            // get x and y points
            xi = Integer.parseInt(x.getText());
            yi = Integer.parseInt(y.getText());
            xi1 = Integer.parseInt(x1.getText());
            yi1 = Integer.parseInt(y1.getText());

            // move the mouse to that point
            r.mouseMove(xi, yi);

            // press the mouse
            r.mousePress(InputEvent.BUTTON1_MASK);

            int i = xi, j = yi;

            // slowly drag the mouse to defined location
            while (i < xi1 || j < yi1) {
                // move the mouse to the other point
                r.mouseMove(i, j);

                if (i < xi1)
                    i++;
                if (j < yi1)
                    j++;

                // wait
                Thread.sleep(30);
            }

            // wait
            Thread.sleep(4000);

            // press the mouse
            r.mouseRelease(InputEvent.BUTTON1_MASK);
        }
        catch (Exception evt) {
            System.err.println(evt.getMessage());
        }
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-201628-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/move2.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/move2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/move2.mp4)</video>

**注意:代码可能无法在在线编译器中运行，请使用离线 IDE。**