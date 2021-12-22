# Java 程序使用方法重载寻找圆的面积

> 原文:[https://www . geesforgeks . org/Java-程序-查找-使用方法的圆区域-重载/](https://www.geeksforgeeks.org/java-program-to-find-area-of-circle-using-method-overloading/)

一个**圆**是一个简单的形状，由平面上与一个称为圆心的点等距的所有点组成。在本文中，我们将学习如何使用方法重载来查找圆的面积。

术语:

*   **方法重载:** [方法重载](https://www.geeksforgeeks.org/overloading-in-java/)允许不同的方法具有相同的名称，但签名不同，其中签名可能因输入参数的数量或输入参数的类型或两者而异。
*   **面积:**表示二维图形或形状在平面上的范围的量称为面积。
*   **半径:**从圆心到圆的任意一点的线段称为半径。
*   **直径:**端点位于圆上并穿过圆心的线段称为圆的直径。它也被称为圆上任意两点之间的最大距离。

#### 圆的面积

圆的面积是圆半径的平方和圆周率的乘积。我们可以简单地用下面的公式计算圆的面积:

*   **使用圆的半径:**

![](img/9914423defd6ec6bd7b7c0dc67927b47.png)

**公式:**

> 圆的面积:A = π * r <sup>2</sup>

这里，r 是圆的半径。

*   **使用圆的直径:**

![](img/907b7bab09219f526ac936661d8a535c.png)

**公式:**

> 圆的面积:A = (π / 4) * d <sup>2</sup>

这里，r 是圆的半径。

> **注:**Java 中 PI 的值是 3.1415926535897

下面是上述方法的实现:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to find the area of
// the circle using Method Overloading

import java.io.*;

class Circle {

    static final double PI = Math.PI;

    // Overloaded Area() function to
    // calculate the area of the circle.
    // It takes one double parameter
    void Area(double r)
    {
        double A = PI * r * r;

        System.out.println("Area of the circle is :" + A);
    }

    // Overloaded Area() function to
    // calculate the area of the circle.
    // It takes one float parameter
    void Area(float r)
    {
        double A = PI * r * r;

        System.out.println("Area of the circle is :" + A);
    }
}

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating object of Circle class
        Circle obj = new Circle();

        // Calling function
        obj.Area(5);
        obj.Area(2.5);
    }
}
```

**Output**

```
Area of the circle is :78.53981633974483
Area of the circle is :19.634954084936208
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to find the area of
// the circle when the diameter is given
// using Method Overloading

import java.io.*;

class Circle {

    static final double PI = Math.PI;

    // Overloaded Area() function to
    // calculate the area of the circle.
    // It takes one double parameter
    void Area(double D)
    {
        double A = (PI / 4) * D * D;

        System.out.println("Area of the circle is :" + A);
    }

    // Overloaded Area() function to
    // calculate the area of the circle.
    // It takes one float parameter
    void Area(float D)
    {
        double A = (PI / 4) * D * D;

        System.out.println("Area of the circle is :" + A);
    }
}

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating object of Circle class
        Circle obj = new Circle();

        // Calling function
        obj.Area(10);
        obj.Area(20.4);
    }
}
```

**Output**

```
Area of the circle is :78.53981633974483
Area of the circle is :326.851299679482
```