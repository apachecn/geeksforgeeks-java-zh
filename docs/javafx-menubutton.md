# JavaFX |菜单按钮

> 原文:[https://www.geeksforgeeks.org/javafx-menubutton/](https://www.geeksforgeeks.org/javafx-menubutton/)

MenuButton 是 JavaFX 库的一部分。当按下菜单按钮时，显示一个显示一组项目的上下文菜单，用户可以选择任何项目。它通常包含几个菜单项，用户一次最多只能选择一个菜单项。
**菜单按钮类的构造函数有:**

1.  **菜单按钮()**:创建新的菜单按钮
2.  **菜单按钮(字符串 t)** :创建带有指定文本的菜单按钮
3.  **菜单按钮(字符串 t，节点 g)** :创建带有指定文本
    和图形的菜单按钮
4.  **菜单按钮(字符串 t，节点 g，菜单元素… i)** 创建一个带有指定文本、图形和菜单元素的菜单按钮

**常用方法:**

<figure class="table">

| 方法 | 说明 |
| --- | --- |
| **【getitem()** | 返回菜单按钮的项目 |
| **【get populapside()** | 获取属性弹出端的值 |
| **隐藏()** | 隐藏上下文菜单 |
| **isShowing()** | 获取显示的属性的值。 |
| **设定上坡(v 侧)** | 设置 popupSide 属性的值。 |
| **显示()** | 显示上下文菜单 |

</figure>

下面的程序说明了菜单按钮类:

*   **创建菜单按钮并向其添加菜单按钮的程序**:将创建一个名为 m 的菜单按钮，并将向菜单按钮 m 添加 3 个菜单 m1、m2、m3。菜单将在场景中创建，场景又将托管在舞台中。函数 setTitle()用于为舞台提供标题。然后创建一个 tilepane，在这个 tile pane 上调用 addChildren()方法将 menubutton 附加到场景内部。最后，调用 show()方法显示最终结果。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Program to create a menubutton and add menuitems to it
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.*;
import javafx.scene.layout.*;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.collections.*;
import javafx.stage.Stage;
import javafx.scene.text.Text.*;
import javafx.scene.paint.*;
import javafx.scene.text.*;
public class MenuButton_1 extends Application {
    // labels
    Label l;

    // launch the application
    public void start(Stage s)
    {
        // set title for the stage
        s.setTitle("creating MenuButton ");

        // create a tile pane
        TilePane r = new TilePane();

        // create a label
        Label l1 = new Label("This is a MenuButton example ");

        // create a menu button
        MenuButton m = new MenuButton("menuButton");

        // create menuitems
        MenuItem m1 = new MenuItem("menu item 1");
        MenuItem m2 = new MenuItem("menu item 2");
        MenuItem m3 = new MenuItem("menu item 3");

        // add menu items to menu
        m.getItems().add(m1);
        m.getItems().add(m2);
        m.getItems().add(m3);

        // create a tilepane
        TilePane vb = new TilePane(l1, m);

        // create a scene
        Scene sc = new Scene(vb, 200, 200);

        // set the scene
        s.setScene(sc);

        s.show();
    }

    public static void main(String args[])
    {
        // launch the application
        launch(args);
    }
}
```