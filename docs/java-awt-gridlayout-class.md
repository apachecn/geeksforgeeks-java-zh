# Java AWT | GridLayout 类

> 原文:[https://www.geeksforgeeks.org/java-awt-gridlayout-class/](https://www.geeksforgeeks.org/java-awt-gridlayout-class/)

GridLayout 类表示在矩形网格中具有指定行数和列数的布局管理器。GridLayout 容器被分成大小相等的矩形，每个矩形中放置一个组件。每个矩形单元格都有相同的大小，因此，它们包含一个填充整个单元格的组件。当用户改变或调整容器的尺寸时，每个矩形的尺寸也相应地改变。

**类的构造函数:**

1.  **GridLayout():** 它创建一个网格布局，默认每个组件在一行中有一列。
2.  **GridLayout(int rw，int cl):** 它创建具有指定行数和列数的网格布局。
3.  **GridLayout(int rw，int cl，int hgap，int vgap):** 它创建具有指定行数和列数的网格布局，并具有水平和垂直间隙。

**常用方法:**

*   **添加布局组件(String str，Component cmp):** 将具有指定名称的指定组件添加到布局中。
*   **设置列数(int cl):** 将此布局中的列数设置为指定值。
*   **设置 Hgap(int hgap):** 将组件之间的水平间隙设置为指定值。
*   **设置行数(int rw):** 将此布局中的行数设置为指定值。
*   **设置 Vgap(int vgap):** 将组件之间的垂直间隙设置为指定值。
*   **layoutContainer(Container pr):**使用此布局布局指定的容器。
*   **toString():** 返回该网格布局值的字符串表示形式。

下面的程序说明了网格布局类:

*   **Program 1:** In below program we are passing the argument in *GridLayout*. We create 4 *JLabel* components named “*one*“, “*two*“, “*three*“, “*four*” and create 2 *JButton* components named “*buttonsave*” and “*buttonexit*” and create 4 *Jtextfield* components named “*tname*“, “*tcode*“, “*tdesig*“, “*tsalary*” and all of add them to the *JFrame* by the method add(). We will set the visibility and size of the frame by using *setVisible()* and *setSize()* method. The layout is set by using *setLayout()* method.

    ```java
    // Java program to illustrate the GridLayout
    import javax.swing.*;
    import java.awt.*;

    // class GridLayout extends JFrame
    public class GridLayoutDemo extends JFrame {

    GridLayoutDemo() {

        // Creating Object P1 of JPanel class
        JPanel p1 = new JPanel();

        // set the layout
        p1.setLayout(new GridLayout(4, 2));

        // Creating Object of "FlowLayout" class
        FlowLayout layout = new FlowLayout();

        // Creating Object P2 of JPanel class
        JPanel p2 = new JPanel();

        // set the layout
        p2.setLayout(layout);

        // Declaration of objects of JLabel class.
        JLabel one, two, three, four;

        // Declaration of objects of JTextField class.
        JTextField tname, tsalary, tcode, tdesig;

        // Declaration of objects of JButton class.
        JButton buttonSave, buttonExit;

        // Initialization of object 
        // "one" of JLabel class.
        one = new JLabel("NAME");

        // Initialization of object 
        // "tname" of JTextField class.
        tname = new JTextField(20);

        // Initialization of object
        // "two" of JLabel class.
        two = new JLabel("CODE");

        // Initialization of object 
        // "tcode" of JTextField class.
        tcode = new JTextField(20);

        // Initialization of object
        // "three" of JLabel class.
        three = new JLabel("DESIGNATION");

        // Initialization of object 
        // "tdesig" of JTextField class.
        tdesig = new JTextField(20);

        // Initialization of object
        // "four" of JLabel class.
        four = new JLabel("SALARY");

        // Initialization of object 
        // "tsalary" of JTextField class.
        tsalary = new JTextField(20);

        // Initialization of object
        // "buttonsave" of JButton class.
        buttonSave = new JButton("SAVE");

        // Initialization of object
        // "buttonexit" of JButton class.
        buttonExit = new JButton("EXIT");

        // Adding Jlabel "one" on JFrame.
        p1.add(one);

        // Adding JTextField "tname" on JFrame.
        p1.add(tname);

        // Adding Jlabel "two" on JFrame.
        p1.add(two);

        // Adding JTextField "tcode" on JFrame.
        p1.add(tcode);

        // Adding Jlabel "three" on JFrame.
        p1.add(three);

        // Adding JTextField "tdesig" on JFrame.
        p1.add(tdesig);

        // Adding Jlabel "four" on JFrame.
        p1.add(four);

        // Adding JTextField "tsalary" on JFrame.
        p1.add(tsalary);

        // Adding JButton "buttonsave" on JFrame.
        p2.add(buttonSave);

        // Adding JButton "buttonexit" on JFrame.
        p2.add(buttonExit);

        // add the p1 object which 
        // refer to the Jpanel
        add(p1, "North");

        // add the p2 object which
        // refer to the Jpanel
        add(p2, "South");

        // Function to set visible
        // status of JFrame.
        setVisible(true);

        // this Keyword refers to current
        // object. Function to set size of JFrame.
        this.setSize(400, 180);
    }

        // Main Method
        public static void main(String args[])
        {

            // calling the constructor
            new GridLayoutDemo();
        }
    }
    ```

    **输出:**

    <video class="wp-video-shortcode" id="video-219795-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/Untitled-14.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/Untitled-14.mp4](https://media.geeksforgeeks.org/wp-content/uploads/Untitled-14.mp4)</video>
*   **Program 2:** In below program we are passing the argument in *GridLayout*. We create 5 *JButton* components named “*btn1*“, “*btn2*“, “*btn3*“, “*btn4*“, “*btn5*” and then add them to the *JFrame* by the method *add()*. We will set the visibility and size of the frame by using *setvisible()* and *setsize()* method. The layout is set by using *setLayout()* method.

    ```java
    // Java program to illustrate the GridLayout
    import java.awt.*;
    import javax.swing.*;

    // create a class griddemo
    public class Griddemo {

    // Main Method
    public static void main(String[] args)
    {

        // Creating Object of JFrame class 
        // with new name frame
        JFrame frame = new JFrame("GridLayout Demo");

        // Initialization of object 
        // "btn1" of JButton class.
        JButton btn1 = new JButton("Button 1");

        // Initialization of object 
        // "btn2" of JButton class.
        JButton btn2 = new JButton("Button 2");

        // Initialization of object 
        // "btn3" of JButton class.
        JButton btn3 = new JButton("Button 3");

        // Initialization of object
        // "btn4" of JButton class.
        JButton btn4 = new JButton("Button 4");

        // Initialization of object 
        // "btn5" of JButton class.
        JButton btn5 = new JButton("Button 5");

        // Creating Object Panel of JPanel class
        // create grid layout with 3 rows, 
        // 2 columns with horizontal and 
        // vertical gap set to 10
        JPanel panel = new JPanel(new GridLayout(3, 2, 10, 10));

        // Adding JButton "btn1" on JPanel.
        panel.add(btn1);

        // Adding JButton "btn2" on JPanel.
        panel.add(btn2);

        // Adding JButton "btn3" on JPanel.
        panel.add(btn3);

        // Adding JButton "btn4" on JPanel.
        panel.add(btn4);

        // Adding JButton "btn5" on JPanel.
        panel.add(btn5);

        // Function to close the operation of JFrame.
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        // Function to set size of JFrame.
        frame.setSize(300, 150);

        // Function to get the content of JFrame.
        frame.getContentPane().add(panel);

        // Function to set visible status of JFrame.
        frame.setVisible(true);
    }
    }
    ```

    **输出:**

    <video class="wp-video-shortcode" id="video-219795-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/Untitled-13Trim-2.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/Untitled-13Trim-2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/Untitled-13Trim-2.mp4)</video>

**注意:**上述程序可能无法在在线 IDE 中运行。请使用离线编译器。

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/awt/gridlayout . html](https://docs.oracle.com/javase/7/docs/api/java/awt/GridLayout.html)