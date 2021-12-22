# Java 中的数学 multiplyFull()方法，带示例

> 原文:[https://www . geesforgeks . org/math-multiply full-method-in-Java-with-examples/](https://www.geeksforgeeks.org/math-multiplyfull-method-in-java-with-examples/)

**数学类**的 **multiplyFull(int x，int y)** 方法用于返回两个参数的精确数学乘积。在参数中，提供了两个整数值，这两个数字的乘积用该方法返回的 long 类型表示。

**语法:**

```java
public static long multiplyFull(int x, int y)
```

**参数:**该方法接受两个整数 **x，y** 作为参数，其中 x 和 y 是要相乘的参数。

**返回值:**该方法返回长类型值，即**X * Y**的精确乘积。

**注:**JDK 9 增加此方法。因此，它不会在联机集成开发环境中运行。

下面的程序说明了 multiplyFull()方法:

**程序 1:**

```java
// Java program to demonstrate
// multiplyFull() method of Math class

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // two Integer values
        int a = 367428, b = 1374;

        // apply multiplyFull method
        long c = Math.multiplyFull(a, b);

        // print result
        System.out.println(a + " * "
                           + b + " = " + c);
    }
}
```

**输出:**

```java
367428 * 1374 = 504846072

```

**程序 2:** 两个整数相乘包含整数。最大值。

```java
// Java program to demonstrate
// multiplyFull() method of Math class

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // two Integer values
        int a = Integer.MAX_VALUE;
        int b = Integer.MAX_VALUE;

        // apply multiplyFull method
        long c = Math.multiplyFull(a, b);

        // print result
        System.out.println(a + " * "
                           + b + " = " + c);
    }
}
```

**输出:**

```java
2147483647 * 2147483647 = 4611686014132420609

```

参考文献:
[https://docs . Oracle . com/javase/10/docs/API/Java/lang/math . html # multiplyFull(int，int)](https://docs.oracle.com/javase/10/docs/api/java/lang/Math.html#multiplyFull(int, int))