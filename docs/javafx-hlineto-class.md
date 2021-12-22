# JavaFX | HLineTo 类

> 原文:[https://www.geeksforgeeks.org/javafx-hlineto-class/](https://www.geeksforgeeks.org/javafx-hlineto-class/)

HLineTo 类是 JavaFX 的一部分。类创建一条从当前位置到指定 x 坐标的水平线。HLineTo 类继承了 PathElement 类。

**该类的构造函数:**

1.  **HLineTo()** :创建 HLineTo 的空对象。
2.  **HLineTo(双 x)** :创建一个具有指定 x 坐标值的 HLineTo 对象。

**常用方法:**

| 方法 | 说明 |
| --- | --- |
| getX（） | 返回 x 坐标的值。 |
| setX(双 v) | 设置 x 坐标的值。 |
| toString() | 返回 HLineTo 对象的字符串表示形式。 |
| xProperty() | 定义 X 坐标。 |

以下程序说明了 HLineTo 类的使用:

*   **Java program to create a path and add HLineTo to it and display it:**
    1.  在这个程序中，我们将创建一个名为 path 的 Path 对象。
    2.  用指定的 X 坐标创建一个 HLineTo 对象。
    3.  然后创建一个名为*移动到*的移动到对象。
    4.  现在将移动到和线到对象添加到路径中。
    5.  将此路径添加到 group 对象并将 Group 对象添加到场景并将场景添加到舞台并调用 *show()* 函数显示最终结果。

    ```java
    // Java program to create a path
    // and add HLineTo to it and display it
    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.*;
    import javafx.scene.layout.*;
    import javafx.stage.Stage;
    import javafx.scene.layout.*;
    import javafx.scene.paint.*;
    import javafx.scene.text.*;
    import javafx.geometry.*;
    import javafx.scene.layout.*;
    import javafx.scene.shape.*;
    import javafx.scene.paint.*;
    import javafx.scene.*;

    public class HLineTo_1 extends Application {

        // launch the application
        public void start(Stage stage)
        {

            try {

                // set title for the stage
                stage.setTitle("HLineTo");

                // create HLineTo
                HLineTo HLineto = new HLineTo(200);

                // create moveto
                MoveTo moveto = new MoveTo(100, 100);

                // create a Path
                Path path = new Path(moveto, HLineto);

                // set fill for path
                path.setFill(Color.BLACK);

                // set stroke width
                path.setStrokeWidth(2);

                // create a Group
                Group group = new Group(path);

                // create a scene
                Scene scene = new Scene(group, 400, 300);

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

    **输出:**

    ![](img/c40784f798166ddb6c6f4b94c6192560.png)

*   **Java program to create a path and add multiple HLineTo object to it and display it:**
    1.  在这个程序中，我们将创建一个名为*路径*的路径对象。
    2.  用指定的 X 坐标创建三个 HLineTo 对象。
    3.  然后创建三个名为 *moveto* 、 *moveto_1* 和 *moveto_2* 的 MoveTo 对象。
    4.  按顺序将所有“移动到”和“直线到”对象添加到路径中。
    5.  之后，将此路径添加到组对象。
    6.  将组对象添加到场景，将场景添加到舞台，调用 *show()* 函数显示最终结果。

    ```java
    // Java program to create a path and add 
    // multiple HLineTo object to it and display it
    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.*;
    import javafx.scene.layout.*;
    import javafx.stage.Stage;
    import javafx.scene.layout.*;
    import javafx.scene.paint.*;
    import javafx.scene.text.*;
    import javafx.geometry.*;
    import javafx.scene.layout.*;
    import javafx.scene.shape.*;
    import javafx.scene.paint.*;
    import javafx.scene.*;

    public class HLineTo_2 extends Application {

        // launch the application
        public void start(Stage stage)
        {

            try {

                // set title for the stage
                stage.setTitle("HLineTo");

                // create HLineTo
                HLineTo HLineto = new HLineTo(200);
                HLineTo HLineto_1 = new HLineTo(250);
                HLineTo HLineto_2 = new HLineTo(225);

                // create moveto
                MoveTo moveto = new MoveTo(100, 100);
                MoveTo moveto_1 = new MoveTo(150, 200);
                MoveTo moveto_2 = new MoveTo(200, 300);

                // create a Path
                Path path = new Path(moveto, HLineto, moveto_1, 
                               HLineto_1, moveto_2, HLineto_2);

                // set fill for path
                path.setFill(Color.BLACK);

                // set stroke width
                path.setStrokeWidth(2);

                // create a Group
                Group group = new Group(path);

                // create a scene
                Scene scene = new Scene(group, 400, 400);

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

    **输出:**

    ![](img/b0af6974e40db6bab3894839463c140f.png)

**注意:**上述程序可能无法在联机 IDE 中运行，请使用脱机编译器。

**参考:**[https://docs . Oracle . com/javase/8/JavaFX/API/JavaFX/scene/shape/hlineto . html](https://docs.oracle.com/javase/8/javafx/api/javafx/scene/shape/HLineTo.html)