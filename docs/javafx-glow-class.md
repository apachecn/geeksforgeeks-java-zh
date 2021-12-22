# JavaFX |辉光类

> 原文:[https://www.geeksforgeeks.org/javafx-glow-class/](https://www.geeksforgeeks.org/javafx-glow-class/)

Glow 类是 JavaFX 的一部分。发光是一种高级效果，使用可配置的阈值使输入图像看起来发光。辉光类继承*效果*类。

**类的构造函数:**

1.  **辉光()**:使用默认参数创建新的辉光对象。
2.  **发光(双 l)** :创建一个具有指定等级的发光新实例。

**常用方法:** 

| 方法 | 说明 |
| --- | --- |
| getInput() | 返回属性输入的值 |
| 设置输入(效果五) | 设置属性输入的值 |
| setLevel(双 v) | 设置发光对象的级别值 |
| getLevel() | 返回发光对象的级别值 |

下面的程序说明了发光类的使用:

1.  **Java Program to add a image and add Glow effect to it:** In this program a *FileInputStream* is created and an image is taken as input from a file. Image named *image* is created using the input from the file input stream. From the *image*, an *image view object* is created and it is added to the *VBox*. The *VBox* is then added to the scene and the scene is added to the *stage*. A Glow effect is created with a specified level passed as parameters and the effect is set to the image view using *setEffect()* function.

    ```
    // Java Program to add a image and 
    // add Glow effect to it.
    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.*;
    import javafx.scene.layout.*;
    import javafx.stage.Stage;
    import javafx.scene.image.*;
    import javafx.scene.effect.*;
    import java.io.*;
    import javafx.event.ActionEvent;
    import javafx.event.EventHandler;
    import javafx.scene.Group;

    public class glow_1 extends Application {

        // launch the application
        public void start(Stage stage) throws Exception
        {

            // set title for the stage
            stage.setTitle("Glow Example");

            // create a input stream
            FileInputStream input = new FileInputStream("D:\\GFG.png");

            // create a image
            Image image = new Image(input);

            // create a image View
            ImageView imageview = new ImageView(image);

            // create a glow effect
            Glow glow = new Glow(0.5);

            // set effect
            imageview.setEffect(glow);

            // create a VBox
            VBox vbox = new VBox(imageview);

            // create a scene
            Scene scene = new Scene(vbox, 200, 200);

            // set the scene
            stage.setScene(scene);

            stage.show();
        }

        // Main Method
        public static void main(String args[])
        {

            // launch the application
            launch(args);
        }
    }
    ```

    **输入图像:**

    [![](img/90b4bf79e84a1dd34e938d364d112546.png)](https://media.geeksforgeeks.org/wp-content/uploads/GFG-12.png)

    **输出:**

    [![](img/308ef90fadb6070c8190d506d19f459d.png)](https://media.geeksforgeeks.org/wp-content/uploads/Glow_1.png)

2.  **Java Program to add an image and add a Glow effect to it, and also add a button to change the glow level:** In this program, an *FileInputStream* is created and an image is taken as input from a file. Image named *image* is created using the input from the file input stream. From the image, an *image view object* is created and it is added to the *VBox*. The *VBox* is then added to the scene and the scene is added to the stage. A Glow effect is created with a specified level passed as parameters and the effect is set to the image view using *setEffect()* function. A Button named button is created which is used to increase the glow of the image. The button is also added to the *VBox*. The glow of the image is increased using the *setLevel()* function. The events related to the button is handled using *EventHandler*.

    ```
    // Java Program to add a image and
    // add Glow effect to it, and also
    // add a button to change the glow level
    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.*;
    import javafx.scene.layout.*;
    import javafx.stage.Stage;
    import javafx.scene.image.*;
    import javafx.scene.effect.*;
    import java.io.*;
    import javafx.event.ActionEvent;
    import javafx.event.EventHandler;
    import javafx.scene.Group;

    public class glow_2 extends Application {

        double level = 0.1;

        // launch the application
        public void start(Stage stage) throws Exception
        {

            // set title for the stage
            stage.setTitle("Glow Example");

            // create a input stream
            FileInputStream input = new FileInputStream("D:\\GFG.png");

            // create a image
            Image image = new Image(input);

            // create a image View
            ImageView imageview = new ImageView(image);

            // create a glow effect
            Glow glow = new Glow(level);

            // create a button
            Button button = new Button("Glow");

            // action event
            EventHandler<ActionEvent> event = new EventHandler<ActionEvent>() {

                public void handle(ActionEvent e)
                {

                    // increase the level
                    level += 0.1;
                    if (level > 1)
                        level = 0.0;

                    // set Level gor glow
                    glow.setLevel(level);
                }
            };

            // set on action of button
            button.setOnAction(event);

            // set effect
            imageview.setEffect(glow);

            // create a VBox
            VBox vbox = new VBox(imageview, button);

            // create a scene
            Scene scene = new Scene(vbox, 200, 200);

            // set the scene
            stage.setScene(scene);

            stage.show();
        }

        // Main Method
        public static void main(String args[])
        {

            // launch the application
            launch(args);
        }
    }
    ```

    **输入图像:**

    [![](img/90b4bf79e84a1dd34e938d364d112546.png)](https://media.geeksforgeeks.org/wp-content/uploads/GFG-12.png)

    **输出图像:**

    <video class="wp-video-shortcode" id="video-218889-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/Glow.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/Glow.mp4](https://media.geeksforgeeks.org/wp-content/uploads/Glow.mp4)</video>

**注意:**上述程序可能无法在在线 IDE 中运行。请使用离线编译器。

**参考:**[https://docs . Oracle . com/javase/8/JavaFX/API/JavaFX/场景/效果/Glow.html](https://docs.oracle.com/javase/8/javafx/api/javafx/scene/effect/Glow.html)