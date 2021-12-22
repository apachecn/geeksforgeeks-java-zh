# Java 数学 min()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-math-min-method-examples/](https://www.geeksforgeeks.org/java-math-min-method-examples/)

**Java.lang.math.min()** 函数是 Java 中的一个内置函数，返回两个数字的最小值。参数有 int、double、float 和 long。如果一个负数和一个正数作为参数传递，则生成负结果。如果传递的两个参数都是负的，那么结果会生成具有较大幅度的数字。
**语法:**

```java
dataType min(dataType num1, dataType num2)
The datatypes can be int, float, double or long.

Parameters : The function accepts two parameters num1 and num2 
among which the minimum is returned
```

**返回值:**函数返回两个数字的最小值。数据类型将与参数的数据类型相同。
下面是函数 min()的例子:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the
// use of min() function
// two double data-type numbers are passed as argument
public class Gfg {

    public static void main(String args[])
    {
        double a = 12.123;
        double b = 12.456;

        // prints the minimum of two numbers
        System.out.println(Math.min(a, b));
    }
}
```

**输出:**

```java
12.123
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate the
// use of min() function
// when one positive and one
// negative integers are passed as argument
public class Gfg {

    public static void main(String args[])
    {
        int a = 23;
        int b = -23;

        // prints the minimum of two numbers
        System.out.println(Math.min(a, b));
    }
}
```

**输出:**

```java
-23
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// the use of min() function
// when two negative integers
// are passed as argument
public class Gfg {

    public static void main(String args[])
    {
        int a = -25;
        int b = -23;

        // prints the minimum of two numbers
        System.out.println(Math.min(a, b));
    }
}
```

**输出:**

```java
-25
```

如果你想在代码中多次找到两个数字的最小值，那么每次写完整的 **Math.min()** 往往会很繁琐。所以这里一个更短更省时的方法是直接将 **java.lang.Math.min** 导入为静态，然后只使用 **min()** 代替完整的 **Math.min()** 。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import static java.lang.Math.min;

class GFG {
    public static void main(String[] args)
    {
        int a = 3;
        int b = 4;
        System.out.println(min(a, b));
    }
}
```

**Output**

```java
3

```