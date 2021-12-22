# Java Swing | JToggleButton 类

> 原文:[https://www . geesforgeks . org/Java-swing-jtogglebutton-class/](https://www.geeksforgeeks.org/java-swing-jtogglebutton-class/)

JToggleButton 是一个双态按钮。这两种状态被选中和取消选中。 *JRadioButton* 和 *JCheckBox* 类是这个类的子类。当用户按下切换按钮时，它会在按下或未按下之间切换。JToggleButton 用于从可能的选项列表中选择一个选项。按钮可以通过操作进行配置，并在一定程度上受到控制。将操作与按钮结合使用，除了直接配置按钮之外，还有许多好处。

**JToggleButton 中的构造函数:**

1.  **JToggleButton():** 在不设置文本或图像的情况下创建最初未选择的切换按钮。
2.  **JToggleButton(动作 a):** 创建一个切换按钮，从提供的动作中获取属性。
3.  **JToggleButton(图标图标):**用指定的图像创建一个最初未选择的切换按钮，但没有文本。
4.  **JToggleButton(Icon icon，boolean selected):** 创建具有指定图像和选择状态的切换按钮，但没有文本。
5.  **JToggleButton(字符串文本):**用指定的文本创建一个未选中的切换按钮。
6.  **JToggleButton(字符串文本，布尔选定):**创建具有指定文本和选择状态的切换按钮。
7.  **JToggleButton(字符串文本，图标图标):**创建具有指定文本和图像的切换按钮，该按钮最初未被选中。
8.  **JToggleButton(字符串文本、图标图标、布尔选定):**创建具有指定文本、图像和选择状态的切换按钮。

**常用方法:**

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| getAccessibleContext() | 获取与此 JToggleButton 关联的 AccessibleContext。 |
| getUIClassID() | 返回一个字符串，该字符串指定呈现此组件的 l&f 类的名称。 |
| paramString() | 返回此 JToggleButton 的字符串表示形式。 |
| updateUI() | 将用户界面属性重置为当前外观的值。 |

</figure>

下面的程序说明了 JToggleButton 类:

**1。用项目侦听器实现 JToggleButton 事件的 Java 程序:**在这个程序中，我们使用 *JFrame()* 创建框架。这里，*设置默认关闭操作()*用于设置框架的关闭选项。使用 *JToggleButton()* 创建一个按钮。实例化*项目监听器*，它只包含*项目状态改变()*方法，当点击按钮时自动调用。事件在按钮上生成，相应地，输出被打印到控制台。附加所有监听器，并在按钮上添加*项目监听器*。向框架添加按钮并设置框架的大小。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.awt.BorderLayout;
import java.awt.event.ItemEvent;
import java.awt.event.ItemListener;
import javax.swing.JFrame;
import javax.swing.JToggleButton;

public class JToggleButtonExamp {

    // Main Method
    public static void main(String args[])
    {

        // create a frame and set title
        JFrame frame = new JFrame("Selecting Toggle");

        // set the default close operation of the frame
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        // create a ToggleButton
        JToggleButton toggleButton = new JToggleButton("Toggle Button");

        // ItemListener is notified whenever you click on the Button
        ItemListener itemListener = new ItemListener() {

            // itemStateChanged() method is nvoked automatically
            // whenever you click or unlick on the Button.
            public void itemStateChanged(ItemEvent itemEvent)
            {

                // event is generated in button
                int state = itemEvent.getStateChange();

                // if selected print selected in console
                if (state == ItemEvent.SELECTED) {
                    System.out.println("Selected");
                }
                else {

                    // else print deselected in console
                    System.out.println("Deselected");
                }
            }
        };

        // Attach Listeners
        toggleButton.addItemListener(itemListener);
        frame.add(toggleButton, BorderLayout.NORTH);
        frame.setSize(300, 125);
        frame.setVisible(true);
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-221558-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20180826_023018.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20180826_023018.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20180826_023018.mp4)</video>

**2。使用 ActionListener 实现 JToggleButton 事件的 Java 程序:**这里，在 JFrame 上创建了一个 JToggleButton。然后，我们定义 ActionListener。 *actionPerformed()* 是 *ActionListener()* 中唯一的方法，只要点击注册的组件就会被调用。 *abstractButton.getModel()。如果选择了按钮，isSelected()* 返回 true，否则返回 false。将监听器连接到跳转按钮。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.awt.BorderLayout;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import javax.swing.AbstractButton;
import javax.swing.JFrame;
import javax.swing.JToggleButton;

public class JToggleButtonExamp {

    // Main Method
    public static void main(String args[])
    {

        // create the JFrame
        JFrame frame = new JFrame("Selecting Toggle");

        // set default close operation for frame
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        // create a ToggleButton
        JToggleButton toggleButton = new JToggleButton("Toggle Button");

        // Define ActionListener

        ActionListener actionListener = new ActionListener()
        {

            // actionPerformed() method is invoked
            // automatically whenever you click on
            // registered component
            public void actionPerformed(ActionEvent actionEvent)
            {

                AbstractButton abstractButton =
                (AbstractButton)actionEvent.getSource();

                // return true or false according
                // to the selection or deselection
                // of the button
                boolean selected = abstractButton.getModel().isSelected();

                System.out.println("Action - selected=" + selected + "\n");
            }
          };
        // Attach Listeners
        toggleButton.addActionListener(actionListener);

        // add ToggleButton to the frame
        frame.add(toggleButton, BorderLayout.NORTH);

        // set size of the frame
        frame.setSize(300, 125);

        frame.setVisible(true);
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-221558-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20180826_031430.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20180826_031430.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20180826_031430.mp4)</video>

**注意:**上述程序可能无法在在线 IDE 中运行。请使用离线编译器。

**参考:**[https://docs . Oracle . com/javase/7/docs/API/javax/swing/jtogglebutton . html](https://docs.oracle.com/javase/7/docs/api/javax/swing/JToggleButton.html)