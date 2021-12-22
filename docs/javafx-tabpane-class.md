# JavaFX | TabPane 类

> 原文:[https://www.geeksforgeeks.org/javafx-tabpane-class/](https://www.geeksforgeeks.org/javafx-tabpane-class/)

TabPane 类是 JavaFX 的一部分。TabPane 允许在几个选项卡之间切换。选项卡窗格充当选项卡的容器。可以使用 setSide()函数指定选项卡的位置。当选项卡不适合选项卡窗格时，选项卡窗格的右上角会出现一个菜单按钮，显示选项卡窗格的所有选项卡。

**类的构造函数:**

1.  **选项卡窗格()**:创建一个没有选项卡的新选项卡窗格。
2.  **选项卡面板(选项卡… t)** :用指定的选项卡创建一个新的选项卡面板。

**常用方法:**

| 方法 | 说明 |
| --- | --- |
| getSide() | 返回选项卡窗格上选项卡的当前位置 |
| getTabs() | 返回选项卡窗格的选项卡。 |
| 设置侧(第五侧) | 在此选项卡窗格中放置选项卡的位置。 |
| 集选择模型(单个选择模型 v) | 设置用于选项卡选择的模型。 |
| getSelectionModel() | 返回选项卡选择的选择模型。 |
| getTabMaxHeight() | 返回选项卡窗格中选项卡的最大高度。 |
| gettadminheight _) | 返回选项卡窗格中选项卡的最小高度。 |
| getTabMaxWidth() | 返回选项卡窗格中选项卡的最大宽度。 |
| gettadminwidth _) | 返回选项卡窗格中选项卡的最小宽度。 |
| settabmaxheight(双 v) | 设置选项卡窗格中选项卡的最大高度。 |
| settadminheight_double v) | 设置选项卡窗格中选项卡的最小高度。 |
| setTabMaxWidth(双 v) | 设置选项卡窗格中选项卡的最大宽度。 |
| settadminwidth _ double v) | 设置选项卡窗格中选项卡的最小宽度。 |

下面的程序说明了 TabPane 类的使用:

1.  **Java program to create multiple tabs and add it to the TabPane:** In this program we will create a Tabpane named *tabpane*. To add multiple tabs we will use a for loop and then add tabs to the *tabpane*. Create a Tab named *tab*. We will also create a Label named *label*. We will add the label to the tab by using the function *setContent()*. The title of the tab will be passed as arguments. Now create a TabPane named *tabpane* and add the tab to the tabpane. After that add the *tabpane* to the scene and add the scene to the stage and display the stage using the *show()* function.

    ```
    // Java program to create multiple tabs 
    // and add it to the TabPane
    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.layout.*;
    import javafx.stage.Stage;
    import javafx.scene.Group;
    import javafx.scene.control.*;

    public class TabPane_1 extends Application {

        // launch the application
        public void start(Stage stage)
        {

            // set title for the stage
            stage.setTitle("Creating Tab");

            // create a tabpane
            TabPane tabpane = new TabPane();

            // create multiple tabs
            for (int i = 0; i < 10; i++) {

                // create Tab
                Tab tab = new Tab("Tab_" + (int)(i + 1));

                // create a label
                Label label = new Label("This is Tab: " + (int)(i + 1));

                // add label to the tab
                tab.setContent(label);

                // add tab
                tabpane.getTabs().add(tab);
            }

            // create a scene
            Scene scene = new Scene(tabpane, 600, 500);

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

    <video class="wp-video-shortcode" id="video-222487-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/TabPane_1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/TabPane_1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/TabPane_1.mp4)</video>
2.  **Java program to create multiple tabs and add it to the TabPane and also create a tab which on selected will create new tabs:** In this program we will create a Tabpane named *tabpane*. We will add multiple tabs to the *tabpane*. To add multiple tabs we will use a for loop. We will create a Tab named *tab*. Now create a Label named *label*. We will add a label to the tab by using the function *setContent()*. We will also create a tab named *newtab*. When it is selected then it will create a new tab. Add event handler to the tab by using *setOnSelectionChanged()* function. The event handler will create a new tab and add it before the new tab in *tabpane* using *getTabs().add()* function and select the last tab using the *getSelectionModel().select()* function. The title of the tab will be passed as arguments. We will create a TabPane named *tabpane* and add the tab to the *tabpane* and add the *tabpane* to the scene and scene to the stage. Display the stage using the *show()* function.

    ```
    // Java program to create multiple tabs and
    // add it to the tabPane and also create a 
    // tab which on selected will create new tabs
    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.layout.*;
    import javafx.stage.Stage;
    import javafx.scene.Group;
    import javafx.scene.control.*;
    import javafx.event.Event;
    import javafx.event.EventHandler;

    public class TabPane_2 extends Application {

    // counter of tabs
    int counter = 0;

    // launch the application
    public void start(Stage stage)
    {

        // set title for the stage
        stage.setTitle("Creating Tab");

        // create a tabpane
        TabPane tabpane = new TabPane();

        for (int i = 0; i < 5; i++) {

            // create Tab
            Tab tab = new Tab("Tab_" + (int)(counter + 1));

            // create a label
            Label label = new Label("This is Tab: " 
                            + (int)(counter + 1));

            counter++;

            // add label to the tab
            tab.setContent(label);

            // add tab
            tabpane.getTabs().add(tab);
        }

        // create a tab which
        // when pressed creates a new tab
        Tab newtab = new Tab();

        // action event
        EventHandler<Event> event = 
        new EventHandler<Event>() {

            public void handle(Event e)
            {
                if (newtab.isSelected()) 
                {

                    // create Tab
                    Tab tab = new Tab("Tab_" + (int)(counter + 1));

                    // create a label
                    Label label = new Label("This is Tab: " 
                                     + (int)(counter + 1));

                    counter++;

                    // add label to the tab
                    tab.setContent(label);

                    // add tab
                    tabpane.getTabs().add(
                            tabpane.getTabs().size() - 1, tab);

                    // select the last tab
                    tabpane.getSelectionModel().select(
                            tabpane.getTabs().size() - 2);
                }
            }
        };

        // set event handler to the tab
        newtab.setOnSelectionChanged(event);

        // add newtab
        tabpane.getTabs().add(newtab);

        // create a scene
        Scene scene = new Scene(tabpane, 600, 500);

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

    <video class="wp-video-shortcode" id="video-222487-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/TabPane_2.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/TabPane_2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/TabPane_2.mp4)</video>

**注意:**上述程序可能无法在在线 IDE 中运行。请使用离线编译器。

**参考:**[https://docs . Oracle . com/javase/8/JavaFX/API/JavaFX/scene/control/tabbane . html](https://docs.oracle.com/javase/8/javafx/api/javafx/scene/control/TabPane.html)