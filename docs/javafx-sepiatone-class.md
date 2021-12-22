# JavaFX | SepiaTone 类

> 原文:[https://www.geeksforgeeks.org/javafx-sepiatone-class/](https://www.geeksforgeeks.org/javafx-sepiatone-class/)

SepiaTone 类是 JavaFX 的一部分。棕褐色类用于为图像添加棕褐色色调效果，类似于古董照片。在应用棕褐色效果时，图像上会出现红棕色调。

**类的构造函数:**

1.  **Sepitone()**:创建 Sepitone 类的新对象。
2.  **Sepitone(双 l)** :创建一个具有指定级别的新 Sepitone 对象。

**常用方法:**

| 方法 | 说明 |
| --- | --- |
| getInput() | 返回属性输入的值。 |
| 设置输入(效果五) | 设置属性输入的值。 |
| setLevel(双 v) | 设置棕褐色调对象的级别值。 |
| getLevel() | 返回棕褐色调对象的级别值。 |

下面的程序说明了 SepiaTone 类的使用:

1.  **Java program to import an image and add SepiaTone effect to it:** In this program a *FileInputStream* is created and an image is taken as input from a file. Image named *image* is created using the input from file input stream. From the image a *image view object* is created and it is added to the *VBox*. The *VBox* is then added to the scene and the scene is added to the stage. A *SepiaTone* effect is created with a specified level passed as parameters and the effect is set to the image view using *setEffect()* function.

    ```
    // Java program to import an image 
    // and add SepiaTone effect to it
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

    public class sepia_tone_1 extends Application {

        // launch the application
        public void start(Stage stage) throws Exception
        {

            // set title for the stage
            stage.setTitle("SepiaTone Example");

            // create a input stream
            FileInputStream input = new FileInputStream("D:\\GFG.png");

            // create a image
            Image image = new Image(input);

            // create a image View
            ImageView imageview = new ImageView(image);

            // create a sepia_tone effect
            SepiaTone sepia_tone = new SepiaTone(0.5);

            // set effect
            imageview.setEffect(sepia_tone);

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
    [![](img/01ce25b0cb8b3d27495cf6844194a413.png)](https://media.geeksforgeeks.org/wp-content/uploads/GFG-15.png)

    **输出:**
    [![](img/f61019fb636fe4994d2eb204a57ed39e.png)](https://media.geeksforgeeks.org/wp-content/uploads/sepia_1.png)

2.  **Java program to import an image and set SepiaTone effect to it. The Level of the SepiaTone effect can be controlled using the button:** In this program a *FileInputStream* is created and an image is taken as input from a file. Image named *image* is created using the input from the file input stream. From the image, an *image view object* is created and it is added to the *VBox*. The VBox is then added to the scene and the scene is added to the stage. A SepiaTone effect is created with a specified level passed as parameters and the effect is set to the image view using *setEffect()* function. A Button named button is created which is used to increase the *SepiaTone* of the image. The button is also added to the *VBox*. The SepiaTone of the image is increased using the *setLevel()* function.The events related to button is handled using *EventHandler*.

    ```
    // Java program to import an image and set
    // SepiaTone effect to it. The Level of the
    // SepiaTone effect can be controlled 
    // using the button
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

    public class sepia_tone_2 extends Application {

        double level = 0.1;

        // launch the application
        public void start(Stage stage) throws Exception
        {

            // set title for the stage
            stage.setTitle("SepiaTone Example");

            // create a input stream
            FileInputStream input = new FileInputStream("D:\\GFG.png");

            // create a image
            Image image = new Image(input);

            // create a image View
            ImageView imageview = new ImageView(image);

            // create a sepia_tone effect
            SepiaTone sepia_tone = new SepiaTone(level);

            // create a button
            Button button = new Button("increase");

            // action event
            EventHandler<ActionEvent> event = new EventHandler<ActionEvent>() {
                public void handle(ActionEvent e)
                {

                    // increase the level
                    level += 0.1;
                    if (level > 1)
                        level = 0.0;

                    // set Level for sepia_tone
                    sepia_tone.setLevel(level);
                }
            };

            // set on action of button
            button.setOnAction(event);

            // set effect
            imageview.setEffect(sepia_tone);

            // create a VBox
            VBox vbox = new VBox(imageview, button);

            // create a scene
            Scene scene = new Scene(vbox, 300, 300);

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
    [![](img/01ce25b0cb8b3d27495cf6844194a413.png)](https://media.geeksforgeeks.org/wp-content/uploads/GFG-15.png)

    **输出:**

    <video class="wp-video-shortcode" id="video-220201-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/Sepia_2.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/Sepia_2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/Sepia_2.mp4)</video>

**注意:**上述程序可能无法在在线 IDE 中运行。请使用离线编译器。

**参考:**[https://docs . Oracle . com/javase/8/JavaFX/API/JavaFX/scene/effect/sepiatone . html](https://docs.oracle.com/javase/8/javafx/api/javafx/scene/effect/SepiaTone.html)