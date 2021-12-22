# Java 数学 sin()方法示例

> 原文:[https://www . geesforgeks . org/Java-math-sin-method-examples/](https://www.geeksforgeeks.org/java-math-sin-method-examples/)

**java.lang.Math.sin()** 返回 0.0 到π之间的三角正弦值。如果参数是 NaN 或无穷大，那么结果就是 NaN。如果该参数为零，则结果是一个零，其符号与该参数相同。返回值将介于-1 和 1 之间。

**语法:**

```java
public static double sin(double a) ;
```

**参数**:要返回正弦值的值。

**返回类型:**此方法返回参数的正弦值。

**实施:**

在这里，我们将提出两个例子，其中一个简单地展示第一个例子的 [*Math.sin()*](https://www.geeksforgeeks.org/java-math-sin-method-examples/) *方法*[*Java . lang 包*](https://www.geeksforgeeks.org/java-lang-package-java/) 方法和次要 be edge case 的工作。

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working
// of java.lang.Math.sin() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {
        double a = 30;

        // converting values to radians
        double b = Math.toRadians(a);

        System.out.println(Math.sin(b));

        a = 45;

        // converting values to radians
        b = Math.toRadians(a);

        System.out.println(Math.sin(b));

        a = 60;

        // converting values to radians
        b = Math.toRadians(a);

        System.out.println(Math.sin(b));

        a = 90;

        // converting values to radians
        b = Math.toRadians(a);

        System.out.println(Math.sin(b));
    }
}
```

**Output:** 

```java
0.49999999999999994
0.7071067811865475
0.8660254037844386
1.0
```

**例 2**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of Math.cos() method
// of java.lang package considering infinity case

// Importing classes from java.lang package
import java.lang.Math;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        double positiveInfinity = Double.POSITIVE_INFINITY;
        double negativeInfinity = Double.NEGATIVE_INFINITY;
        double nan = Double.NaN;
        double result;

        // Here argument is negative infinity,
        // output will be NaN
        result = Math.sin(negativeInfinity);
        System.out.println(result);

        // Here argument is positive infinity,
        // output will also be NaN
        result = Math.sin(positiveInfinity);
        System.out.println(result);

        // Here argument is NaN, output will be NaN
        result = Math.sin(nan);
        System.out.println(result);
    }
}
```

**Output:** 

```java
NaN
NaN
NaN
```