# Java 中的数学 fma()方法，带示例

> 原文:[https://www . geesforgeks . org/math-fma-method-in-Java-with-examples/](https://www.geeksforgeeks.org/math-fma-method-in-java-with-examples/)

在数学类中，根据传递给它的参数，有两种类型的 fma()方法。

这些方法是:

### fma(双 a、双 b、双 c):

**数学类**的这个方法是用第三个双精度相加返回前两个双精度的精确乘积，然后将结果四舍五入到最近的双精度。舍入是使用最接近的偶数舍入模式完成的。假设 a，b，c 是三个双精度数，那么 a * b + c 被计算为一个正则浮点表达式，涉及两个舍入误差，第一个用于 a * b 的乘法运算，第二个用于与 c 的乘积结果的加法运算。

这种方法的一些特殊情况是:

*   如果这三个中的任何一个参数是 NaN，那么结果就是 NaN。
*   如果前两个参数中的一个是无穷大，另一个是零，那么结果就是 NaN。
*   如果两个参数的精确乘积是无穷大，而第三个参数是符号相反的无穷大，那么结果就是 NaN。

**例:**

```java
Input: a = 2.0, b = 3.0, c = 3.0
Output: 9.0
    As 2.0 * 3.0 + 3.0 = 9.0

Input: a = 9.20, b = 6.30, c = 4.10
Output: 62.059999999999995 
    As 9.20 * 6.30 + 4.10 = 62.059999999999995 

```

**语法:**

```java
public static double fma(double a, double b, double c)
```

**参数:**此方法接受三个双精度 **a、b、c** 作为参数，其中 a 和 b 是要相乘的自变量，c 是要与乘积相加的自变量。

**返回值:**该方法计算 **a * b + c** 后返回四舍五入的双精度值，范围和精度不限。

**注:**本法在 **JDK 9 号中增加。**因此它不会在在线集成开发环境中运行。

以下程序说明了 fma()方法:

**节目 1:**

```java
// Java program to demonstrate the fma() Method.

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // three double values
        double a = 9.20, b = 6.30, c = 4.10;

        // apply fma method
        double d = Math.fma(a, b, c);

        // print result
        System.out.println(a + " * " + b
                           + " + " + c
                           + " = " + d);
    }
}
```

**输出:**

```java
9.2 * 6.3 + 4.1 = 62.059999999999995

```

**节目 2:**

```java
// Java program to demonstrate the fma() Method.

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // three double values
        double a = 19.20, b = 16.30, c = 44.10;

        // apply fma method
        double d = Math.fma(a, b, c);

        // print result
        System.out.println(a + " * " + b
                           + " + " + c
                           + " = " + d);
    }
}
```

**输出:**

```java
19.2 * 16.3 + 44.1 = 357.06

```

### fma(浮子 a、浮子 b、浮子 c):

**数学类**的这个方法和 fma(双 a，双 b，双 c)的工作原理一样，不同的是它以 float 为属性，以 return float 为返回值。所以我们可以说，这个方法返回前两个参数(浮点值)加上第三个参数(浮点值)的精确乘积，然后将结果舍入到最近的浮点值。舍入是使用最接近的偶数舍入模式完成的。假设 a，b，c 是三个浮点数，那么 a * b + c 的计算是一个正则浮点表达式，涉及两个舍入误差，第一个用于 a * b 的乘法运算，第二个用于与 c 的乘积结果的加法运算。

**例** :

```java
Input: a = 29.20f, b = 18.40f, c = 43.10f;
Output: 580.38 
    As 29.20f * 18.40f + 43.10f = 580.38

Input: a = 9.20f, b = 6.30f, c = 4.10f;
Output: 62.059999999999995f 
    As 9.20f * 6.30f + 4.10f = 62.059999999999995f

```

**语法:**

```java
public static double fma(float a, float b, float c)
```

**参数:**这个方法接受三个浮点数 **a，b，c** 作为参数，其中 a 和 b 是我们要相乘的自变量，c 是我们要与乘积相加的自变量。

**返回值:**该方法计算 **a * b + c** 后返回四舍五入的浮点值，范围和精度不限。

**注:**本法在 **JDK 9 号中增加。**因此它不会在在线集成开发环境中运行。

以下程序说明了 fma()方法:

**节目 1:**

```java
// Java program to demonstrate
// the fma() Method.

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // three double values
        float a = 29.20f, b = 18.40f, c = 43.10f;

        // apply fma method
        float d = Math.fma(a, b, c);

        // print result
        System.out.println(a + " * " + b
                           + " + " + c
                           + " = " + d);
    }
}
```

**输出:**

```java
29.2 * 18.4 + 43.1 = 580.38

```

**节目 2:**

```java
// Java program to demonstrate
// the fma() Method.

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // three double values
        float a = 49.29f, b = 28.58f, c = 33.63f;

        // apply fma method
        float d = Math.fma(a, b, c);

        // print result
        System.out.println(a + " * " + b
                           + " + " + c
                           + " = " + d);
    }
}
```

**输出:**

```java
49.29 * 28.58 + 33.63 = 1442.3383

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/lang/math . html # fma(double、double、double)](https://docs.oracle.com/javase/10/docs/api/java/lang/Math.html#fma(double, double, double)) ，[https://docs . Oracle . com/javase/10/docs/API/Java/lang/math . html # fma(float、float、float)](https://docs.oracle.com/javase/10/docs/api/java/lang/Math.html#fma(float, float, float))