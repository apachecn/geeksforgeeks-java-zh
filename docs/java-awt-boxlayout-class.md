# Java AWT | BoxLayout 类

> 原文:[https://www.geeksforgeeks.org/java-awt-boxlayout-class/](https://www.geeksforgeeks.org/java-awt-boxlayout-class/)

BoxLayout 类用于垂直(沿 Y 轴)或水平(沿 X 轴)排列组件。在 BoxLayout 类中，组件被放在单行或单列中。组件不会换行，因此，例如，当调整框架大小时，组件的水平排列将保持水平排列。

**该类的构造函数:**

*   **BoxLayout(容器 c，int 轴):**创建一个用 X 轴或 Y 轴排列组件的 BoxLayout 类。

**常用方法:**

*   **addLayoutComponent(Component CMP，Object obj):** 此类不使用它。
*   **getLayoutAlignmentX(容器 con):** 返回容器沿 X 轴的对齐方式。
*   **getLayoutAlignmentY(容器 con):** 返回容器沿 Y 轴的对齐方式。
*   **最大尺寸(容器 con):** 返回目标容器可用于布局其包含的组件的最大尺寸。
*   **minimumLayoutSize(Container con):**返回布局指定目标容器中包含的组件所需的最小尺寸。
*   **removeLayoutComponent(Component CMP):**此类不使用它。
*   **layoutContainer(容器 tar):** 当需要布局指定的容器时，由 AWT 调用。

下面的程序说明了 BoxLayout 类:

*   **Program 1:** In the below program we are arranging several *JLabel* components in a *JFrame*. We create 1 *JPanel* component named *“Panel”* and 5 *JButton* components named “*jbtn1*“, “*jbtn2*“, “*jbtn3*“, “*jbtn4*“, “*jbtn5*“. Also, we are creating a *BoxLayout* component named “boxlayout” and one *JFrame* class and then add them to the *JFrame* by using *add()* method. We set the visibility of the frame using *setvisible()* method. The layout is set using *setLayout()* method.

    ```
    // Java program to demonstrate BoxLayout 
    // class along X-Axis
    import javax.swing.JFrame;
    import javax.swing.JButton;
    import javax.swing.BoxLayout;
    import javax.swing.Box;
    import javax.swing.JPanel;
    import javax.swing.border.EmptyBorder;
    import java.awt.Insets;
    import java.awt.Dimension;

    // taking a class Demo
    public class Demo {

        // Main Method
        public static void main(String[] args)
        {

            // Function to set up the window frame.
            JFrame.setDefaultLookAndFeelDecorated(true);

            // Creating Object of "JFrame" class
            JFrame frame = new JFrame("BoxLayout Example X_AXIS");

            // Declaration of objects of JButton class.
            JButton jbtn1, jbtn2, jbtn3, jbtn4, jbtn5;

            // Function to set the default
            // close operation of JFrame the.
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

            // Set the panel to add buttons
            JPanel panel = new JPanel();

            // Creating Object of "boxlayout" in 
            // X_Axis from left to right
            BoxLayout boxlayout = new BoxLayout(panel, BoxLayout.X_AXIS);

            // to set the box layout
            panel.setLayout(boxlayout);

            // Set border for the panel
            panel.setBorder(new EmptyBorder(new Insets(100, 150, 100, 150)));

            // Initialization of object "jb1" of JButton class.
            jbtn1 = new JButton("Button 1");

            // Initialization of object "jb2" of JButton class.
            jbtn2 = new JButton("Button 2");

            // Initialization of object "jb3" of JButton class.
            jbtn3 = new JButton("Button 3");

            // Initialization of object "jb4" of JButton class.
            jbtn4 = new JButton("Button 4");

            // Initialization of object "jb5" of JButton class.
            jbtn5 = new JButton("Button 5");

            // Adding JButton "jb1" on JFrame
            panel.add(jbtn1);

            // Adding JButton "jb2" on JFrame
            panel.add(jbtn2);

            // Adding JButton "jb3" on JFrame
            panel.add(jbtn3);

            // Adding JButton "jb4" on JFrame
            panel.add(jbtn4);

            // Adding JButton "jb5" on JFrame
            panel.add(jbtn5);

            // Function to set the panel  of JFrame.
            frame.add(panel);

            // Function to use the  pack of JFrame.
            frame.pack();

            // Function to set visible status of JFrame.
            frame.setVisible(true);
        }
    }
    ```

    **输出:**

    <video class="wp-video-shortcode" id="video-220262-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/gfgbl1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/gfgbl1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/gfgbl1.mp4)</video>
*   **Program 2:** The following program arranges the components along Y-AXIS in a *JFrame.* We create 1 *JPanel* components named *“Panel”*, 5 *JButton* components named “*jbtn1*“, “*jbtn2*“, “*jbtn3*“, “*jbtn4*“, “*jbtn5*“, a *BoxLayout* components named “boxlayout” and a one *JFrame* class and then add them to the *JFrame* by using *add()* method. We will set the visibility of the frame by using *setvisible()* method. The layout is set by using *setLayout()* method.

    ```
    // Java program to demonstrate BoxLayout 
    // class along Y-Axis
    import javax.swing.JFrame;
    import javax.swing.JButton;
    import javax.swing.BoxLayout;
    import javax.swing.Box;
    import javax.swing.JPanel;
    import javax.swing.border.EmptyBorder;
    import java.awt.Insets;
    import java.awt.Dimension;

    // construct a class Demo_1
    public class Demo_1 {

        // Main Method
        public static void main(String[] args)
        {

            // Function to set up the window frame.
            JFrame.setDefaultLookAndFeelDecorated(true);

            // Creating Object of "JFrame" class
            JFrame frame = new JFrame("BoxLayout Example Y_AXIS");

            // Declaration of objects of JButton class.
            JButton jbtn1, jbtn2, jbtn3, jbtn4, jbtn5;

            // Function to set the default close operation of JFrame the.
            frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

            // Set the panel to add buttons
            JPanel panel = new JPanel();

            // Creating Object of "boxlayout" in Y_Axis from top to down
            BoxLayout boxlayout = new BoxLayout(panel, BoxLayout.Y_AXIS);

            // to set the box layout
            panel.setLayout(boxlayout);

            // Set border for the panel
            panel.setBorder(new EmptyBorder(new Insets(100, 150, 100, 150)));

            // Initialization of object "jb1" of JButton class.
            jbtn1 = new JButton("Button 1");

            // Initialization of object "jb2" of JButton class.
            jbtn2 = new JButton("Button 2");

            // Initialization of object "jb3" of JButton class.
            jbtn3 = new JButton("Button 3");

            // Initialization of object "jb4" of JButton class.
            jbtn4 = new JButton("Button 4");

            // Initialization of object "jb5" of JButton class.
            jbtn5 = new JButton("Button 5");

            // Adding JButton "jb1" on JFrame
            panel.add(jbtn1);

            // Adding JButton "jb2" on JFrame
            panel.add(jbtn2);

            // Adding JButton "jb3" on JFrame
            panel.add(jbtn3);

            // Adding JButton "jb4" on JFrame
            panel.add(jbtn4);

            // Adding JButton "jb5" on JFrame
            panel.add(jbtn5);

            // Function to set the panel  of JFrame.
            frame.add(panel);

            // Function to use the  pack of JFrame.
            frame.pack();

            // Function to set visible status of JFrame.
            frame.setVisible(true);
        }
    }
    ```

    **输出:**

    <video class="wp-video-shortcode" id="video-220262-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/Untitled-17.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/Untitled-17.mp4](https://media.geeksforgeeks.org/wp-content/uploads/Untitled-17.mp4)</video>

**注意:**上述程序可能无法在在线 IDE 中运行。请使用离线编译器。

**参考:**[https://docs . Oracle . com/javase/7/docs/API/javax/swing/box layout . html](https://docs.oracle.com/javase/7/docs/api/javax/swing/BoxLayout.html)