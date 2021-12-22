# Java AWT | GridBagLayout 类

> 原文:[https://www.geeksforgeeks.org/java-awt-gridbaglayout-class/](https://www.geeksforgeeks.org/java-awt-gridbaglayout-class/)

GridBagLayout 类是一个灵活的布局管理器。它用于水平、垂直或沿基线对齐组件。它不需要同样大小的组件。每个 GridBagLayout 对象管理一个矩形单元格网格，每个组件动态占据一个或多个单元格，称为其显示区域。GridBagLayout 组件与 GridBagConstraints 实例相关联。这些约束用于定义组件的显示区域及其位置。除了它的约束对象，GridBagLayout 还考虑每个组件的最小和首选大小，以确定组件的大小。GridBagLayout 组件也排列在矩形网格中，但是可以有不同的大小，并且可以占据多行或多列。

**施工方:**

*   **GridBagLayout():** 用于创建网格包布局管理器。

**常用方法:**

*   **移除布局组件(组件 cmp):** 从布局中移除指定的组件。
*   **getLayoutAlignmentY(容器 p):** 返回沿 y 轴的对齐。
*   **添加布局组件(组件 cmp，对象 cons):** 将具有指定名称的指定组件添加到布局中。
*   **toString():** 返回此网格包布局值的字符串表示形式。
*   **getLayoutAlignmentX(容器 p):** 返回沿 x 轴的对齐。
*   **获取约束(组件 cmp):** 获取指定组件的约束。
*   **最大尺寸(容器焦油):**给定指定目标容器中的组件，返回该布局的最大尺寸。
*   **minimumLayoutSize(容器标准尺寸):**使用此网格袋布局确定父容器的最小尺寸。

下面的程序说明了 GridBagLayout 类:

*   **程序 1:** 下面的程序将几个行列组件排列在一个 *JFrame* 中，其实例类命名为“ *Gridbagdemo* ”。我们创建了 4 个名为“ *java* ”、“*布局*”、“*管理器*”、“*演示*”的组件，然后通过 *add()* 的方法将其添加到 *JFrame* 中。我们通过*设置大小()*和*设置可见()*的方法设置框架的大小和可见性。布局通过*设置布局()*的方法设置。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate GridBagLayout class.
import java.awt.*;
import java.awt.event.*;
import javax.swing.JFrame;
import javax.swing.*;

// class extends JFrame
public class GridbagDemo extends JFrame {

    GridbagDemo()
    {

        // Function to set title of JFrame.
        setTitle("GridBagLayoutDemo");

        // Creating Object of Jpanel class
        JPanel p = new JPanel();

        // set the layout
        p.setLayout(new GridBagLayout());

        // creates a constraints object
        GridBagConstraints c = new GridBagConstraints();

        // insets for all components
        c.insets = new Insets(2, 2, 2, 2);

        // column 0
        c.gridx = 0;

        // row 0
        c.gridy = 0;

        // increases components width by 10 pixels
        c.ipadx = 15;

        // increases components height by 50 pixels
        c.ipady = 50;

        // constraints passed in
        p.add(new JButton("Java Swing"), c);

        // column 1
        c.gridx = 1;

        // increases components width by 70 pixels
        c.ipadx = 90;

        // increases components height by 40 pixels
        c.ipady = 40;

        // constraints passed in
        p.add(new JButton("Layout"), c);

        // column 0
        c.gridx = 0;

        // row 2
        c.gridy = 1;

        // increases components width by 20 pixels
        c.ipadx = 20;

        // increases components height by 20 pixels
        c.ipady = 20;

        // constraints passed in
        p.add(new JButton("Manager"), c);

        // increases components width by 10 pixels
        c.ipadx = 10;

        // column 1
        c.gridx = 1;

        // constraints passed in
        p.add(new JButton("Demo"), c);

        // Creating Object of "wndcloser"
        // class of windowlistener
        WindowListener wndCloser = new WindowAdapter() {

            public void windowClosing(WindowEvent e)
            {

                // exit the system
                System.exit(0);
            }
        };

        // add the actionwindowlistener
        addWindowListener(wndCloser);

        // add the content
        getContentPane().add(p);

        // Function to set size of JFrame.
        setSize(600, 400);

        // Function to set visibility of JFrame.
        setVisible(true);
    }

    // Main Method
    public static void main(String[] args)
    {

        // calling the constructor
        new GridbagDemo();
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-219701-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/gfggb1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/gfggb1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/gfggb1.mp4)</video>

*   **程序 2:** 下面的程序将几个行列组件排列在一个 *JFrame* 中，其实例类命名为“ *Gridbagdemo* ”。我们创建 5 个 *JButton* 组件，然后通过 *add()* 方法将它们添加到 *JFrame* 中。我们通过方法 setTitle、 *setSize()* 和 *setVisible()* 设置框架的标题、大小和可见性。布局通过*设置布局()*的方法设置。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate GridBagLayout class.
import java.awt.*;
import javax.swing.JButton;
import javax.swing.JFrame;

// Constructor of GridBagLayout class.
public class GridBagLayoutDemo {

    final static boolean shouldFill = true;
    final static boolean shouldWeightX = true;
    final static boolean RIGHT_TO_LEFT = false;

public static void addComponentsToPane(Container pane)
{

    // if condition
    if (RIGHT_TO_LEFT) {

        pane.setComponentOrientation(ComponentOrientation.RIGHT_TO_LEFT);
    }

    // Declaration of objects of JButton class
    JButton button;

    // set the layout
    pane.setLayout(new GridBagLayout());

    // creates a constraints object
    GridBagConstraints c = new GridBagConstraints();

    // if condition
    if (shouldFill) {

        // natural height, maximum width
        c.fill = GridBagConstraints.HORIZONTAL;
    }

    // Initialization of object
    // "button" of JButton class.
    button = new JButton("Button 1");

    // if condition
    if (shouldWeightX) {
        c.weightx = 0.5;
    }

    // column 0
    c.gridx = 0;

    // row 0
    c.gridy = 0;

    // Adding JButton "button" on JFrame.
    pane.add(button, c);

    // Initialization of object
    // "button" of JButton class.
    button = new JButton("Button 2");

    // column 1
    c.gridx = 1;

    // row 0
    c.gridy = 0;

    // Adding JButton "button" on JFrame.
    pane.add(button, c);

    // Initialization of object
    // "button" of JButton class.
    button = new JButton("Button 3");

    // column 1
    c.gridx = 2;

    // row 0
    c.gridy = 0;

    // Adding JButton "button" on JFrame.
    pane.add(button, c);

    // Initialization of object
    // "button" of JButton class.
    button = new JButton("Long-Named Button 4");

    // increases components height by 40 pixels
    c.ipady = 40;

    // column width 0
    c.weightx = 0.0;

    // row width 3
    c.gridwidth = 3;

    // column 1
    c.gridx = 0;

    // row 1
    c.gridy = 1;

    // Adding JButton "button" on JFrame.
    pane.add(button, c);

    // Initialization of object
    // "button" of JButton class.
    button = new JButton("Button 5");

    // increases components height by 0 pixels
    c.ipady = 0;

    // request any extra vertical space
    c.weighty = 1.0;

    // bottom of space
    c.anchor = GridBagConstraints.PAGE_END;

    // top padding
    c.insets = new Insets(10, 0, 0, 0);

    // column 2
    c.gridx = 1;

    // 2 columns wide
    c.gridwidth = 2;

    // row 3
    c.gridy = 2;

    // Adding JButton "button" on JFrame.
    pane.add(button, c);
}

// Create the GUI and show it.  For thread safety,
// this method should be invoked from the
// event-dispatching thread.
private static void createAndShowGUI()
{

    // to set a Jframe default
    JFrame.setDefaultLookAndFeelDecorated(true);

    // Create and set up the window.
    JFrame frame = new JFrame("GridBagLayoutDemo");

    // Function to close the operation of JFrame.
    frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

    // adding the content pane.
    addComponentsToPane(frame.getContentPane());

    // Display the window.
    frame.pack();

    // Function to set visible status of JFrame.
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

<video class="wp-video-shortcode" id="video-219701-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/gfggd2.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/gfggd2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/gfggd2.mp4)</video>

**注意:**上述程序可能无法在在线 IDE 中运行。请使用离线编译器。
**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/awt/gridbaglayout . html](https://docs.oracle.com/javase/7/docs/api/java/awt/GridBagLayout.html)