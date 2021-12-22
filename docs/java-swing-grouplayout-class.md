# Java Swing | GroupLayout 类

> 哎哎哎:# t0]https://www . geeksforgeeks . org/Java-swing-group layout-class/

组布局是一个布局管理器，它对组件进行分层分组，并将它们排列在一个容器中。分组是通过使用 Group 类的实例来完成的。它通常用于开发图形用户界面(图形用户界面)构建器，如网络豆集成开发环境提供的图形用户界面构建器马蒂斯。组布局类支持两种类型的组:

*   顺序组依次放置其子元素。
*   平行组以不同的方式对齐其子元素。

**该类的构造函数:**

*   **组布局(容器主机):**用于为指定的容器创建组布局。

**常用方法:**

1.  **添加组件(组件组件，对象组件):**通知组件已添加到父容器。
2.  **getHonorsVisibility():** 返回在调整组件大小和定位组件时是否考虑组件可见性。
3.  **最大尺寸(容器父级):**返回指定容器的最大尺寸。
4.  **getLayoutAlignmentX(沿水平轴):**返回沿 x 轴的对齐。
5.  **minimumLayoutSize(容器父级):**返回指定容器的最小大小。
6.  **getLayoutStyle():** 返回用于计算组件之间首选间隙的 LayoutStyle。

下面的程序说明了 GroupLayout 类的使用:

*   下面的程序通过在一个 *JFrame* 中排列 *JLabel* 组件来说明 GropuLayout 的使用，该 JFrame 的实例类是“*组布局*”。我们创建 2 个名为“ *headerLabel* ”、“ *statusLabel* ”的 JLabel 组件，并创建 3 个名为“*JButton*BTN 1”、“ *btn2* ”、“ *btn3* 的组件，然后使用 *add()* 方法将其添加到 JFrame 中。我们使用 *setSize()* 和 *setVisible()* 方法设置框架的大小和可见性。布局使用 *setLayout()* 方法设置。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate the GroupLayout class
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

// creating a class GroupLayoutDemo
public class GroupLayoutDemo {

    // Declaration of objects
    // of JFrame class
    private JFrame mainFrame;

    // Declaration of objects
    // of JLabel class
    private JLabel headerLabel, statusLabel, msglabel;

    // Declaration of objects
    // of JPanel class
    private JPanel controlPanel;

    // create a class GroupLayoutDemo
    public GroupLayoutDemo()
    {

        // used to prepare GUI
        prepareGUI();
    }

    public static void main(String[] args)
    {

        // Creating Object of "GroupLayoutDemo" class
        GroupLayoutDemo GroupLayoutDemo = new GroupLayoutDemo();

        // to show the group layout demo
        GroupLayoutDemo.showGroupLayoutDemo();
    }

    private void prepareGUI()
    {

        // Initialization of object
        // "mainframe" of JFrame class.
        mainFrame = new JFrame("Java GroupLayout Examples");

        // Function to set the
        // size of JFrame.
        mainFrame.setSize(400, 400);

        // Function to set the
        // layout of JFrame.
        mainFrame.setLayout(new GridLayout(3, 1));

        // Initialization of object
        // "headerLabel" of JLabel class.
        headerLabel = new JLabel("", JLabel.CENTER);

        // Initialization of object
        // "statusLabel" of JLabel class.
        statusLabel = new JLabel("", JLabel.CENTER);

        // Function to set the
        // size of JFrame.
        statusLabel.setSize(350, 100);

        // to add action WindowListner in JFrame
        mainFrame.addWindowListener(new WindowAdapter()
        {
            public void windowClosing(WindowEvent windowEvent)
            {
                System.exit(0);
            }
        });

        // Initialization of object
        // "controlPanel" of JPanel class.
        controlPanel = new JPanel();

        // Function to set the
        // layout of JFrame.
        controlPanel.setLayout(new FlowLayout());

        // Adding Jlabel "headerlabel"
        // on JFrame.
        mainFrame.add(headerLabel);

        // Adding JPanel "controlPanel"
        // on JFrame.
        mainFrame.add(controlPanel);

        // Adding JLabel "statusLabel"
        // on JFrame.
        mainFrame.add(statusLabel);

        // Function to set the visible of JFrame.
        mainFrame.setVisible(true);
    }

    private void showGroupLayoutDemo()
    {

        // Function to set the text
        // on the header of JFrame.
        headerLabel.setText("Layout in action: GroupLayout");

        // Creating Object of
        // "Panel" class
        JPanel panel = new JPanel();

        // Function to set the size of JFrame.
        panel.setSize(200, 200);

        // Creating Object of
        // "layout" class
        GroupLayout layout = new GroupLayout(panel);

        // it used to set Auto
        // Create Gaps
        layout.setAutoCreateGaps(true);

        // it used to set Auto
        // Create Container Gaps
        layout.setAutoCreateContainerGaps(true);

        // Creating Object
        // of "btn1" class
        JButton btn1 = new JButton("Button 1");

        // Creating Object of
        // "btn2" class
        JButton btn2 = new JButton("Button 2");

        // Creating Object of "btn3" class
        JButton btn3 = new JButton("Button 3");

        // It used to set the
        // Horizontal group
        layout.setHorizontalGroup(layout.createSequentialGroup()

        // Adding the JButton "btn1"
        .addComponent(btn1)

        // Adding the sequential Group
        .addGroup(layout.createSequentialGroup()

        // Adding the Parallel Group
        .addGroup(layout.createParallelGroup(GroupLayout.Alignment.LEADING)

        // Adding the JButton "btn2"
        .addComponent(btn2)

        // Adding the JButton "btn3"
        .addComponent(btn3))));

        // set the vertical layout group
        layout.setVerticalGroup(layout.createSequentialGroup()

        // Adding the JButton "btn1"
        .addComponent(btn1)

        // Adding the JButton "btn2"
        .addComponent(btn2)

        // Adding the JButton "btn3"
        .addComponent(btn3));

        // Function to set the Layout of JFrame.
        panel.setLayout(layout);

        // Adding the control panel
        controlPanel.add(panel);

        // Function to set the visible of JFrame.
        mainFrame.setVisible(true);
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-221751-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/Untitled-18.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/Untitled-18.mp4](https://media.geeksforgeeks.org/wp-content/uploads/Untitled-18.mp4)</video>

*   下面的程序通过在一个 *JFrame* 中排列 *JLabel* 组件来说明 GropuLayout 的使用，该 JFrame 的实例类是“ *GroupLayoutExample* ”。我们创建 1 *JLabel* 、1 *JTextField* 和 2 *JCheckbox* 组件。两个 *JButton* 组件也创建为“ *FindButton* ”、“ *CancelButton* ”，然后使用 add()方法将它们添加到 JFrame 中。布局使用 *setLayout()* 方法设置。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate the GroupLayout class
import java.awt.Component;
import javax.swing.*;
import static javax.swing.GroupLayout.Alignment.*;

// creating a class GroupLayoutExample
public class GroupLayoutExample {

    // Main Method
    public static void main(String[] args)
    {

        // Function to set the Default Look
        // And Feel Decorated of JFrame.
        JFrame.setDefaultLookAndFeelDecorated(true);

        // Creating Object of
        // "JFrame" class
        JFrame frame = new JFrame("GroupLayoutExample");

        // Function to set the Default
        // Close Operation of JFrame.
        frame.setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);

        // Creating Object of "JLabel" class
        JLabel label = new JLabel("Label:");

        // Creating Object of
        // "JTextField" class
        JTextField textField = new JTextField();

        // Creating Object of
        // "JCheckBox" class
        JCheckBox checkBox1 = new JCheckBox("CheckBox1");

        // Creating Object of "JCheckBox" class
        JCheckBox checkBox2 = new JCheckBox("CheckBox2");

        // Creating Object of "JButton" class
        JButton findButton = new JButton("Button 1");

        // Creating Object of "JButton" class
        JButton cancelButton = new JButton("Button 2");

        // used to set the Border of a checkBox1
        checkBox1.setBorder(BorderFactory.createEmptyBorder(0, 0,
                                                          0, 0));

        // used to set the Border of a checkBox2
        checkBox2.setBorder(BorderFactory.createEmptyBorder(0, 0,
                                                          0, 0));

        // Creating Object of "GroupLayout" class
        GroupLayout layout = new GroupLayout(frame.getContentPane());

        // to get the content pane
        frame.getContentPane().setLayout(layout);

        // it used to set Auto Create Gaps
        layout.setAutoCreateGaps(true);

        // it used to set Auto Create Container Gaps
        layout.setAutoCreateContainerGaps(true);

        // it used to set the horizontal group
        layout.setHorizontalGroup(layout.createSequentialGroup()

        // Adding the label
        .addComponent(label)

        // Adding the Parallel Group
        .addGroup(layout.createParallelGroup(LEADING)

        // Adding the textfield
        .addComponent(textField)

        // Adding the Sequential Group
        .addGroup(layout.createSequentialGroup()

        // Adding the Parallel Group
        .addGroup(layout.createParallelGroup(LEADING)

        // Adding the checkBox1
        .addComponent(checkBox1))

        // Adding the Parallel Group
        .addGroup(layout.createParallelGroup(LEADING)

        // Adding the checkBox2
        .addComponent(checkBox2))))

        // Adding the Parallel Group
        .addGroup(layout.createParallelGroup(LEADING)

        // Adding the findButton
        .addComponent(findButton)

        // Adding the CancelButton
        .addComponent(cancelButton)));

        layout.linkSize(SwingConstants.HORIZONTAL,
                        findButton, cancelButton);

        layout.setVerticalGroup(layout.createSequentialGroup()

        // Adding the Parallel Group
        .addGroup(layout.createParallelGroup(BASELINE)

        // Adding the label
        .addComponent(label)

        // Adding the textField
        .addComponent(textField)

        // Adding the findButton
        .addComponent(findButton))

        // Adding the Parallel Group
        .addGroup(layout.createParallelGroup(LEADING)

        // Adding the sequential Group
        .addGroup(layout.createSequentialGroup()

        // Adding the Parallel Group
        .addGroup(layout.createParallelGroup(BASELINE)

        // Adding the checkBox1
        .addComponent(checkBox1)

        // Adding the checkBox2
        .addComponent(checkBox2))

        // Adding the Parallel Group
        .addGroup(layout.createParallelGroup(BASELINE)))

        // Adding the CancelButton
        .addComponent(cancelButton)));

        frame.pack();
        frame.show();
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-221751-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/Untitled-19.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/Untitled-19.mp4](https://media.geeksforgeeks.org/wp-content/uploads/Untitled-19.mp4)</video>

**注意:**上述程序可能无法在在线 IDE 中运行。请使用离线编译器。
**参考:**[https://docs . Oracle . com/javase/7/docs/API/javax/swing/group layout . html](https://docs.oracle.com/javase/7/docs/api/javax/swing/GroupLayout.html)