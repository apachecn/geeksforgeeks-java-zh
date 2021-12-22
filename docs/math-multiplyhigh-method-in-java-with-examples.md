# Java 中的数学 multiplyHigh()方法，带示例

> 原文:[https://www . geesforgeks . org/math-multiplyhigh-method-in-Java-with-examples/](https://www.geeksforgeeks.org/math-multiplyhigh-method-in-java-with-examples/)

**数学类**的 **multiplyHigh(长 x，长 y)** 方法用于从两个 64 位因子的 128 位乘积中返回最高有效的 64 位。此方法采用两个长值作为输入，一个长值是 64 位数字。此方法将两个长值相乘，并从乘积结果中返回最高有效的 64 位，其长度可能为 128 位。

**语法:**

```java
public static long multiplyHigh(long x, long y)
```

**参数:**这个方法接受两个长的 **x，y** 作为参数，其中 x 和 y 是我们想要相乘的参数。

**返回值:**此方法从两个 64 位数字的 128 位乘积**返回最高有效的 64 位长值，即 X * Y** 。

**注:**此法在 **JDK 9 中增加。因此，它不会在在线集成开发环境中运行。**

**下面的程序说明了 multiplyHigh()方法:**

 ****程序 1:**

```java
// Java program to demonstrate
// multiplyHigh() method of Math class

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // two long values
        long a = 45267356745l, b = 45676556735l;

        // apply multiplyHigh method
        long c = Math.multiplyHigh(a, b);

        // print result
        System.out.println(a + " * "
                           + b + " = "
                           + c);
    }
}
```

**输出:**

```java
45267356745 * 45676556735 = 112

```

**程序 2:** 乘法二长包含 long。最大值。

```java
// Java program to demonstrate
// multiplyHigh() method of Math class

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // two Integer values
        long a = Long.MAX_VALUE, b = Long.MAX_VALUE;

        // apply multiplyHigh method
        long c = Math.multiplyHigh(a, b);

        // print result
        System.out.println(a + " * "
                           + b + " = " + c);
    }
}
```

**输出:**

```java
9223372036854775807 * 9223372036854775807 = 4611686018427387903

```** 参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/lang/math . html # multiplyHigh(long，long)](https://docs.oracle.com/javase/10/docs/api/java/lang/Math.html#multiplyHigh(long, long))