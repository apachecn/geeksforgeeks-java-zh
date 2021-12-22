# Java AWT | CardLayout 类

> 原文:[https://www.geeksforgeeks.org/java-awt-cardlayout-class/](https://www.geeksforgeeks.org/java-awt-cardlayout-class/)

CardLayout 类以一次只能看到一个组件的方式管理组件。它将每个组件视为容器中的一张卡片。一次只能看到一张卡片，容器充当一叠卡片。添加到*卡片布局*对象的第一个组件是首次显示容器时的可见组件。

**施工人员:**

1.  **卡片布局():**用于创建一个间隙大小为零的新卡片布局。
2.  **卡片布局(int horizontalgap，int verticalgap):** 用于创建具有指定水平和垂直间隙的新卡片布局类。

**常用方法:**

*   **getLayoutAlignmentX(容器父级):**返回沿 x 轴的对齐方式。
*   **getLayoutAlignmentY(容器父级):**返回沿 y 轴的对齐方式。
*   **getVgap():** 用于获取组件之间的垂直间隙。
*   **添加组件(组件 cm，对象 cn):** 用于将指定的组件添加到该卡布局的内部名称表中。
*   **getHgap():** 用于获取组件之间的水平间隙。
*   **toString():** 返回此卡片布局状态的字符串表示。
*   **移除布局组件(组件 cm):** 用于从布局中移除指定的组件。

下面的程序说明了卡片布局类:

*   **程序 1:** 在下面的程序中，我们在一个 *JFrame* 中安排了几个 *JLabel* 组件，其实例类为“ *Cardlayout* ”。我们创建 3 个名为“ *bt1* ”、“ *bt2* ”、“ *bt3* ”的【JButton】组件，然后使用 *add()* 方法将其添加到 *JFrame* 中。我们通过*设置大小()*和*设置可见()*的方法设置框架的大小和可见性。布局通过*方法设置布局()*方法设置。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate the CardLayout Class
import java.awt.*;
import java.awt.event.*;
import javax.swing.JFrame;
import javax.swing.*;

// class extends JFrame and implements actionlistener
public class Cardlayout extends JFrame implements ActionListener {

    // Declaration of objects of CardLayout class.
    CardLayout card;

    // Declaration of objects of JButton class.
    JButton b1, b2, b3;

    // Declaration of objects
    // of Container class.
    Container c;

    Cardlayout()
    {

        // to get the content
        c = getContentPane();

        // Initialization of object "card"
        // of CardLayout class with 40
        // horizontal space and 30 vertical space .
        card = new CardLayout(40, 30);

        // set the layout
        c.setLayout(card);

        // Initialization of object "b1" of JButton class.
        b1 = new JButton("GEEKS");

        // Initialization of object "b2" of JButton class.
        b2 = new JButton("FOR");

        // Initialization of object "b3" of JButton class.
        b3 = new JButton("GEEKS");

        // this Keyword refers to current object.
        // Adding Jbutton "b1" on JFrame using ActionListener.
        b1.addActionListener(this);

        // Adding Jbutton "b2" on JFrame using ActionListener.
        b2.addActionListener(this);

        // Adding Jbutton "b3" on JFrame using ActionListener.
        b3.addActionListener(this);

        // Adding the JButton "b1"
        c.add("a", b1);

        // Adding the JButton "b2"
        c.add("b", b2);

        // Adding the JButton "b1"
        c.add("c", b3);
    }

    public void actionPerformed(ActionEvent e)
    {

        // call the next card
        card.next(c);
    }

    // Main Method
    public static void main(String[] args)
    {

        // Creating Object of CardLayout class.
        Cardlayout cl = new Cardlayout();

        // Function to set size of JFrame.
        cl.setSize(400, 400);

        // Function to set visibility of JFrame.
        cl.setVisible(true);

        // Function to set default operation of JFrame.
        cl.setDefaultCloseOperation(EXIT_ON_CLOSE);
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-218780-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/CardLayout-1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/CardLayout-1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/CardLayout-1.mp4)</video>

*   **程序 2:** 在下面的程序中，我们正在一个 *JFrame* 中排列 4 个 *JLabel* 组件，其类为“*cardlayoutemo*”。我们创建了名为“ *firstbtn* ”、“ *nextbtn* ”、“ *previousbtn* ”、“ *lastbtn* ”的 4 个 *JLabel* 名为“ *jl1* ”、“ *jl2* ”、“*JL 3*”*的组件这里我们还创建了 4 个名为“ *jp1* ”、“ *jp2* ”、“ *jp3* ”、“ *jp4* 的组件，然后使用 *add()* 方法将其添加到 *JFrame* 中。我们将分别使用 *setSize()* 、 *setVisible()* 和 *setTitle()* 方法设置框架的大小、可见性和标题。布局使用 *setLayout()* 方法设置。*

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to show Example of CardLayout.
// in java. Importing different Package.
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import javax.swing.*;

// class extends JFrame
public class CardLayoutDemo extends JFrame {

    // Initialization the value of
    // current card is 1 .
    private int currentCard = 1;

    // Declaration of objects
    // of CardLayout class.
    private CardLayout cl;

    public CardLayoutDemo()
    {

        // Function to set visibility of JFrame
        setTitle("Card Layout Example");

        // Function to set visibility of JFrame
        setSize(300, 150);

        // Creating Object of "Jpanel" class
        JPanel cardPanel = new JPanel();

        // Initialization of object "c1"
        // of CardLayout class.
        cl = new CardLayout();

        // set the layout
        cardPanel.setLayout(cl);

        // Initialization of object
        // "jp1" of JPanel class.
        JPanel jp1 = new JPanel();

        // Initialization of object
        // "jp2" of CardLayout class.
        JPanel jp2 = new JPanel();

        // Initialization of object
        // "jp3" of CardLayout class.
        JPanel jp3 = new JPanel();

        // Initialization of object
        // "jp4" of CardLayout class.
        JPanel jp4 = new JPanel();

        // Initialization of object
        // "jl1" of JLabel class.
        JLabel jl1 = new JLabel("Card1");

        // Initialization of object
        // "jl2" of JLabel class.
        JLabel jl2 = new JLabel("Card2");

        // Initialization of object
        // "jl3" of JLabel class.
        JLabel jl3 = new JLabel("Card3");

        // Initialization of object
        // "jl4" of JLabel class.
        JLabel jl4 = new JLabel("Card4");

        // Adding JPanel "jp1" on JFrame.
        jp1.add(jl1);

        // Adding JPanel "jp2" on JFrame.
        jp2.add(jl2);

        // Adding JPanel "jp3" on JFrame.
        jp3.add(jl3);

        // Adding JPanel "jp4" on JFrame.
        jp4.add(jl4);

        // Adding the cardPanel on "jp1"
        cardPanel.add(jp1, "1");

        // Adding the cardPanel on "jp2"
        cardPanel.add(jp2, "2");

        // Adding the cardPanel on "jp3"
        cardPanel.add(jp3, "3");

        // Adding the cardPanel on "jp4"
        cardPanel.add(jp4, "4");

        // Creating Object of "JPanel" class
        JPanel buttonPanel = new JPanel();

        // Initialization of object
        // "firstbtn" of JButton class.
        JButton firstBtn = new JButton("First");

        // Initialization of object
        // "nextbtn" of JButton class.
        JButton nextBtn = new JButton("Next");

        // Initialization of object
        // "previousbtn" of JButton class.
        JButton previousBtn = new JButton("Previous");

        // Initialization of object
        // "lastbtn" of JButton class.
        JButton lastBtn = new JButton("Last");

        // Adding JButton "firstbtn" on JFrame.
        buttonPanel.add(firstBtn);

        // Adding JButton "nextbtn" on JFrame.
        buttonPanel.add(nextBtn);

        // Adding JButton "previousbtn" on JFrame.
        buttonPanel.add(previousBtn);

        // Adding JButton "lastbtn" on JFrame.
        buttonPanel.add(lastBtn);

        // add firstbtn in ActionListener
        firstBtn.addActionListener(new ActionListener()
        {
            public void actionPerformed(ActionEvent arg0)
            {

                // used first c1 CardLayout
                cl.first(cardPanel);

                // value of currentcard is 1
                currentCard = 1;
            }
        });

        // add lastbtn in ActionListener
        lastBtn.addActionListener(new ActionListener()
        {
            public void actionPerformed(ActionEvent arg0)
            {

                // used last c1 CardLayout
                cl.last(cardPanel);

                // value of currentcard is 4
                currentCard = 4;
            }
        });

        // add nextbtn in ActionListener
        nextBtn.addActionListener(new ActionListener()
        {
            public void actionPerformed(ActionEvent arg0)
            {

                // if condition apply
                if (currentCard < 4)
                {

                    // increment the value of currentcard by 1
                    currentCard += 1;

                    // show the value of currentcard
                    cl.show(cardPanel, "" + (currentCard));
                }
            }
        });

        // add previousbtn in ActionListener
        previousBtn.addActionListener(new ActionListener()
        {
            public void actionPerformed(ActionEvent arg0)
            {
                // if condition apply
                if (currentCard > 1) {

                    // decrement the value
                    // of currentcard by 1
                    currentCard -= 1;

                    // show the value of currentcard
                    cl.show(cardPanel, "" + (currentCard));
                }
            }
        });

        // used to get content pane
        getContentPane().add(cardPanel, BorderLayout.NORTH);

        // used to get content pane
        getContentPane().add(buttonPanel, BorderLayout.SOUTH);
    }

    // Main Method
    public static void main(String[] args)
    {

        // Creating Object of CardLayoutDemo class.
        CardLayoutDemo cl = new CardLayoutDemo();

        // Function to set default operation of JFrame.
        cl.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        // Function to set visibility of JFrame.
        cl.setVisible(true);
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-218780-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/CardLayout-2.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/CardLayout-2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/CardLayout-2.mp4)</video>

**注意:**上述程序可能无法在在线 IDE 中运行。请使用离线编译器。

**参考:**T2T4】