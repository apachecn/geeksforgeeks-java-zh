# Java Math max()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-math-max-method-examples/](https://www.geeksforgeeks.org/java-math-max-method-examples/)

**Java.lang.math.max()** 函数是 Java 中的一个内置函数，最多返回两个数字。参数有 int、double、float 和 long。如果一个负数和一个正数作为参数传递，则生成正结果。如果传递的两个参数都是负的，那么结果会生成具有较低幅度的数字。

**语法:**

```java
dataType max(dataType num1, dataType num2)
The datatypes can be int, float, double or long.

Parameters : The function accepts two parameters num1 and num2 
among which the maximum is returned

```

**返回值:**函数返回两个数字的最大值。数据类型将与参数的数据类型相同。

下面给出了函数 max()的例子

```java
// Java program to demonstrate the use of max() function
// when two double data-type numbers are
// passed as arguments
public class Gfg {

    public static void main(String args[])
    {
        double a = 12.123;
        double b = 12.456;

        // prints the maximum of two numbers
        System.out.println(Math.max(a, b));
    }
}
```

**输出:**

```java
12.456

```

```java
// Java program to demonstrate the use of max() function
// when one positive and one negative
// integers are passed as argument
public class Gfg {

    public static void main(String args[])
    {
        int a = 23;
        int b = -23;

        // prints the maximum of two numbers
        System.out.println(Math.max(a, b));
    }
}
```

**输出:**

```java
23

```

```java
// Java program to demonstrate the use of max() function
// when two negative integers are passed as argument.
public class Gfg {

    public static void main(String args[])
    {
        int a = -25;
        int b = -23;

        // prints the maximum of two numbers
        System.out.println(Math.max(a, b));
    }
}
```

**输出:**

```java
-23

```