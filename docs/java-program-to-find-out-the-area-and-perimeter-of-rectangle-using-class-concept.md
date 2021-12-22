# 利用类概念

求矩形面积和周长的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-找出矩形的面积和周长-使用类-概念/](https://www.geeksforgeeks.org/java-program-to-find-out-the-area-and-perimeter-of-rectangle-using-class-concept/)

**周长**是形状轮廓的长度。要找到矩形或正方形的**周长**，你必须加上所有四条边的长度。在这种情况下，x 是矩形的长度，而 y 是矩形的宽度。**区域**是对形状表面的测量。

这里的主要任务是创建一个类，用于查找矩形的面积和周长。

**用矩形面积和矩形周长的公式:**

```
Area of Rectangle = Length * Breadth
```

```
Perimeter of Rectangle = 2 * (Length + Breadth)
```

> **示例:**
> 
> 长度= 10
> 
> 宽度= 20
> 
> 矩形面积= 200
> 
> 矩形的周长= 60

**进场:**

*   首先，我们将创建一个名为矩形的类，在其中我们将定义可变的长度和宽度。面积和周长法计算矩形的面积和周长。
*   然后我们将创建另一个类，在其中我们将创建一个主方法。
*   在主方法中，矩形的对象被创建，使用它我们可以调用赋值给矩形类的变量，在赋值之后，矩形类的方法将被调用来计算矩形的面积和周长。
*   矩形类的两个方法都将使用长度和宽度的值，这些值是我们使用该类的对象从主方法传递过来的。结果会被打印出来。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to create a class to
// print the area and perimeter of a
// rectangle

import java.util.*;

// Rectangle Class File
public class Rectangle {

    // Variable of data type double
    double length;
    double width;

    // Area Method to calculate the area of Rectangle
    void Area()
    {
        double area;
        area = this.length * this.width;
        System.out.println("Area of rectangle is : "
                           + area);
    }

    // Perimeter Method to calculate the Perimeter of
    // Rectangle
    void Perimeter()
    {
        double perimeter;
        perimeter = 2 * (this.length + this.width);
        System.out.println("Perimeter of rectangle is : "
                           + perimeter);
    }
}

 class Use_Rectangle {

    public static void main(String args[])
    {
        // Object of Rectangle class is created
        Rectangle rect = new Rectangle();

        // Assigning the value in the length variable of
        // Rectangle Class
        rect.length = 15.854;

        // Assigning the value in the width variable of
        // Rectangle Class
        rect.width = 22.65;

        System.out.println("Length = " + rect.length);
        System.out.println("Width = " + rect.width);

        // Calling of Area method of Rectangle Class
        rect.Area();

        // Calling of Perimeter method of Rectangle Class
        rect.Perimeter();
    }
}
```

**Output**

```
Length = 15.854
Width = 22.65
Area of rectangle is : 359.09309999999994
Perimeter of rectangle is : 77.008
```