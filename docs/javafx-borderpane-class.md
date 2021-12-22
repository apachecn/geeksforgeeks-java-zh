# JavaFX | BorderPane 类

> 原文:[https://www.geeksforgeeks.org/javafx-borderpane-class/](https://www.geeksforgeeks.org/javafx-borderpane-class/)

BorderPane 类是 JavaFX 的一部分。BorderPane 类将其子级放置在顶部、底部、中间、左侧和右侧位置。BorderPane 在五个位置布局每个子集合，而不管子集合的可见属性值是什么。BorderPane 类继承了 Pane 类。
**类的构造函数:**

1.  **边框()**:创建新的边框窗格。
2.  **边框面板(节点 c)** :创建一个以指定节点为中心的新边框窗格。
3.  **边框面板(节点中心、节点顶部、节点右侧、节点底部、节点左侧)**:使用给定的节点创建边框面板布局，用于边框窗格的每个主要布局区域。

**常用方法:**

<figure class="table">

| 方法 | 说明 |
| --- | --- |
| 对齐(节点 c) | 返回节点的对齐方式。 |
| getBottom() | 返回边框窗格的底部节点。 |
| getCenter() | 返回边框窗格的中心节点。 |
| getLeft（） | 返回边框窗格的左节点。 |
| 亮显() | 返回边框窗格的右节点。 |
| getTop（） | 返回边框窗格的顶部节点。 |
| 设置对齐(节点 c，位置 v) | 设置节点 c 与位置 v 的对齐方式。 |
| setBottom(节点 v) | 设置边框窗格的底部节点。 |
| setCenter(节点五) | 设置边框窗格的中心节点。 |
| setLeft(节点五) | 设置边框窗格的左节点。 |
| 设置右侧(节点五) | 设置边框窗格的右节点。 |
| 设置点(节点五) | 设置边框窗格的顶部节点。 |

</figure>

下面的程序说明了 BorderPane 类的使用:

1.  **Java 程序创建一个 BorderPane 并将其添加到舞台:**在这个程序中我们创建一个名为*的标签*。现在创建一个名为*的 borderpane* 。我们将把这个标签添加到 BorderPane 布局的中心。将边框窗格添加到场景，并将此场景添加到舞台，并显示舞台以显示最终结果。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to create a BorderPane
// and add it to the stage
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.*;
import javafx.scene.layout.*;
import javafx.stage.Stage;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.canvas.*;
import javafx.scene.web.*;
import javafx.scene.layout.BorderPane;
import javafx.scene.shape.*;

public class BorderPane_1 extends Application {

    // launch the application
    public void start(Stage stage)
    {

        try {

            // set title for the stage
            stage.setTitle("BorderPane");

            // create a label
            Label label = new Label("this is BorderPane example");

            // create a BorderPane
            BorderPane border_pane = new BorderPane(label);

            // create a scene
            Scene scene = new Scene(border_pane, 400, 300);

            // set the scene
            stage.setScene(scene);

            stage.show();
        }

        catch (Exception e) {

            System.out.println(e.getMessage());
        }
    }

    // Main Method
    public static void main(String args[])
    {

        // launch the application
        launch(args);
    }
}
```