# JavaFX |维度 2D 类

> 原文:[https://www.geeksforgeeks.org/javafx-dimension2d-class/](https://www.geeksforgeeks.org/javafx-dimension2d-class/)

Dimension2D 类是 JavaFX 的一部分。Dimension2D 类是一个存储高度和宽度的对象。它继承了 *java.lang.Object* 类。

**该类的构造函数:**

1.  **尺寸 2D(双倍宽度，双倍高度)**:创建具有指定宽度和高度的尺寸对象。

**常用方法:**

| 方法 | 说明 |
| --- | --- |
| 等于(对象对象) | 返回二维对象是否相等 |
| getHeight（） | 返回尺寸 2d 对象的高度 |
| getWidth（） | 返回尺寸 2d 对象的宽度 |
| hashCode() | 返回维度 2D 对象的哈希代码值。 |

以下程序将说明尺寸 2D 类的使用:

1.  **Java program to create a Dimension2D object and display its contents:** This program creates a Dimension2D object named dimension. The height and width of the dimension is passed as arguments. Then the height and width are extracted from the object using *getHeight()* and *getWidth()* function and the respective values are displayed.

    ```
    // Java program to create a Dimension2D 
    // object and display its contents
    import javafx.geometry.*;

    public class Dimension_1 {

        // Main Method
        public static void main(String args[])
        {

            // create a dimension object
            Dimension2D dimension = new Dimension2D(20.0f, 50.0f);

            double height, width;

            // get the height and width of the dimension2D
            height = dimension.getHeight();
            width = dimension.getWidth();

            // display the height and width of dimension2D
            System.out.println("Height = " + height + " Width = " + width);
        }
    }
    ```

    **输出:**

    ```
    Height = 50.0 Width = 20.0

    ```

2.  **Java program to create 3 Dimension2D objects display its contents and how whether one object is equal to the other or not:** This program creates three Dimension2D object named *dimension_1*, *dimension_2*, *dimension_3*. The height and width of the dimension is passed as arguments. Then the height and width are extracted from the object using *getHeight()* and *getWidth()* function and the respective values are displayed. The three objects are then compared using the equals() functions and the result is displayed.

    ```
    // Java program to create 3 Dimension2D objects display
    // its contents and how whether one object is equal to 
    // the other or not
    import javafx.geometry.*;

    public class Dimension_2 {

        // Main Method
        public static void main(String args[])
        {

            // create three dimension objects
            Dimension2D dimension_1 = new Dimension2D(20.0f, 50.0f);
            Dimension2D dimension_2 = new Dimension2D(120.0f, 150.0f);
            Dimension2D dimension_3 = new Dimension2D(20.0f, 50.0f);

            // display the coordinates of the 3 dimensions
            display(dimension_1);
            display(dimension_2);
            display(dimension_3);

            // check whether any dimension is equal to other or not
            System.out.println("Dimension 1 equals Dimension 2 = " 
                               + dimension_1.equals(dimension_2));

            System.out.println("Dimension 2 equals Dimension 3 = " 
                                + dimension_2.equals(dimension_3));

            System.out.println("Dimension 3 equals Dimension 1 = " 
                                + dimension_3.equals(dimension_1));
        }

        // Display Method
        public static void display(Dimension2D dimension)
        {

            double height, width;

            // get the cheight and width of the dimension
            height = dimension.getHeight();
            width = dimension.getWidth();

            // display the height and width of dimension2D
            System.out.println("Height = " + height + " Width = " + width);
        }
    }
    ```

    **输出:**

    ```
    Height = 50.0 Width = 20.0
    Height = 150.0 Width = 120.0
    Height = 50.0 Width = 20.0
    Dimension 1 equals Dimension 2 = false
    Dimension 2 equals Dimension 3 = false
    Dimension 3 equals Dimension 1 = true

    ```

**注意:**上述程序可能无法在在线 IDE 中运行。请使用离线编译器。

**参考:**[https://docs . Oracle . com/javase/8/JavaFX/API/JavaFX/geometry/dimension 2d . html](https://docs.oracle.com/javase/8/javafx/api/javafx/geometry/Dimension2D.html)