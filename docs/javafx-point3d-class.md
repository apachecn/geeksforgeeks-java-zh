# JavaFX | Point3D 类

> 原文:[https://www.geeksforgeeks.org/javafx-point3d-class/](https://www.geeksforgeeks.org/javafx-point3d-class/)

***Point3D*** 类是 JavaFX 的一部分。这个类定义了三维空间中的一个三维点。Point3D 类通过其 x，y，z 坐标来表示 3D 点。

**该类的构造函数为:**

*   **点 3D(双 x，双 y，双 z)** :使用指定的坐标创建点 3D 对象。

**常用方法:**

<figure class="table">

| 方法 | 说明 |
| --- | --- |
| 距离(双 x，双 y，双 z) | 计算该点和指定点之间的距离 |
| 距离(点 3D p) | 计算该点和指定的点三维对象之间的距离 |
| 等于(java.lang.Object o) | 返回该点的哈希代码值。 |
| getX（） | 返回 x 坐标 |
| 盖蒂（） | 返回 y 坐标 |
| getZ() | 返回 z 坐标 |
| hashCode() | 返回此 Point3D 对象的哈希代码。 |

</figure>

以下程序将说明 Point3D 类的使用:

**1。创建一个 Point3D 对象并显示其坐标并找到其与原点的距离的 Java 程序:**在这个程序中，我们通过传递其 x，y，z 坐标作为参数来创建一个名为 point3d_1 的 Point3D 对象。我们使用 *getX()* 、 *getY()* 、 *getZ()* 函数得到 x，y，z 参数并显示出来。我们还计算该点离原点的距离，并显示它。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to create a point 3D
// object and display its coordinates
// and find its distance from origin
import javafx.geometry.Point3D;

public class Point3D_1 {

    // Main Method
    public static void main(String args[])
    {

        // Create a point3D object
        Point3D point3d_1 = new Point3D(20.0f, 50.0f, 70.0f);

        double x, y, z;

        // get the coordinates of the point
        x = point3d_1.getX();
        y = point3d_1.getY();
        z = point3d_1.getZ();

        // display the coordinates of the point
        System.out.println("x coordinate = " + x
                            + ", y coordinate = "
                            + y + ", z coordinate = " + z);

        // print its distance from origin
        System.out.println("Distance From Origin = "
                     + point3d_1.distance(0, 0, 0));
    }
}
```

**输出:**

```
x coordinate = 20.0, y coordinate = 50.0, z coordinate = 70.0
Distance From Origin = 88.31760866327846
```

**2。Java 程序创建 3 个 Point3D 对象并显示它们的坐标和与原点的距离，并检查这 3 个点中的哪一个是相似的以及它们在两个点之间的距离:**在这个程序中，我们通过传递其 x，y，z 坐标作为参数来创建名为 point3d_1，point3d_2，point3d_3 的 3 个 Point3D 对象。我们使用 *getX()* 、 *getY()* 、 *getZ()* 函数得到 x，y，z 参数并显示出来。我们还计算了该点与原点的距离，并显示了三个点的距离。我们还使用 *equals()* 函数显示任意两点是否相等，并使用距离函数显示两点之间的距离。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to create 3 Point3D objects and
// display their coordinates and distance from
// origin and check which of the 3 points are
// similar and their distances between two points
import javafx.geometry.Point3D;

public class Point3D_2 {

    // Main Method
    public static void main(String args[])
    {

        // create three point3D objects
        Point3D point3d_1 = new Point3D(20.0f, 50.0f, 70.0f);
        Point3D point3d_2 = new Point3D(20.0f, 50.0f, 70.0f);
        Point3D point3d_3 = new Point3D(200.0f, 20.0f, 90.0f);

        // display the coordinates of the 3 points
        display(point3d_1);
        display(point3d_2);
        display(point3d_3);

        // check whether any point is equal to other or not
        System.out.println("Point 1 equals point 2 = "
                       + point3d_1.equals(point3d_2));

        System.out.println("Point 2 equals point 3 = "
                       + point3d_2.equals(point3d_3));

        System.out.println("Point 3 equals point 1 = "
                        + point3d_3.equals(point3d_1));

        // distance between two points
        System.out.println("Distance between point 1 and point 2 = "
                                  + point3d_1.distance(point3d_2));

        System.out.println("Distance between point 2 and point 3 = "
                                   + point3d_2.distance(point3d_3));

        System.out.println("Distance between point 3 and point 1 = "
                                  + point3d_3.distance(point3d_1));
    }

    // Display Method
    public static void display(Point3D point3d)
    {

        double x, y, z;

        // get the coordinates of the point
        x = point3d.getX();
        y = point3d.getY();
        z = point3d.getZ();

        // display the coordinates of the point
        System.out.println("x coordinate = " + x
                           + ", y coordinate = "
                           + y + ", z coordinate = " + z);

        // print its distance from origin
        System.out.println("Distance From Origin = " +
                            point3d.distance(0, 0, 0));
    }
}
```

**输出:**

```
x coordinate = 20.0, y coordinate = 50.0, z coordinate = 70.0
Distance From Origin = 88.31760866327846
x coordinate = 20.0, y coordinate = 50.0, z coordinate = 70.0
Distance From Origin = 88.31760866327846
x coordinate = 200.0, y coordinate = 20.0, z coordinate = 90.0
Distance From Origin = 220.22715545545242
Point 1 equals point 2 = true
Point 2 equals point 3 = false
Point 3 equals point 1 = false
Distance between point 1 and point 2 = 0.0
Distance between point 2 and point 3 = 183.5755975068582
Distance between point 3 and point 1 = 183.5755975068582
```

**注意:**上述程序可能无法在在线 IDE 中运行。请使用离线编译器。

**参考:**[https://docs . Oracle . com/JavaFX/2/API/JavaFX/geometry/point3d . html](https://docs.oracle.com/javafx/2/api/javafx/geometry/Point3D.html)