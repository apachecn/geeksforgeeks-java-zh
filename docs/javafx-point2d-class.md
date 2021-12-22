# JavaFX | Point2D 类

> 原文:[https://www.geeksforgeeks.org/javafx-point2d-class/](https://www.geeksforgeeks.org/javafx-point2d-class/)

Point2D 类是 JavaFX 的一部分。这个类定义了空间中的一个二维点。点 2D 类通过它的 x，y 坐标来表示 2D 点。它继承了 *java.lang.Object* 类。
**本班建造师:**

*   **点 2D(双 x，双 y)** :用指定的 x 和 y 坐标创建点 2D 对象。

**常用方法:**

<figure class="table">

| 方法 | 说明 |
| --- | --- |
| 距离(双 x1，双 y1) | 计算该点和点(x1，y1)之间的距离。 |
| 距离(点 2D p) | 计算该点和点 p 之间的距离。 |
| 等于(java.lang.Object obj) | 返回该对象是否等于指定对象 |
| getX（） | 返回点的 x 坐标 |
| 盖蒂（） | 返回点的 y 坐标 |
| hashCode() | 返回该点的哈希代码值。 |

</figure>

以下程序将说明 Point2D 类的使用:

**1.Java 程序创建一个点 2D 对象并显示其坐标并找到其与原点的距离:**在该程序中，我们使用其 x，y 坐标作为参数创建了一个名为 *point2d_1* 的 point 2D 对象。我们将使用 *getX()* 、 *getY()* 函数获得 x、y 的值，然后显示它。我们也在计算这些点离原点的距离。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to create a point 2D
// object and display its coordinates
// and find its distance from origin
import javafx.geometry.Point2D;

public class Point2D_1 {

    // Main Method
    public static void main(String args[])
    {

        // Create a point2D object
        Point2D point2d_1 = new Point2D(20.0f, 150.0f);

        double x, y;

        // get the coordinates of the point
        x = point2d_1.getX();
        y = point2d_1.getY();

        // display the coordinates of the point
        System.out.println("x coordinate = " + x
                      + ", y coordinate = " + y);

        // print its distance from origin
        System.out.println("distance from origin = "
                        + point2d_1.distance(0, 0));
    }
}
```

**输出:**

```java
x coordinate = 20.0, y coordinate = 150.0
distance from origin = 151.32745950421557
```

**2.Java 程序创建 3 个 Point2D 对象，并显示它们的坐标和与原点的距离，并检查这 3 个点中的哪一个相似以及它们在两个点之间的距离:**在该程序中，我们通过传递其 x，y 坐标作为参数来创建名为 *point2d_1* 、 *point2d_2* 、 *point2d_3* 的 3 个 Point2D 对象。我们使用 *getX()* 、 *getY()* 函数得到 x、y 值，然后显示出来。我们还计算了该点与原点的距离，并显示了三个点的距离。我们还使用 *equals()* 功能显示任意两点是否相等，使用 *distance()* 功能显示两点之间的距离。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to create 3 Point2D objects and display
// their coordinates and distance from origin and
// check which of the 3 points are similar and
// their distances between two points
import javafx.geometry.Point2D;

public class Point2D_2 {

    // Main Method
    public static void main(String args[])
    {

        // Create three point2D objects
        Point2D point2d_1 = new Point2D(120.0f, 50.0f);
        Point2D point2d_2 = new Point2D(120.0f, 50.0f);
        Point2D point2d_3 = new Point2D(200.0f, 120.0f);

        // Display the coordinates of the 3 points
        display(point2d_1);
        display(point2d_2);
        display(point2d_3);

        // Check whether any point is equal to other or not
        System.out.println("Point 1 equals Point 2 = "
                        + point2d_1.equals(point2d_2));

        System.out.println("Point 2 equals Point 3 = "
                        + point2d_2.equals(point2d_3));

        System.out.println("Point 3 equals Point 1 = "
                        + point2d_3.equals(point2d_1));

        // distance between two points
        System.out.println("Distance between point 1 and point 2 = "
                                  + point2d_1.distance(point2d_2));

        System.out.println("Distance between point 2 and point 3 = "
                                   + point2d_2.distance(point2d_3));

        System.out.println("Distance between point 3 and point 1 = "
                                    + point2d_3.distance(point2d_1));
    }

    // display method
    public static void display(Point2D point2d)
    {

        double x, y;

        // get the coordinates of the point
        x = point2d.getX();
        y = point2d.getY();

        // display the coordinates of the point
        System.out.println("x coordinate = " + x
                      + ", y coordinate = " + y);

        // print its distance from origin
        System.out.println("Distance from origin = "
                          + point2d.distance(0, 0));
    }
}
```

**输出:**

```java
x coordinate = 120.0, y coordinate = 50.0
Distance from origin = 130.0
x coordinate = 120.0, y coordinate = 50.0
Distance from origin = 130.0
x coordinate = 200.0, y coordinate = 120.0
Distance from origin = 233.23807579381202
Point 1 equals Point 2 = true
Point 2 equals Point 3 = false
Point 3 equals Point 1 = false
Distance between point 1 and point 2 = 0.0
Distance between point 2 and point 3 = 106.30145812734649
Distance between point 3 and point 1 = 106.30145812734649
```

**注意:**上述程序可能无法在在线 IDE 中运行。请使用离线编译器。
**参考:**[https://docs . Oracle . com/JavaFX/2/API/JavaFX/geometry/point2d . html](https://docs.oracle.com/javafx/2/api/javafx/geometry/Point2D.html)