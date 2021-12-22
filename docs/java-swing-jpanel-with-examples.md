# Java Swing–JPanel 示例

> 原文:[https://www . geesforgeks . org/Java-swing-jpanel-with-examples/](https://www.geeksforgeeks.org/java-swing-jpanel-with-examples/)

JPanel 是 [Java Swing 包](https://www.geeksforgeeks.org/difference-between-awt-and-swing-in-java/)的一部分，是一个可以存储一组组件的容器。JPanel 的主要任务是组织组件，可以在 JPanel 中设置各种布局来更好地组织组件，但是它没有标题栏。

### **JPanel**的构造函数

1.  **JPanel()** :使用流程布局创建新面板
2.  **JPanel(LayoutManager l)** :用指定的 LayoutManager 创建一个新的 JPanel
3.  **JPanel(boolean is doublebuffered)**:用指定的缓冲策略创建一个新的 JPanel
4.  **JPanel(LayoutManager l，boolean is doublebuffed)**:使用指定的 LayoutManager 和指定的缓冲策略创建一个新的 JPanel

### **JPanel 常用功能**

1.  **添加(组件 c)** :向指定容器添加组件
2.  **设置布局(LayoutManager l)** :将容器的布局设置为指定的布局管理器
3.  **updateUI()** :用当前观感的值重置 UI 属性。
4.  **setUI(panel ui)**:设置渲染此组件的对象的外观和感觉。
5.  **getUI()** :返回渲染此组件的观感对象。
6.  **ParaString()**:返回此 JPanel 的字符串表示形式。
7.  **getUIClassID()** :返回渲染此组件的外观类的名称。
8.  **getAccessibleContext()** :获取与此 JPanel 关联的 AccessibleContext。

让我们以一个示例程序为例，通过附加输出的顺序执行快照来说明 JPanel 类的使用，如下所示:

**例:**

## 爪哇

```java
// Java Program to Create a Simple JPanel
// and Adding Components to it

// Importing required classes
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;

// Class 1
// Helper class extending JFrame class
class solution extends JFrame {

    // JFrame
    static JFrame f;

    // JButton
    static JButton b, b1, b2;

    // Label to display text
    static JLabel l;

    // Main class
    public static void main(String[] args)
    {
        // Creating a new frame to store text field and
        // button
        f = new JFrame("panel");

        // Creating a label to display text
        l = new JLabel("panel label");

        // Creating a new buttons
        b = new JButton("button1");
        b1 = new JButton("button2");
        b2 = new JButton("button3");

        // Creating a panel to add buttons
        JPanel p = new JPanel();

        // Adding buttons and textfield to panel
        // using add() method
        p.add(b);
        p.add(b1);
        p.add(b2);
        p.add(l);

        // setbackground of panel
        p.setBackground(Color.red);

        // Adding panel to frame
        f.add(p);

        // Setting the size of frame
        f.setSize(300, 300);

        f.show();
    }
}
```