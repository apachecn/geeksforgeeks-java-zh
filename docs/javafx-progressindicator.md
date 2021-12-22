# JavaFX |进步指示器

> 原文:[https://www.geeksforgeeks.org/javafx-progressindicator/](https://www.geeksforgeeks.org/javafx-progressindicator/)

ProgressIndicator 是 JavaFX 包的一部分。这是一个循环控件，用于指示进度，可以是无限的，也可以是有限的。通常与任务应用编程接口一起用于表示后台任务的进度。它通常显示任务的完成量。

**该类的构造函数为**

1.  **进度指示器()**:创建一个新的中间进度指示器。
2.  **进度指示器(双 p)** :创建具有指定进度的进度指示器

**常用方法**

| 方法 | 说明 |
| --- | --- |
| **Isincrement()** | 获取不确定属性的值。 |
| **获取进展（）** | 获取属性进度的值。 |
| **设定程序(双 v)** | 设置属性进度的值 |

以下程序说明了进度指示器的使用:

**创建进度指示器的程序:**该程序创建由名称 *pb* 指示的进度指示器。进度指示器将在场景中创建，而场景又将托管在舞台中。函数 setTitle()用于为舞台提供标题。然后创建一个平铺窗格，在该窗格上调用 addChildren()方法来附加进度指示器和场景内的按钮。最后调用 show()方法显示最终结果。

```
// Java program to illustrate the use of Progress Indicator
import javafx.application.Application;
import javafx.scene.Scene;
import javafx.scene.control.*;
import javafx.scene.layout.*;
import java.io.*;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.control.Label;
import javafx.stage.Stage;
import java.net.*;
public class progressi extends Application {

    static double ii = 0;

    // launch the application
    public void start(Stage s) throws Exception
    {
        // set title for the stage
        s.setTitle("creating progressIndicator");

        // create a progress indicator
        ProgressIndicator pb = new ProgressIndicator();

        // create a tile pane
        TilePane r = new TilePane();

        // action event
        EventHandler<ActionEvent> event = new EventHandler<ActionEvent>() {
            public void handle(ActionEvent e)
            {
                // set progress to different level of progressindicator
                ii += 0.1;
                pb.setProgress(ii);
            }

        };

        // creating button
        Button b = new Button("increase");

        // set on action
        b.setOnAction(event);

        // add button
        r.getChildren().add(pb);
        r.getChildren().add(b);

        // create a scene
        Scene sc = new Scene(r, 200, 200);

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

**输出:**
![](img/17e412a42309e53af53abc02b3cf8839.png)

![](img/160b54c6e005cba95274e4f6212f41ff.png)

![](img/1ded14709b0c88f4e8ac40e5d735034b.png)

**注意**:以下程序可能无法在联机 IDE 中运行，请使用脱机编译器。
**参考:**[https://docs . Oracle . com/javase/8/JavaFX/API/JavaFX/scene/control/progressionedicator . html](https://docs.oracle.com/javase/8/javafx/api/javafx/scene/control/ProgressIndicator.html)