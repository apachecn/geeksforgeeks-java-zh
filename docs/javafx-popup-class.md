# JavaFX |弹出类

> 原文:[https://www.geeksforgeeks.org/javafx-popup-class/](https://www.geeksforgeeks.org/javafx-popup-class/)

Popup 类是 JavaFX 的一部分。Popup 类创建一个没有内容、空填充并且透明的弹出窗口。Popup 类用于显示通知、按钮或下拉菜单等。弹出窗口没有装饰。它本质上是一个没有装饰的特殊场景/窗口。

**该类的构造函数:**

*   **Popup()** :创建一个 Popup 类的对象。

**常用方法:**

| 方法 | 说明 |
| --- | --- |
| getContent() | 要在此弹出窗口上呈现的节点的观察列表。 |
| setAutoHide(boolean v) | 将自动隐藏的值设置为指定的布尔值。 |
| isShowing() | 返回弹出窗口是否可见。 |

下面的程序说明了弹出类的使用:

1.  **Java program to create a popup and add it to the stage:** In this program we create a Popup named *popup*. The popup contains a Label named *label*. We also create a Button named *button* and add event handler to it and then display the popup if it is hidden and hide it if it is already visible. The button is added to the TilePane and the TilePane is added to the scene, and the scene is added to the stage. The show function is called to display the results. The background color of the label is set using the *setStyle()* function, and the label size is set using *setMinHeight()*, *setMinWidth()* function. The *hide()* and *show()* function is used to hide or show the popup.

    ```
    // Java program to create a popup and 
    // add it to the stage
    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.Button;
    import javafx.scene.layout.*;
    import javafx.event.ActionEvent;
    import javafx.event.EventHandler;
    import javafx.scene.control.Label;
    import javafx.stage.Stage;
    import javafx.stage.Popup;

    public class Popup_1 extends Application {

        // launch the application
        public void start(Stage stage)
        {

            // set title for the stage
            stage.setTitle("Creating popup");

            // create a button
            Button button = new Button("button");

            // create a tile pane
            TilePane tilepane = new TilePane();

            // create a label
            Label label = new Label("This is a Popup");

            // create a popup
            Popup popup = new Popup();

            // set background
            label.setStyle(" -fx-background-color: white;");

            // add the label
            popup.getContent().add(label);

            // set size of label
            label.setMinWidth(80);
            label.setMinHeight(50);

            // action event
            EventHandler<ActionEvent> event = 
            new EventHandler<ActionEvent>() {

                public void handle(ActionEvent e)
                {
                    if (!popup.isShowing())
                        popup.show(stage);
                    else
                        popup.hide();
                }
            };

            // when button is pressed
            button.setOnAction(event);

            // add button
            tilepane.getChildren().add(button);

            // create a scene
            Scene scene = new Scene(tilepane, 200, 200);

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

    **输出:**

    <video class="wp-video-shortcode" id="video-222156-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/Popup_1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/Popup_1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/Popup_1.mp4)</video>
2.  **Java Program to create a popup and add it to the stage and make the popup hide automatically when it loses focus using the *setAutoHide()* function:** In this program we create a Popup named *popup*. The popup contains a Label named *label*. We also create a Button named *button* and add event handler to it, to display the popup if it is hidden. The button is added to the TilePane and the TilePane is added to the scene, and the scene is added to the stage. The show function is called to display the results. The popup will automatically hide when it loses focus, we will apply this feature to the popup using the *setAutoHide()* function.The background color of the label is set using the *setStyle()* function, and the label size is set using *setMinHeight()*, *setMinWidth()* function. The hide() and *show()* function is used to hide or show the popup.

    ```
    // Java Program to create a popup and add
    // it to the stage and make the popup hide
    // automatically when it loses focus using
    // the setAutoHide() function
    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.Button;
    import javafx.scene.layout.*;
    import javafx.event.ActionEvent;
    import javafx.event.EventHandler;
    import javafx.scene.control.Label;
    import javafx.stage.Stage;
    import javafx.stage.Popup;

    public class popup_2 extends Application {

        // launch the application
        public void start(Stage stage)
        {

            // set title for the stage
            stage.setTitle("Creating Popup");

            // create a button
            Button button = new Button("popup");

            // create a tile pane
            TilePane tilepane = new TilePane();

            // create a label
            Label label = new Label("This is a Popup");

            // create a popup
            Popup popup = new Popup();

            // set background
            label.setStyle(" -fx-background-color: white;");

            // add the label
            popup.getContent().add(label);

            // set size of label
            label.setMinWidth(80);
            label.setMinHeight(50);

            // set auto hide
            popup.setAutoHide(true);

            // action event
            EventHandler<ActionEvent> event = 
            new EventHandler<ActionEvent>() {
                public void handle(ActionEvent e)
                {
                    if (!popup.isShowing())
                        popup.show(stage);
                }
            };

            // when button is pressed
            button.setOnAction(event);

            // add button
            tilepane.getChildren().add(button);

            // create a scene
            Scene scene = new Scene(tilepane, 200, 200);

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

    **输出:**

    <video class="wp-video-shortcode" id="video-222156-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/Popup_2.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/Popup_2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/Popup_2.mp4)</video>

**注意:**上述程序可能无法在在线 IDE 中运行。请使用离线编译器。

**参考:**[https://docs . Oracle . com/javase/8/JavaFX/API/JavaFX/stage/popup . html](https://docs.oracle.com/javase/8/javafx/api/javafx/stage/Popup.html)