# Java 程序演示一个没有参数但有返回类型的方法

> 原文:[https://www . geesforgeks . org/Java-program-to-installation-a-method-不带参数但带有返回类型/](https://www.geeksforgeeks.org/java-program-to-illustrate-a-method-without-parameters-but-with-return-type/)

任务是说明一个不包含任何参数但应该返回值的方法。方法用于将一个完整的程序分解成个可以逐个执行的模块。考虑任何随机形状来说明:圆形

**例:**首先要创建一个名为‘圆’的类**，**，然后借助这个类，它可以计算圆的面积和周长。

1.  面积计算
2.  周长计算

在类 Circle 中，我们将声明一个名为 radius 的变量来获取用户的半径值，这样通过使用这个半径值，我们将能够计算圆的面积和周长。现在，为了计算面积和周长，我们需要创建两个单独的方法，称为**面积()**和**周长()**，这两个方法没有将任何值作为参数，但肯定会返回一些值，这种方法返回的值是圆的面积和周长的最终值。这些方法将在变量值的帮助下计算后返回值。最重要的是计算面积和周长，使用这些方法首先需要的是调用那些被称为调用函数的方法，为此我们必须创建一个 Circle 类的对象，因为在主方法中，我们想要访问它们， 另一个类的方法因此我们需要使包含我们的方法的类的对象**区域()**和**圆周()**并且通过使用类的对象**圆**，我们将容易地调用方法并且那些方法将返回一些值，并且我们将通过使用我们的预定义函数来显示它。

**语法:**

```
 class name
    {
        datatype MethodName()
        {
            statements....
            ..
            ..
            return value;
        }
    }
```

**实施:**

**例 1:** 面积计算

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate a Method
// without Parameters but with Return Type

// Importing generic java classes
import java.util.*;
// Importing Scanner class if
// input is from user (optional)*/
import java.util.Scanner;

// Auxiliary Class (Sample class)
// class which contains the method area()
class Circle {

    // initializing the variable radius
    double radius;

    // functions calculating area
    double area()
    {
        double r = 7;

        // Area of circle will be calculate and
        // will store into the variable ar
        double ar = 3.14 * r * r;

        // Method returning the area
        return ar;
    }
}

// Main Class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Object of circle is created
        Circle c = new Circle();

        // Big type variable to hold area value
        double area;

        // Area method is called and
        // will store the value in variable area
        area = c.area();

        // Printing area of circle
        System.out.println("Area of circle is : " + area);
    }
}
```

**Output**

```
Area of circle is : 153.86
```

**例 2:** 周长计算

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate a Method
// without Parameters but with Return Type

// Importing java generic classes
import java.util.*;

class Circle {

    double radius;

    // method which does not contain
    // parameter but will return
    // the circumference of circle
    double circumference()
    {

        double r = 7;
        double circum = 2 * 3.14 * r;

        // Method returning the circumference of circle
        return circum;
    }
}
public class GFG {

    public static void main(String args[])
    {
        // the object of circle is created to call the
        // method circumference()
        Circle c = new Circle();
        double circum;

        // the value returned from method will store into
        // the variable circum
        circum = c.circumference();
        System.out.println("Circumference of circle is : "
                           + circum);
    }
}
```

**Output**

```
Circumference of circle is : 43.96
```