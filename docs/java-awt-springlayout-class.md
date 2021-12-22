# Java AWT | SpringLayout 类

> 原文:[https://www.geeksforgeeks.org/java-awt-springlayout-class/](https://www.geeksforgeeks.org/java-awt-springlayout-class/)

AWT(抽象窗口工具包)中的一个 SpringLayout 类根据一组布局约束将子级布局到其关联的容器中。每个约束由一个弹簧对象表示，该对象控制两个组件边之间的垂直或水平距离。这些边可以属于容器的任何子级，也可以属于容器本身。默认情况下，*弹簧布局*创建约束，使其关联组件具有*最小*、*首选*、*最大*和*实际*值。

**施工方:**

*   **SpringLayout():** 用于构造一个新的 SpringLayout 类。

**常用方法:**

*   **void addLayoutComponent(Component com，Object cons):** 如果约束是 *SpringLayout 的一个实例。约束*，将约束与指定的组件相关联。
*   **getLayoutAlignmentX(容器 c):** 用于返回 0.5f(居中)。
*   **getLayoutAlignmentY(容器 c):** 用于返回 0.5f(居中)。
*   **getConstraint((String edge name，Component c):** 返回控制组件指定边缘与其父组件顶部或左侧边缘之间距离的弹簧。
*   **获取约束(组件 c):** 返回指定组件的约束。
*   **layoutContainer(容器父级):**用于布局指定的容器。

下面的程序说明了 SpringLayout 类:

*   **Program 1:** Below program arranges the components in a *JFrame*. We create 1 *JLabel* components named “*label*” and create a 1 *JTextField* named “*textfield*” and create a 2 classes, one is *JFrame class* and another is *SpringLayout class* and then add them to the *JFrame* by the method *add()*. We set the visibility of the frame using *setvisible()* method. The layout is set by using *setLayout()* method.

    ```java
    // Java program to show Example of SpringLayout.
    // in java. Importing different Package.
    import java.awt.Container;
    import javax.swing.JFrame;
    import javax.swing.JLabel;
    import javax.swing.JTextField;
    import javax.swing.SpringLayout;

    // construct a class springdemo
    public class Springdemo {

        // It is used to create and show GUI
        private static void createAndShowGUI()
        {

            // Creating Object of "JFrame" class
            JFrame frame = new JFrame("MySpringDemp");

            // Function to set default 
            // close operation of JFrame.
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

            // to get content pane
            Container contentPane = frame.getContentPane();

            // Creating Object of "Springlayout" class
            SpringLayout layout = new SpringLayout();

            // to set content pane
            contentPane.setLayout(layout);

            // Initialization of object 
            // "label" of JLabel class.
            JLabel label = new JLabel("Label: ");

            // Initialization of object 
            // "label" of JLabel class.
            JTextField textField = new JTextField("Enter the text ", 15);

            // to add content pane of JLabel
            contentPane.add(label);

            // to add content pane of JTextField
            contentPane.add(textField);

            // It is used to put the layout
            // constraint in JFrame using springLayout class
            layout.putConstraint(SpringLayout.WEST, label, 
                       6, SpringLayout.WEST, contentPane);

            layout.putConstraint(SpringLayout.NORTH, label, 
                       6, SpringLayout.NORTH, contentPane);

            layout.putConstraint(SpringLayout.WEST, textField,
                                 6, SpringLayout.EAST, label);

            layout.putConstraint(SpringLayout.NORTH, textField, 
                           6, SpringLayout.NORTH, contentPane);

            layout.putConstraint(SpringLayout.EAST, contentPane, 
                               6, SpringLayout.EAST, textField);

            layout.putConstraint(SpringLayout.SOUTH, contentPane, 
                               6, SpringLayout.SOUTH, textField);

            // Function to pack the JFrame.
            frame.pack();

            // Function to set visible status of JFrame.
            frame.setVisible(true);
        }

        // Main Method
        public static void main(String[] args)
        {
            javax.swing.SwingUtilities.invokeLater(new Runnable() 
            {

                // create a class
                public void run()
                {
                    // to create and show GUI
                    createAndShowGUI();
                }
            });
        }
    }
    ```

    **输出:**

    <video class="wp-video-shortcode" id="video-219508-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/gfgspr1.mp4.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/gfgspr1.mp4.mp4](https://media.geeksforgeeks.org/wp-content/uploads/gfgspr1.mp4.mp4)</video>
*   **Program 2:** Below program arranges the components in a *JFrame*. We create 1 class named “*springlayout* class” and create a 4 *JButton* components named “*b1″, “b2”, “b3”, “b4”, “b5*” and then add them to the *JFrame* by the method *add()*. We set the visibility of the frame by using the method *setvisible()*. The layout is set by *setLayout()* method.

    ```java
    // Java program to show Example of SpringLayout.
    // in java. Importing different Package.
    import java.awt.*;
    import javax.swing.*;

    // construct a class Springclassdemo
    public class Springclassdemo {

        // Main Method
        public static void main(String[] arguments)
        {

            // main window
            // Function to set the default look 
            // and feel decorated status of JFrame.
            JFrame.setDefaultLookAndFeelDecorated(true);

            // Creating Object of "JFrame" class
            JFrame frame = new JFrame("SpringLayoutExample Example");

            // Function to set the default 
            // close operation status of JFrame
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

            // Function to set the 
            // size status of JFrame
            frame.setSize(300, 200);

            // to get the content pane
            Container content = frame.getContentPane();

            // Creating Object of "SpringLayout" class
            SpringLayout layout = new SpringLayout();

            // to set the layout class
            frame.setLayout(layout);

            // Initialization of object 
            // "b1" of JButton class.
            Component b1 = new JButton("GEEKS");

            // Initialization of object 
            // "b2" of JButton class.
            Component b2 = new JButton("GFG");

            // Initialization of object
            // "b3" of JButton class.
            Component b3 = new JButton("JAVA");

            // Initialization of object
            // "b4" of JButton class.
            Component b4 = new JButton("Sudo Placement");

            // Adding the JButton "b1" on frame
            frame.add(b1);

            // Adding the JButton "b2" on frame
            frame.add(b2);

            // Adding the JButton "b3" on frame
            frame.add(b3);

            // Adding the JButton "b4" on frame
            frame.add(b4);

            // It is used to put the layout
            // constraint in JFrame using 
            // springLayout class on b1 JButton
            layout.putConstraint(SpringLayout.WEST, b1, 
                       25, SpringLayout.WEST, content);

            layout.putConstraint(SpringLayout.NORTH, b1, 
                        10, SpringLayout.NORTH, content);

            // It is used to put the layout
            // constraint in JFrame using 
            // springLayout class on b2 JButton
            layout.putConstraint(SpringLayout.WEST, b2, 
                       50, SpringLayout.WEST, content);

            layout.putConstraint(SpringLayout.NORTH, b2,
                            10, SpringLayout.SOUTH, b1);

            // It is used to put the layout
            // constraint in JFrame using 
            // springLayout class on b3 JButton
            layout.putConstraint(SpringLayout.WEST, b3, 
                       75, SpringLayout.WEST, content);

            layout.putConstraint(SpringLayout.NORTH, b3, 
                            10, SpringLayout.SOUTH, b2);

            // It is used to put the layout
            // constraint in JFrame using 
            // springLayout class on b4 JButton
            layout.putConstraint(SpringLayout.WEST, b4, 
                            15, SpringLayout.EAST, b1);

            layout.putConstraint(SpringLayout.NORTH, b4,
                        10, SpringLayout.NORTH, content);

            // Function to set the
            // visible status of JFrame
            frame.setVisible(true);
        }
    }
    ```

    **输出:**

    <video class="wp-video-shortcode" id="video-219508-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/gfgspring.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/gfgspring.mp4](https://media.geeksforgeeks.org/wp-content/uploads/gfgspring.mp4)</video>

**注意:**上述程序可能无法在在线 IDE 中运行。请使用离线编译器。

**参考:**[https://docs . Oracle . com/javase/7/docs/API/javax/swing/springlayout . html](https://docs.oracle.com/javase/7/docs/api/javax/swing/SpringLayout.html)