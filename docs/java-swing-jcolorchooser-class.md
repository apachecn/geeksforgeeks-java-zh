# Java Swing | JColorChooser 类

> 原文:[https://www . geesforgeks . org/Java-swing-jcolorchoser-class/](https://www.geeksforgeeks.org/java-swing-jcolorchooser-class/)

JColorChooser 提供了一个控件面板，旨在允许用户操作和选择颜色。该类提供*三级 API* :

1.  一种静态便利方法，显示模式颜色选择器对话框并返回用户选择的颜色。
2.  一种创建颜色选择器对话框的静态便利方法，其中*动作监听器*可以被指定为当用户按下其中一个对话框按钮时被调用。
3.  能够直接(在任何容器内)创建 *JColorChooser* 窗格的实例。*属性改变*可以添加监听器来检测当前“颜色”属性何时改变。

**类的构造函数:**

1.  **JColorChooser():** 创建初始颜色为白色的颜色选择器窗格。
2.  **JColorChooser(颜色初始颜色):**使用指定的初始颜色创建颜色选择器窗格。
3.  **JColorChooser(颜色选择模型):**用指定的*颜色选择模型*创建颜色选择面板。

**常用方法:**

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| setColor(颜色) | 将颜色选择器的当前颜色设置为指定颜色。 |
| setColor(int c) | 将颜色选择器的当前颜色设置为指定颜色。 |
| setColor(int r，int g，int b) | 将颜色选择器的当前颜色设置为指定的 RGB 颜色。 |
| 显示对话框(组件 cmp，字符串标题，颜色初始化 _ 颜色) | 显示一个模式颜色选择器对话框，并阻塞直到对话框被隐藏。 |
| updateUI() | 来自 UIManager 的 L&F 已更改的通知
 |
| setchooserpanels(抽象 ColorChooserPanel[]面板) | 指定用于选择颜色值的颜色面板。 |
| addchooserpanel 面板(抽象 color chooser 面板) | 向颜色选择器添加颜色选择器面板。 |
| setui(color choui) | 设置呈现此组件的 L&F 对象。 |
| setselectionmodel(color selection model new model) | 设置包含所选颜色的模型。 |
| preview 面板(JComponent preview) | 设置当前预览面板。 |

</figure>

**创建自定义选择器面板:**默认颜色选择器提供五个选择器面板:

1.  **色板:**用于从色板集合中选择颜色。
2.  **HSV:** 用于使用色调-饱和度-值颜色表示选择颜色。在 JDK 7 之前，它被称为 HSB，代表色调-饱和度-亮度。
3.  **HSL:** 用于使用色相-饱和度-明度颜色表示来选择颜色。
4.  **RGB:** 用于使用红绿蓝颜色模型选择颜色。
5.  **CMYK:** 用于选择使用混色或四色模式的颜色。

下面的程序说明了 JColorChooser 类的使用:

**1。使用 ChangeListener 实现 JColorChooser 类的 Java 程序:**在这个程序中，我们首先在窗口顶部创建一个标签，其中显示了一些文本，我们将在其中应用颜色变化。设置前景色和背景色。设置字体的大小和类型。创建一个面板并设置其布局。现在设置颜色选择器来设置文本颜色。使用 *stateChanged()* 方法，使用 *getColor()* 方法生成文本颜色变化的事件。现在创建图形用户界面，创建一个设置窗口。设置窗口的默认关闭操作。创建并设置内容窗格，向框架添加内容并显示窗口。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to implement JColorChooser
// class using ChangeListener
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.event.*;
import javax.swing.colorchooser.*;

public class ColorChooserDemo extends JPanel

    implements ChangeListener {

    protected JColorChooser Jcc;
    protected JLabel label;

    public ColorChooserDemo()
    {
        super(new BorderLayout());

        // Set up the Label at the top of the window
        label = new JLabel("Welcome to GeeksforGeeks",
                                       JLabel.CENTER);

        // set the foreground color of the text
        label.setForeground(Color.green);

        // set background color of the field
        label.setBackground(Color.WHITE);
        label.setOpaque(true);

        // set font type and size of the text
        label.setFont(new Font("SansSerif", Font.BOLD, 30));

        // set size of the label
        label.setPreferredSize(new Dimension(100, 65));

        // create a Panel and set its layout
        JPanel bannerPanel = new JPanel(new BorderLayout());
        bannerPanel.add(label, BorderLayout.CENTER);
        bannerPanel.setBorder(BorderFactory.createTitledBorder("Label"));

        // Set up color chooser for setting text color
        Jcc = new JColorChooser(label.getForeground());
        Jcc.getSelectionModel().addChangeListener(this);
        Jcc.setBorder(BorderFactory.createTitledBorder(
            "Choose Text Color"));

        add(bannerPanel, BorderLayout.CENTER);
        add(Jcc, BorderLayout.PAGE_END);
    }

    public void stateChanged(ChangeEvent e)
    {
        Color newColor = Jcc.getColor();
        label.setForeground(newColor);
    }

    // Create the GUI and show it.  For thread safety,
    // this method should be invoked from the
    // event-dispatching thread.
    private static void createAndShowGUI()
    {

        // Create and set up the window.
        JFrame frame = new JFrame("ColorChooserDemo");

        // set default close operation of the window.
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        // Create and set up the content pane.
        JComponent newContentPane = new ColorChooserDemo();

        // content panes must be opaque
        newContentPane.setOpaque(true);

        // add content pane to the frame
        frame.setContentPane(newContentPane);

        // Display the window.
        frame.pack();
        frame.setVisible(true);
    }

    // Main Method
    public static void main(String[] args)
    {

        // Schedule a job for the event-dispatching thread:
        // creating and showing this application's GUI.
        javax.swing.SwingUtilities.invokeLater(new Runnable() {

            public void run()
            {

                createAndShowGUI();
            }
        });
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-222470-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20180830_205846.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20180830_205846.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20180830_205846.mp4)</video>

**2。使用 ActionListener 实现 JColorChooser 类的 Java 程序:**创建一个按钮和一个容器，并设置容器的布局。将 *ActionListener()* 添加到按钮，并将一个按钮添加到容器。*actionlistener()*有一个方法 *actionPerformed()* 一点击按钮就实现了。选择颜色并设置容器的背景颜色。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to implement JColorChooser
// class using ActionListener
import java.awt.event.*;
import java.awt.*;
import javax.swing.*;

public class ColorChooserExample extends
      JFrame implements ActionListener {

    // create a button
    JButton b = new JButton("color");

    Container c = getContentPane();

    // Constructor
    ColorChooserExample()
    {

        // set Layout
        c.setLayout(new FlowLayout());

        // add Listener
        b.addActionListener(this);

        // add button to the Container
        c.add(b);
    }

    public void actionPerformed(ActionEvent e)
    {

        Color initialcolor = Color.RED;

        // color chooser Dialog Box
        Color color = JColorChooser.showDialog(this,
                    "Select a color", initialcolor);

        // set Background color of the Container
        c.setBackground(color);
    }

    // Main Method
    public static void main(String[] args)
    {

        ColorChooserExample ch = new ColorChooserExample();
        ch.setSize(400, 400);
        ch.setVisible(true);
        ch.setDefaultCloseOperation(EXIT_ON_CLOSE);
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-222470-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20180826_123241.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20180826_123241.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20180826_123241.mp4)</video>

**注意:**上述程序可能无法在在线 IDE 中运行。请使用离线编译器。
**参考:**[https://docs . Oracle . com/javase/7/docs/API/javax/swing/jcolorchooser . html](https://docs.oracle.com/javase/7/docs/api/javax/swing/JColorChooser.html)