# JavaFX |带示例的光标类

> 原文:[https://www . geesforgeks . org/JavaFX-cursor-class-with-examples/](https://www.geeksforgeeks.org/javafx-cursor-class-with-examples/)

游标类是 JavaFX 的一部分。Cursor 类用于封装鼠标光标的位图表示。游标类有几个预定义的游标，可以根据程序员的需要使用。

**常用方法:**

| 方法 | 说明 |
| --- | --- |
| 光标(字符串) | 返回指定字符串的光标对象 |
| toString() | 返回光标的字符串表示形式。 |

下面的程序将说明游标类的使用:

1.  **Java program to set some predefined cursor to the by passing string identifier as arguments:** This program creates a Cursor named *cursor_*. The cursor will be set to the scene using the function *setCursor()*.we will create a label. The label will be created inside a scene, which in turn will be hosted inside a stage. The function *setTitle()* is used to provide title to the stage. Then a tile pane is created, on which *addChildren()* method is called to attach the label inside the scene. Finally, the *show()* method is called to display the final results.

    ```java
    // Java program to set some predefined cursor
    // to the by passing string identifier as arguments
    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.Button;
    import javafx.scene.layout.*;
    import javafx.event.ActionEvent;
    import javafx.event.EventHandler;
    import javafx.scene.control.Label;
    import javafx.stage.Stage;
    import javafx.scene.Cursor;

    public class cursor_0 extends Application {

        // launch the application
        public void start(Stage stage)
        {

            // set title for the stage
            stage.setTitle("Creating Cursor");

            // create a stack pane
            TilePane tilepane = new TilePane();

            // create a label
            Label label = new Label("Cursor Example");

            // add button
            tilepane.getChildren().add(label);

            // create a scene
            Scene scene = new Scene(tilepane, 200, 200);

            // create a cursor
            Cursor cursor_ = Cursor.cursor("WAIT");

            // set cursor for the scene
            scene.setCursor(cursor_);

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

    <video class="wp-video-shortcode" id="video-217275-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/Cursor_1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/Cursor_1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/Cursor_1.mp4)</video>
2.  **Java program to set some predefined cursor to the scene:** This program creates a Button indicated by the name button respectively. We will create an array of predefined cursors named *cursor_*. The cursor will be set to the scene using the function *setCursor()* from the list of predefined cursor *cursor_*. The button will be created inside a scene, which in turn will be hosted inside a stage. We would create a label. The function *setTitle()* is used to provide title to the stage. Then a tile pane is created, on which *addChildren()* method is called to attach the button and label inside the scene. Finally, the *show()* method is called to display the final results.we would create an event handler to handle the button events. The event handler would be added to the button using *setOnAction()* function. When the button will be pressed the cursor of the scene will be changed by using the function **setCursor()**.

    ```java
    // Java program to set some predefined
    // cursor to the scene
    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.Button;
    import javafx.scene.layout.*;
    import javafx.event.ActionEvent;
    import javafx.event.EventHandler;
    import javafx.scene.control.Label;
    import javafx.stage.Stage;
    import javafx.scene.Cursor;

    public class cursor_1 extends Application {

    // counter of cursor
    int i = 0;

    // launch the application
    public void start(Stage stage)
    {
        // set title for the stage
        stage.setTitle("Creating Cursor");

        // create a button
        Button button = new Button("cursor");

        // create a stack pane
        TilePane tilepane = new TilePane();

        // create a label
        Label label = new Label("Cursor Example");

        // create a cursor with predefined cursor
        Cursor cursor_[] = {Cursor.CLOSED_HAND, Cursor.CROSSHAIR,
                            Cursor.DEFAULT, Cursor.DISAPPEAR, 
                            Cursor.E_RESIZE, Cursor.H_RESIZE, 
                            Cursor.HAND, Cursor.MOVE, 
                            Cursor.N_RESIZE, Cursor.NE_RESIZE, 
                            Cursor.NONE, Cursor.NW_RESIZE, 
                            Cursor.OPEN_HAND, Cursor.SE_RESIZE, 
                            Cursor.SW_RESIZE, Cursor.TEXT, 
                            Cursor.V_RESIZE, Cursor.W_RESIZE,
                            Cursor.WAIT};

        // add button
        tilepane.getChildren().add(button);
        tilepane.getChildren().add(label);

        // create a scene
        Scene scene = new Scene(tilepane, 200, 200);

        // set cursor for the scene
        scene.setCursor(cursor_[0]);

        // action event
        EventHandler<ActionEvent> event = 
          new EventHandler<ActionEvent>() 
        {
            public void handle(ActionEvent e)
            {
                if (i == cursor_.length - 1)
                    i = -1;

                // change the cursor
                scene.setCursor(cursor_[++i]);
            }
        };

        // when button is pressed
        button.setOnAction(event);

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

    <video class="wp-video-shortcode" id="video-217275-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/Cursor_1.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/Cursor_1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/Cursor_1.mp4)</video>

**注意:**上述程序可能无法在在线 IDE 中运行。请使用离线编译器。

**参考:**