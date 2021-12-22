# JavaFX |滑块类

> 原文:[https://www.geeksforgeeks.org/javafx-slider-class/](https://www.geeksforgeeks.org/javafx-slider-class/)

滑块是 JavaFX 中的一个控件，用于显示连续或离散范围的有效数字选项，并允许用户与控件交互。滑块呈现为带有旋钮的垂直或水平条，用户可以滑动该旋钮来指示所需的值。滑块也可以有刻度线和标签来指示沿条的间隔。
滑块的三个基本变量是 *min* 、 *max* 和*值*。该值应该始终是由最小值和最大值定义的范围内的数字。*最小值*应始终小于至*最大值*。*最小值*默认为 0，而*最大值*默认为 100。

**类的构造函数:**

*   **滑块():**创建默认的滑块实例。
*   **滑块(双最小值、双最大值、双值):**使用指定的滑块最小值、最大值和当前值构建滑块控件。

**常用方法:**

| 方法 | 描述 |
| --- | --- |
| 调整值(双倍新值) | 调整值以匹配新值。 |
| 减量() | 将值递减区块增量，以最大值为界。 |
| getBlockIncrement() | 获取属性 blockIncrement 的值。 |
| getMax() | 获取属性 max 的值。 |
| getMin() | 获取属性 min 的值。 |
| getMajorTickUnit() | 获取 majorTickUnit 属性的值。 |
| getMinorTickCount() | 获取 minorTickCount 属性的值。 |
| 获得价值 （） | 获取属性值。 |
| 增量() | 以最大值为界，按块增量递增该值。 |
| setblockincrement(双值) | 设置属性块增量的值。 |
| setmajortickunit(双值) | 设置 majorTickUnit 属性的值。 |
| 设置最大值(双精度值) | 设置属性 max 的值。 |
| 设置最小值(双数值) | 设置属性最小值。 |
| setMinorTickCount(整数值) | 设置 minorTickCount 属性的值。 |
| 设置值(双精度值) | 设置属性值。 |
| 设置值更改(布尔值) | 设置属性值更改。 | setShowTickMarks(布尔值) | 设置属性 showTickMarks 的值。 |
| setShowTickLabels(布尔值) | 设置属性 showTickLabels 的值。 | isShowTickLabels() | 获取属性 showTickLabels 的值。 |
| isShowTickMarks() | 获取属性 showTickMarks 的值。 |

下面的程序说明了 Slider 类的使用:

1.  **Simple Java program to implement the Slider Class:** In this program we will create a group and Scene. Add Scene to the frame. Then, create a Slider and add it to the frame. Now launch the application.

    ```
    // Java program to implement the Slider Class
    import javafx.application.Application;
    import javafx.scene.Group;
    import javafx.scene.Scene;
    import javafx.scene.control.Slider;
    import javafx.stage.Stage;

    public class SliderExample extends Application {

        public void start(Stage stage)
        {

            // creating group
            Group root = new Group();
            Scene scene = new Scene(root, 600, 400);

            // set Scene to the stage
            stage.setScene(scene);

            // set title for the frame
            stage.setTitle("Slider Sample");

            // create slider
            Slider slider = new Slider();

            // add slider to the frame
            root.getChildren().add(slider);

            stage.show();
        }

        // Main Method
        public static void main(String[] args)
        {

            // launch the application
            launch(args);
        }
    }
    ```

    **输出:**

    <video class="wp-video-shortcode" id="video-222956-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20180831_234901.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20180831_234901.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20180831_234901.mp4)</video>
2.  **Java program to implement Slider class by using TickMarks and TickLabels:** In this program we will create a Group and scene. Add the scene to the frame. Create a slider with specified *min*, *max* and *value*. Enable the Marks and Labels. Set *MajorTickUnit* with the specified value. Add the Slider to the frame and display it.

    ```
    // Java program to implement Slider class
    // by using TickMarks and TickLabels
    import javafx.application.Application;
    import javafx.scene.Group;
    import javafx.scene.Scene;
    import javafx.scene.control.Slider;
    import javafx.stage.Stage;

    public class SliderExample extends Application {

        public void start(Stage stage)
        {
            Group root = new Group();

            // create a Scene
            Scene scene = new Scene(root, 600, 400);

            // add Scene to the frame
            stage.setScene(scene);

            // set title of the frame
            stage.setTitle("Slider Sample");

            // Creates a slider
            Slider slider = new Slider(0, 1, 0.5);

            // enable the marks
            slider.setShowTickMarks(true);

            // enable the Labels
            slider.setShowTickLabels(true);

            // set Major tick unit
            slider.setMajorTickUnit(0.25f);

            // sets the value of the property
            // blockIncrement
            slider.setBlockIncrement(0.1f);

            root.getChildren().add(slider);

            // display
            stage.show();
        }

        // Main Method
        public static void main(String[] args)
        {

            // Launch the application
            launch(args);
        }
    }
    ```

    **输出:**

    <video class="wp-video-shortcode" id="video-222956-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20180901_000557.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20180901_000557.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20180901_000557.mp4)</video>
3.  **Java program to implement Slider Class using ChangeListener:** In this program, we will create a *Label* and set the color for the text. Create a slider and set its min, max and value. Enable TickLabels and TickMarks. Set the value of the property *blockIncrement*. *setBlockIncrement()* method defines the distance that the thumb moves when a user clicks on the track. Add ChangeListener, on moving the slider the value of the brightness changes which will show in the label. Create a VBox and add to the frame. Create Scene and to the frame. Finally, launch the application.

    ```
    // Java program to implement Slider Class
    // using ChangeListener
    import javafx.application.Application;
    import javafx.beans.value.ChangeListener;
    import javafx.beans.value.ObservableValue;
    import javafx.geometry.Insets;
    import javafx.scene.Scene;
    import javafx.scene.control.Label;
    import javafx.scene.control.Slider;
    import javafx.scene.layout.VBox;
    import javafx.scene.paint.Color;
    import javafx.stage.Stage;

    public class SliderExample extends Application {

        public void start(Stage stage)
        {

            // create label
            Label label = new Label("Select the Brightness");
            Label l = new Label(" ");

            // set the color of the tesxt
            l.setTextFill(Color.BLACK);

            // create slider
            Slider slider = new Slider();

            // set the value of property min,
            // max and value
            slider.setMin(0);
            slider.setMax(100);
            slider.setValue(80);

            // enable TickLabels and Tick Marks
            slider.setShowTickLabels(true);
            slider.setShowTickMarks(true);

            slider.setBlockIncrement(10);

            // Adding Listener to value property.
            slider.valueProperty().addListener(
                 new ChangeListener<Number>() {

                public void changed(ObservableValue <? extends Number > 
                          observable, Number oldValue, Number newValue)
                {

                    l.setText("value: " + newValue);
                }
            });

            // create a VBox
            VBox root = new VBox();

            root.setPadding(new Insets(20));
            root.setSpacing(10);
            root.getChildren().addAll(label, slider, l);

            stage.setTitle("Slider Sample");

            // create Scene and add to the frame
            Scene scene = new Scene(root, 350, 200);
            stage.setScene(scene);
            stage.show();
        }

        // Main Method
        public static void main(String[] args)
        {

            // Launch Application
            Application.launch(args);
        }
    }
    ```

    **输出:**

    <video class="wp-video-shortcode" id="video-222956-3" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20180901_010316.mp4?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/20180901_010316.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20180901_010316.mp4)</video>

**注意:**上述程序可能无法在在线 IDE 中运行。请使用离线编译器。

**参考:**T2【https://docs . Oracle . com/javase/8/JavaFX/API/JavaFX/scene/control/slider . html