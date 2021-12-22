# Java Swing |带示例的弹出式和弹出式工厂

> 原文:[https://www . geesforgeks . org/Java-swing-popup-and-popupfactory-with-examples/](https://www.geeksforgeeks.org/java-swing-popup-and-popupfactory-with-examples/)

Popup 和 PopupFactory 是 Java Swing 库的一部分。当我们想要向用户显示特定包含层次结构中所有其他组件之上的组件时，会使用弹出窗口。PopupFactory 是用于创建弹出窗口的类。弹出窗口的生命周期非常短，通常是子组件有限的轻量级组件。
**类的构造函数有:**

1.  **弹出工厂():**为弹出工厂创建一个对象

**常用方法** :

<figure class="table">

| 方法 | 说明 |
| --- | --- |
| **获取弹出窗口(组件 o，组件 c，int x，int y)** | 在所有者组件的 x，y 位置为包含组件 c 的组件 o 创建一个弹出窗口。 |
| **隐藏()** | 隐藏和处置弹出窗口。 |
| **显示()** | 使弹出窗口可见。 |

</figure>

下面的程序将说明弹出窗口的使用:

1.  **Java 程序创建一个弹出窗口并显示在父框架**上:我们通过创建一个弹出窗口工厂并使用返回弹出窗口的函数 getpopup()来创建一个弹出窗口 p。我们将这个弹出窗口添加到标题为“pop”的框架 f 中，我们将创建一个标签，并将 t 添加到容器面板 p2 中，并使用 setBackground()函数设置面板 p2 的背景。我们将把容器面板 p2 添加到弹出窗口中。我们还将创建一个名为“click”的按钮 b，添加一个动作监听器，并在按钮被按下时显示弹出窗口。按钮 b 被添加到面板，面板被添加到框架。使用设置大小(400，400)将帧设置为大小 400，400。最后，使用 show()函数显示框架。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to create a popup and display
// it on a parent frame
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
class pop extends JFrame implements ActionListener {
    // popup
    Popup p;

    // constructor
    pop()
    {
        // create a frame
        JFrame f = new JFrame("pop");

        // create a label
        JLabel l = new JLabel("This is a popup");

        f.setSize(400, 400);

        PopupFactory pf = new PopupFactory();

        // create a panel
        JPanel p2 = new JPanel();

        // set Background of panel
        p2.setBackground(Color.red);

        p2.add(l);

        // create a popup
        p = pf.getPopup(f, p2, 180, 100);

        // create a button
        JButton b = new JButton("click");

        // add action listener
        b.addActionListener(this);

        // create a panel
        JPanel p1 = new JPanel();

        p1.add(b);
        f.add(p1);
        f.show();
    }

    // if the button is pressed
    public void actionPerformed(ActionEvent e)
    {
        p.show();
    }
    // main class
    public static void main(String args[])
    {
        pop p = new pop();
    }
}
```