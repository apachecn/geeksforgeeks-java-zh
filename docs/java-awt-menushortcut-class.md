# Java AWT | menushotcut 类

> 原文:[https://www.geeksforgeeks.org/java-awt-menushortcut-class/](https://www.geeksforgeeks.org/java-awt-menushortcut-class/)

MenuShortcut 类是 JavaAWT 的一部分。MenuShortcut 类实现了使用虚拟键码实现的菜单快捷方式。MenuShortcut 类表示 MenuItem 的键盘加速器。

**类的构造函数:**

1.  **菜单快捷键(int k)** :用指定的键创建一个菜单快捷键对象。
2.  **menushotcut(int k，boolean b)** :为指定的虚拟键码构造一个新的 menushotcut。

**常用方法:**

| 方法 | 说明 |
| --- | --- |
| 等于(菜单快捷方式) | 返回此菜单快捷方式是否与另一个菜单快捷方式相同。 |
| getKey() | 返回此菜单快捷方式的原始键码。 |
| hashCode() | 返回 MenuShortcut 的 hashcode。 |
| usesShiftModifier() | 返回是否必须使用 SHIFT 键调用此菜单快捷方式。 |

下面的程序说明了菜单快捷方式类:

1.  **Java program to create a menubar and add MenuItems to it and also add MenuShortcut to MenuItems:** In this program we will create a Frame named *frame*, MenuBar named *menubar*, a Menu named *menu* and three MenuItems named *menuitem_1*, *menuitem_2*, *menuitem_3*. We will also create three MenuShortcut named *menushortcut_1*, *menushortcut_2*, *menushortcut_3* and specify their key to ‘A’, ‘B’, ‘C’. When *ctrl+A* will be pressed *menuitem_1* will be invoked. Similarly, when *ctrl+B*, *ctrl+C* will be pressed then *menuitem_2*, *menuitem_3* will be invoked respectively. ActionListener will be added to all the menuitems and a label will display which MenuItem is clicked. The MenuItems will be added to the menu the menu will be added to the menubar and the menubar and label will be added to the frame and the size of the frame will be set to the specified value and the show function will display the results.

    ## Java 语言(一种计算机语言，尤用于创建网站)

    ```
    // Java program to create a menubar and add
    // menuitems to it and also add menushortcut
    // to MenuItems
    import java.awt.*;
    import javax.swing.*;
    import java.awt.event.*;

    public class Shortcut_1 extends 
    Frame implements ActionListener {

        // menubar
        static MenuBar menubar;

        // Menu
        static Menu menu;

        // Menu items
        static MenuItem menuitem_1, menuitem_2, menuitem_3;

        // create a frame
        static Frame frame;

        // create label
        Label label;

        // default constructor
        Shortcut_1()
        {

            // create a frame
            frame = new Frame("MenuShortcut Demo");

            // when exit button is pressed
            frame.addWindowListener(new WindowAdapter() {

                public void windowClosing(WindowEvent windowEvent)
                {
                    System.exit(0);
                }
            });

            // create a menubar
            menubar = new MenuBar();

            // create a menu
            menu = new Menu("Menu");

            // create label
            label = new Label("Nothing Selected");

            // create menu shortcuts
            MenuShortcut menushortcut_1 = 
            new MenuShortcut(KeyEvent.VK_A, false);

            MenuShortcut menushortcut_2 = 
            new MenuShortcut(KeyEvent.VK_B, false);

            MenuShortcut menushortcut_3 = 
            new MenuShortcut(KeyEvent.VK_C, false);

            // create menuitems
            menuitem_1 = new MenuItem("MenuItem_1 ", menushortcut_1);
            menuitem_2 = new MenuItem("MenuItem_2 ", menushortcut_2);
            menuitem_3 = new MenuItem("MenuItem_3 ", menushortcut_3);

            // add ActionListener to menuItems
            menuitem_1.addActionListener(this);
            menuitem_2.addActionListener(this);
            menuitem_3.addActionListener(this);

            // add menu items to menu
            menu.add(menuitem_1);
            menu.add(menuitem_2);
            menu.add(menuitem_3);

            // add menu to menu bar
            menubar.add(menu);

            // add menubar to frame
            frame.setMenuBar(menubar);

            // add label
            frame.add(label);

            // set the size of the frame
            frame.setSize(500, 500);
            frame.setVisible(true);
        }

        // when an action is performed
        public void actionPerformed(ActionEvent e)
        {
            String s = e.getActionCommand();

            // set the label to the menuItem
            // that is selected
            label.setText(s + " selected");
        }

        // Main Method
        public static void main(String args[])
        {

            // create an object
            Shortcut_1 m = new Shortcut_1();
        }
    }
    ```

    **输出:**

    <video class="wp-video-shortcode" id="video-222188-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/S-1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/cdn-uploads/S-1.mp4](https://media.geeksforgeeks.org/wp-content/cdn-uploads/S-1.mp4)</video>
2.  **Java program to create a menubar and add MenuItems to it and also add MenuShortcut to MenuItems and also add shift modifier to MenuShortcut:** In this program we will create a Frame named *frame*, MenuBar named *menubar*, a Menu named menu and three MenuItems named *menuitem_1*, *menuitem_2*, *menuitem_3*. We will also create three MenuShortcut named *menushortcut_1*, *menushortcut_2*, *menushortcut_3* and specify their key to ‘A’, ‘B’, ‘C’ and the shift modifier will be set to true. When *ctrl+shift+A* will be pressed menuitem_1 will be invoked. Similarly, when *ctrl+shift+B*, *ctrl+shift+C* will be pressed *menuitem_2*, *menuitem_3* will be invoked respectively. ActionListener will be added to all the Menu Items and a label will display which MenuItem is clicked. The MenuItems will be added to the menu and the menu will be added to the menubar and the menubar and label will be added to the frame and the size of the frame will be set to the specified value and the show function will display the results.

    ## Java 语言(一种计算机语言，尤用于创建网站)

    ```
    // Java program to create a menubar and add 
    // menuitems to it and also add menushortcut 
    // to MenuItems and also add shift modifier
    // to MenuShortcut
    import java.awt.*;
    import javax.swing.*;
    import java.awt.event.*;

    public class Shortcut_2 extends Frame 
              implements ActionListener {

        // menubar
        static MenuBar menubar;

        // Menu
        static Menu menu;

        // Menu items
        static MenuItem menuitem_1, menuitem_2, menuitem_3;

        // create a frame
        static Frame frame;

        // create label
        Label label;

        // default constructor
        Shortcut_2()
        {
            // create a frame
            frame = new Frame("MenuShortcut Demo");

            // when exit button is pressed
            frame.addWindowListener(new WindowAdapter() {

                public void windowClosing(WindowEvent windowEvent)
                {
                    System.exit(0);
                }
            });

            // create a menubar
            menubar = new MenuBar();

            // create a menu
            menu = new Menu("Menu");

            // create label
            label = new Label("Nothing Selected");

            // create menu shortcuts
            MenuShortcut menushortcut_1 = 
            new MenuShortcut(KeyEvent.VK_A, true);

            MenuShortcut menushortcut_2 = 
            new MenuShortcut(KeyEvent.VK_B, true);

            MenuShortcut menushortcut_3 = 
            new MenuShortcut(KeyEvent.VK_C, true);

            // create menuitems
            menuitem_1 = new MenuItem("MenuItem_1 ", 
                                    menushortcut_1);

            menuitem_2 = new MenuItem("MenuItem_2 ",
                                    menushortcut_2);

            menuitem_3 = new MenuItem("MenuItem_3 ", 
                                    menushortcut_3);

            // add ActionListener to menuItems
            menuitem_1.addActionListener(this);
            menuitem_2.addActionListener(this);
            menuitem_3.addActionListener(this);

            // add menu items to menu
            menu.add(menuitem_1);
            menu.add(menuitem_2);
            menu.add(menuitem_3);

            // add menu to menu bar
            menubar.add(menu);

            // add menubar to frame
            frame.setMenuBar(menubar);

            // add label
            frame.add(label);

            // set the size of the frame
            frame.setSize(500, 500);
            frame.setVisible(true);
        }

        // when an action is performed
        public void actionPerformed(ActionEvent e)
        {
            String s = e.getActionCommand();

            // set the label to the MenuItem,
            // that is selected
            label.setText(s + " selected");
        }

        // Main Function
        public static void main(String args[])
        {

            // create an object
            Shortcut_2 m = new Shortcut_2();
        }
    }
    ```

    **输出:**

    <video class="wp-video-shortcode" id="video-222188-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/S-2.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/cdn-uploads/S-2.mp4](https://media.geeksforgeeks.org/wp-content/cdn-uploads/S-2.mp4)</video>

**注意:**上述程序可能无法在在线 IDE 中运行。请使用离线编译器。

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/awt/menushotcut . html](https://docs.oracle.com/javase/7/docs/api/java/awt/MenuShortcut.html)