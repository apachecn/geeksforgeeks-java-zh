# 将双精度转换为字符串的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到转换-双字符串/](https://www.geeksforgeeks.org/java-program-to-convert-double-to-string/)

**问题陈述:**使用内置函数在 java 中将双数据类型转换为字符串的 Java 程序。这样做的主要目标是存储大的数字流，这些数字流来自于即使是数据类型也无法存储数字流的地方。

插图:

```
Input: 22.098 // Double Data
Output: 22.098 // String Data

Input: 123.456 // Double Data
Output: 123.456 // String Data
```

将双精度数据转换为字符串数据有不同的方法。两种标准方法如下:

**接近:**

*   使用 [String.valueOf()](https://www.geeksforgeeks.org/data-conversion-using-valueof-method-java/) 方法
*   使用 Double.toString()方法

**方法 1:使用** [**弦.值**](https://www.geeksforgeeks.org/data-conversion-using-valueof-method-java/) **法**

**String.valueOf()** 是 java 中的一个方法，它只是简单地将下面给定的参数类型化为字符串，因为它是 java 中的一个内置方法 os String 类。请记住，在使用此方法执行一次后，任何执行都可能会改变结果，因为它将导致无指导的输出。

**示例:**

```
int a = 10, int b = 20;
String s1 = String.valueOf(a);
String s2 = String.valueOf(b);
System.out.println(s1+s2);      || Output: 30       || Addition of a and b via s1+s2
System.out.println(s1+s2);      || Output: 1020     || Concatenation of s1 & s2
```

**参数**可以保持:

```
object, float, char, double, int, float, long, char[]
```

**返回类型:**

```
Always String
```

这个方法是一个内置的方法，已经存在于 java 的目录中，它返回前面讨论过的字符串对象。下面是一个用 java 实现的例子:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert double data to a string data

// Importing Libraries
import java.util.*;
import java.io.*;

class GFG {

    // Main driver function
    public static void main(String[] args)
    {
        // Declaring the number
        double number = 123.456;

        // Converting Double data to String data
        String output = String.valueOf(number);

        // Printing the string data
        System.out.println(output);
    }
}
```

**输出:**

```
123.456
```

**方法二:使用 Double.toString()方法**

**Double.toString():** 在 java 中每当调用 print 时，总是直接或间接地调用 java 中 Object Class 的 toString()方法。即使没有使用这个内置函数，并且打印了双精度数字，也会调用 toString()方法。字符串是 Java 中的一个类。java 中的所有类都是从[对象](https://www.geeksforgeeks.org/object-class-in-java/)类派生的。每当访问未创建 java 程序中对象的打印时。每当用户用 java 给出打印命令时，总是调用 java 中 [Object](https://www.geeksforgeeks.org/object-class-in-java/) 类的 toString()方法。

因此，现在如果用户已经创建了自己类型的对象，那么就迫切需要重写现有的 toString()方法，以便在调用 print 命令时重写 toString()方法。如果用户没有创建对象，那么就知道它已经是一个内置的方法，已经存在于 java 的目录中，它将把双精度数据转换成字符串值。

下面的示例描述了该方法的使用:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert double data to a string data

// Importing Libraries
import java.util.*;
import java.io.*;

class GFG {

    // Main driver function
    public static void main(String[] args)
    {
        // Declaring the number
        double number = 123.456;

        // Converting Double data to String data
        String output = Double.toString(number);

        // Printing the string data
        System.out.println(output);
    }
}
```

**输出:**

```
123.456
```