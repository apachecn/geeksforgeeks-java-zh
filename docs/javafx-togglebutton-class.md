# JavaFX | ToggleButton 类

> 原文:[https://www.geeksforgeeks.org/javafx-togglebutton-class/](https://www.geeksforgeeks.org/javafx-togglebutton-class/)

ToggleButton 是一个特殊的控件，具有被选择的能力。基本上，ToggleButton 的呈现方式类似于 Button，但这两种是不同类型的控件。按钮是一个“命令”按钮，单击时会调用一个函数。但是 ToggleButton 是一个带有布尔值的控件，指示它是否被选中。它继承了*按钮库*类。

ToggleButton 也可以分组放置。默认情况下，ToggleButton 不在一个组中。分组时，在该组中一次只能选择一个切换按钮。要将两个 ToggleButtons 放在同一个组中，只需为 ToggleGroup 分配相同的值。与单选按钮不同，切换组中的切换按钮不会强制组中至少一个选定的切换按钮。意味着，如果选择了一个切换按钮，单击它将导致它被取消选择。使用单选按钮，单击组中选定的按钮将不起作用。

**类的构造函数:**

1.  **切换按钮()**:创建标签为空字符串的切换按钮。
2.  **切换按钮(String txt)** :创建一个以指定文本为标签的切换按钮。
3.  **切换按钮(字符串 txt，节点图形)**:创建一个切换按钮，其标签具有指定的文本和图标。

**常用方法:**

| 方法 | 描述 |
| --- | --- |
| 设置组值 | 将属性的值设置为 Group。 |
| 设置选定(布尔值) | 设置选定属性的值。 |
| isSelected() | 获取选定属性的值。 |
| 火灾() | 当用户手势指示应该发生此按钮库的事件时调用。 |

下面的程序说明了 ToggleButton 类的使用:

1.  **Simple Java program to demonstrate ToggleButton Class:** In this program we are trying to select the gender of a person. We first Create *HBox* and then set the *Layout* for it. Create a ToggleGroup and new Toggle Buttons named”*Male*” and “*Female*“. Set the Toggle Group (in a group only one button can be selected at a time) using *setToggleGroup()* method. By default Male button is selected. Create the scene and set scene to the stage using *setScene() method.* And launch the application.

    ```java
    // Java program to demonstrate ToggleButton Class
    import javafx.application.Application;
    import javafx.geometry.Insets;
    import javafx.scene.Scene;
    import javafx.scene.control.Label;
    import javafx.scene.control.ToggleButton;
    import javafx.scene.control.ToggleGroup;
    import javafx.scene.layout.HBox;
    import javafx.stage.Stage;

    public class ToggleButtonExample extends Application {

        public void start(Stage stage)
        {

            // Hbox layout
            HBox root = new HBox();
            root.setPadding(new Insets(10));
            root.setSpacing(5);

            // Gender
            root.getChildren().add(new Label("Your gender:"));

            // Creating a ToggleGroup
            ToggleGroup group = new ToggleGroup();

            // Creating new Toggle buttons.
            ToggleButton maleButton = new ToggleButton("Male");
            ToggleButton femaleButton = new ToggleButton("Female");

            // Set toggle group
            // In a group, maximum only
            // one button is selected
            maleButton.setToggleGroup(group);
            femaleButton.setToggleGroup(group);

            maleButton.setUserData("I am a Male");
            femaleButton.setUserData("I am a Female");

            // male button is selected at first by default
            maleButton.setSelected(true);

            root.getChildren().addAll(maleButton, femaleButton);

            // create the scene
            Scene scene = new Scene(root, 450, 300);

            stage.setTitle("Toggle Button");
            stage.setScene(scene);
            stage.show();
        }

        // Main Method
        public static void main(String[] args)
        {
            launch(args);
        }
    }
    ```

    **输出:**

    <video class="wp-video-shortcode" id="video-222117-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20180825_200037.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20180825_200037.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20180825_200037.mp4)</video>
2.  **Java program to demonstrate ToggleButton Class using ChangeListener:** In this program, we first create a label. Then we will create Toggle Buttons using *ToggleButton()* and Toggle Group is created using *ToggleGroup()* method. Add all the Toggle Buttons to the ToggleGroup. Now create a *ChangeListener* for the ToggleGroup. A ChangeListener is notified whenever the value of an ObservableValue change. An ObservableValue is an entity that wraps a value and allows to observe the value for changes. Now, create the label for the selection of the subjects. Create a HBox using *HBox()* Now, add ToggleButtons to an HBox. Set the spacing between the buttons using *setSpacing()* method. Create the VBox, add labels and *HBox* to the *VBox*. Set the size of the VBox and set padding of the VBox (e.g border-style, border-width, border-radius, border-insets, border-color). Create the scene and add it to the stage. Set the title of the stage and display.

    ```java
    // Java program to demonstrate ToggleButton
    // Class using ChangeListener
    import javafx.application.Application;
    import javafx.beans.value.ChangeListener;
    import javafx.beans.value.ObservableValue;
    import javafx.scene.Scene;
    import javafx.scene.control.Label;
    import javafx.scene.control.Toggle;
    import javafx.scene.control.ToggleButton;
    import javafx.scene.control.ToggleGroup;
    import javafx.scene.layout.HBox;
    import javafx.scene.layout.VBox;
    import javafx.stage.Stage;

    public class ToggleButtonDemo extends Application {

        // Create the Message Label
        Label selectionMsg = new Label("Your selection: None");

    public void start(Stage stage)
    {

        // Create four ToggleButtons
        ToggleButton csBtn = new ToggleButton("Computer Science");
        ToggleButton pBtn = new ToggleButton("Physics");
        ToggleButton chemBtn = new ToggleButton("Chemistry");
        ToggleButton mBtn = new ToggleButton("Maths");

        // Create a ToggleGroup
        final ToggleGroup group = new ToggleGroup();

        // Add all ToggleButtons to a ToggleGroup
        group.getToggles().addAll(csBtn, pBtn, chemBtn, mBtn);

        // Create a ChangeListener for the ToggleGroup
        group.selectedToggleProperty().addListener(
                       new ChangeListener<Toggle>() 
        {
            public void changed(ObservableValue<? extends Toggle> ov,
                        final Toggle toggle, final Toggle new_toggle)
            {
                String toggleBtn = ((ToggleButton)new_toggle).getText();
                selectionMsg.setText("Your selection: " + toggleBtn);
            }
        });

        // Create the Label for the Selection
        Label selectLbl = new Label("Select the subject :");

        // Create a HBox
        HBox buttonBox = new HBox();

        // Add ToggleButtons to an HBox
        buttonBox.getChildren().addAll(csBtn, pBtn, chemBtn, mBtn);

        // Set the spacing between children to 10px
        buttonBox.setSpacing(10);

        // Create the VBox
        VBox root = new VBox();

        // Add the Labels and HBox to the VBox
        root.getChildren().addAll(selectionMsg, selectLbl, buttonBox);

        // Set the spacing between children to 10px
        root.setSpacing(10);

        // Set the Size of the VBox
        root.setMinSize(350, 250);

        // Set the padding of the VBox
        // Set the border-style of the VBox
        // Set the border-width of the VBox
        // Set the border-insets of the VBox
        // Set the border-radius of the VBox
        // Set the border-color of the VBox
        root.setStyle("-fx-padding: 10;"
                + "-fx-border-style: solid inside;"
                + "-fx-border-width: 2;"
                + "-fx-border-insets: 5;"
                + "-fx-border-radius: 5;"
                + "-fx-border-color: blue;");

        // Create the Scene
        Scene scene = new Scene(root);

        // Add the scene to the Stage
        stage.setScene(scene);

        // Set the title of the Stage
        stage.setTitle("A ToggleButton Example");

        // Display the Stage
        stage.show();
    }

        // Main Method
        public static void main(String[] args)
        {

            // launch the application
            Application.launch(args);
        }
    }
    ```

    **输出:**

    <video class="wp-video-shortcode" id="video-222117-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20180825_185006-1.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20180825_185006-1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20180825_185006-1.mp4)</video>

    **注:**上述程序可能无法在在线 IDE 中运行。请使用离线编译器。

    **参考:**[https://docs . Oracle . com/javase/8/JavaFX/API/JavaFX/scene/control/togglebutton . html](https://docs.oracle.com/javase/8/javafx/api/javafx/scene/control/ToggleButton.html)