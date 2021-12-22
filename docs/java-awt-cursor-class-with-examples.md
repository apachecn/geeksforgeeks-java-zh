# Java AWT |带示例的 Cursor 类

> 原文:[https://www . geesforgeks . org/Java-awt-cursor-class-with-examples/](https://www.geeksforgeeks.org/java-awt-cursor-class-with-examples/)

游标类是 Java AWT 包的一部分，用于创建自定义游标或继承系统或预定义游标。
Cursor 类主要用于封装鼠标光标的位图表示。

**光标类的构造函数为:**

1.  **光标(int t)** :用指定的类创建光标
2.  **光标(字符串名称)**:创建具有指定名称的自定义光标。

**常用方法**

| 方法 | 说明 |
| --- | --- |
| getDefaultCursor() | 返回系统默认光标。 |
| 获取名（） | 返回此光标的名称。 |
| getPredefinedCursor（int t） | 返回具有指定预定义类型的光标对象。 |
| getSystemCustomCursor（String n） | 返回与指定名称匹配的系统特定自定义光标对象。 |
| getType() | 返回此光标的类型 |
| toString() | 返回此光标的字符串表示形式。 |
| 创建自定义光标(图像 I，点 p，字符串名称) | 使用指定的图像和名称创建自定义光标。 |

**1。将一些预定义光标和系统光标应用于组件(标签)的程序**

```java
// Java  Program to apply some predefined and system cursors to components (label)
import java.awt.*;
import javax.swing.*;
class cursor extends JFrame {
    // frame
    static JFrame f;

    // label
    static Label l, l1, l2;

    // default constructor
    cursor()
    {
    }

    // main class
    public static void main(String args[])
    {
        try {
            // create a frame
            f = new JFrame("cursor");

            // create e panel
            JPanel p = new JPanel();

            // create labels
            l = new Label("label one");
            l1 = new Label("label two");
            l2 = new Label("label three");

            // create cursors
            Cursor c = new Cursor(CROSSHAIR_CURSOR);
            Cursor c1 = new Cursor(HAND_CURSOR);

            // get System cursor
            Cursor c2 = Cursor.getSystemCustomCursor("Invalid.32x32");

            // set cursor
            l.setCursor(c);
            l1.setCursor(c1);
            l2.setCursor(c2);

            // add labels to panel
            p.add(l);
            p.add(l1);
            p.add(l2);

            // add panel to the frame
            f.add(p);

            // show the frame
            f.show();
            f.setSize(250, 300);
        }
        catch (Exception e) {
            System.err.println(e.getMessage());
        }
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-204359-1" width="238" height="294" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/2018-06-03-13-42-16.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/2018-06-03-13-42-16.mp4](https://media.geeksforgeeks.org/wp-content/uploads/2018-06-03-13-42-16.mp4)</video>

**2\. Program to add all predefined cursors to a choice**

```java
// Java Program to add all predefined cursors to a choice
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
class cursor extends JFrame implements ItemListener {
    // frame
    static JFrame f;

    // labels
    static Label l;

    // create a choice
    static Choice c;

    // default constructor
    cursor()
    {
    }

    // main class
    public static void main(String args[])
    {
        // create a frame
        f = new JFrame("cursor");

        // create e panel
        JPanel p = new JPanel();

        // create a choice
        c = new Choice();

        // add items to choice
        for (int i = 0; i < 14; i++)
            c.add(Cursor.getPredefinedCursor(i).getName());

        // object of class
        cursor cu = new cursor();

        // create a label
        l = new Label(" label one ");

        // add item listener to the choice
        c.addItemListener(cu);

        // add labels to panel
        p.add(l);
        p.add(c);

        // add panel to the frame
        f.add(p);

        // show the frame
        f.show();
        f.setSize(250, 300);
    }

    // if an item of choice is selected
    public void itemStateChanged(ItemEvent e)
    {
        // set the cursor
        l.setCursor(Cursor.getPredefinedCursor(c.getSelectedIndex()));
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-204359-2" width="238" height="292" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/2018-06-03-12-03-56.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/2018-06-03-12-03-56.mp4](https://media.geeksforgeeks.org/wp-content/uploads/2018-06-03-12-03-56.mp4)</video>

**3\. program to create a custom cursor and add it to labels**

```java
// Java program to create a custom cursor and add it to labels
import java.awt.*;
import javax.swing.*;
class cursor extends JFrame {
    // frame
    static JFrame f;

    // label
    static Label l, l1, l2;

    // default constructor
    cursor()
    {
        // create a frame
        f = new JFrame("cursor");

        // create e panel
        JPanel p = new JPanel();

        // extract image
        // the files gfg.jpg and gfg.png contains image of cursor
        Image i = Toolkit.getDefaultToolkit().getImage("f:\\gfg.jpg");
        Image i1 = Toolkit.getDefaultToolkit().getImage("f:\\gfg.png");

        // point p
        Point p11 = new Point(0, 0);

        // create labels
        l = new Label("label one");
        l1 = new Label("label two");

        // create cursors
        Cursor c = Toolkit.getDefaultToolkit().createCustomCursor(i, p11, "cursor1");
        Cursor c1 = Toolkit.getDefaultToolkit().createCustomCursor(i1, p11, "cursor2");

        // set cursor
        l.setCursor(c);
        l1.setCursor(c1);

        // add labels to panel
        p.add(l);
        p.add(l1);

        // add panel to the frame
        f.add(p);

        // show the frame
        f.show();
        f.setSize(250, 300);
    }

    // main class
    public static void main(String args[])
    {
        cursor c = new cursor();
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-204359-3" width="236" height="292" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/2018-06-03-13-30-17.mp4?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/2018-06-03-13-30-17.mp4](https://media.geeksforgeeks.org/wp-content/uploads/2018-06-03-13-30-17.mp4)</video>
**Note : The programs might not run in an online IDE please use an offline IDE.**