# JavaFX | WebView 类

> 原文:[https://www.geeksforgeeks.org/javafx-webview-class/](https://www.geeksforgeeks.org/javafx-webview-class/)

WebView 类是 JavaFX 的一部分。网络视图可以创建和管理网络引擎，并显示其内容。关联的网络引擎是在构建时自动创建的，不能更改。网络视图管理键盘和鼠标事件，并自动向网络视图添加滚动条。

**该类的构造函数:**

*   **网络视图()**:创建一个新的网络视图对象。

**常用方法:**

| 方法 | 说明 |
| --- | --- |
| getChildren() | 获取此父级的子级列表。 |
| getEngine() | 返回 webview 的引擎。 |
| getFontScale() | 返回 webview 对象的 fontscale。 |
| getHeight（） | 返回此网络视图的高度。 |
| getMaxHeight() | 返回最大高度。 |
| getMaxWidth() | 返回最大宽度。 |
| getMinHeight() | 设置最小高度。 |
| getMinWidth() | 返回最小宽度。 |
| getPrefHeight() | 返回首选高度。 |
| getPrefWidth() | 返回首选宽度。 |
| getWidth（） | 返回此网页视图的宽度。 |
| getZoom() | 返回当前缩放因子。 |
| maxHeight(双 v) | 设置最大高度。 |
| 最大宽度(双 v) | 设置最大宽度。 |
| minHeight(双 v) | 设置最小高度。 |
| 最小宽度(双 v) | 设置最小宽度。 |
| 字首高度(双 v) | 设置 webview 的首选高度。 |
| 字首宽度(双 v) | 设置 webview 的首选宽度。 |
| setFontScale(双 v) | 设置 webview 的字体比例。 |
| setMaxHeight(双 v) | 设置最大高度。 |
| setMaxWidth(双 v) | 设置最大宽度。 |
| setMinHeight(双 v) | 设置最小高度。 |
| 设置最小宽度(双 v) | 设置最小宽度。 |
| setPrefHeight（double v） | 设置首选高度。 |
| setprefwidth(双 v) | 设置首选宽度。 |
| 凸模(双 v) | 设置 webview 的缩放比例。 |

以下程序说明了 Webview 类的使用:

1.  **Java Program to create a WebView and load a website and display it on the stage:** In this program we will create a WebView named *webview* . We will extract WebEngine from the WebView by using *getEngine()* method. Now load a website on the engine by using *load()* function, we will set the *webview* to the scene with preferred height and preferred width and add the scene to the stage using *setScene()* method and display the stage using *show()* function.

    ```java
    // Java Program to create a WebView and load 
    // a website and display it on the stage
    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.*;
    import javafx.scene.layout.*;
    import javafx.stage.Stage;
    import javafx.event.ActionEvent;
    import javafx.event.EventHandler;
    import javafx.scene.canvas.*;
    import javafx.scene.web.*;
    import javafx.scene.Group;

    public class SliderExample extends Application {

        // launch the application
        public void start(Stage stage)
        {
            try {

                // set title for the stage
                stage.setTitle("creating Webview");

                // create a webview object
                WebView w = new WebView();

                // get the web engine
                WebEngine e = w.getEngine();

                // load a website
                e.load("https://www.geeksforgeeks.org");

                // create a scene
                Scene scene = new Scene(w, w.getPrefWidth(), 
                                         w.getPrefHeight());

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

    ![](img/4ac44a8d152a531ec7ba368d4a923e44.png)

2.  **Java Program to create a WebView and load a website, set the font scale, also set the zoom and display it on the stage:** In this program we will create a WebView named *webview*. We will extract WebEngine from the WebView by using *getEngine()* method. Now set the font size and the zoom of the object using the *setFontSize()* and *setZoom()* function. We will load a website on the engine by using function *load()*. Then set the webview to the scene with preferred height and preferred width and add the scene to the stage using *setScene()* method and display the stage using *show()* function.

    ```java
    // Java Program to create a WebView and load 
    // a website, set the fontscale, also set 
    // the zoom and display it on the stage
    import javafx.application.Application;
    import javafx.scene.Scene;
    import javafx.scene.control.*;
    import javafx.scene.layout.*;
    import javafx.stage.Stage;
    import javafx.event.ActionEvent;
    import javafx.event.EventHandler;
    import javafx.scene.canvas.*;
    import javafx.scene.web.*;
    import javafx.scene.Group;

    public class webview_2 extends Application {

        // launch the application
        public void start(Stage stage)
        {

            try {

                // set title for the stage
                stage.setTitle("creating Webview");

                // create a webview object
                WebView w = new WebView();

                // get the web engine
                WebEngine e = w.getEngine();

                // load a website
                e.load("https://www.geeksforgeeks.org");

                // set font scale for the webview
                w.setFontScale(1.5f);

                // set zoom
                w.setZoom(0.8);

                // create a scene
                Scene scene = new Scene(w, w.getPrefWidth(),
                                         w.getPrefHeight());

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
    ![](img/2268a5af811c4e6e19e18cf6dd986608.png)

**注意:**上述程序可能无法在在线 IDE 中运行。请使用离线编译器。

**参考:**[https://docs . Oracle . com/javase/8/JavaFX/API/JavaFX/scene/web/webview . html](https://docs.oracle.com/javase/8/javafx/api/javafx/scene/web/WebView.html)