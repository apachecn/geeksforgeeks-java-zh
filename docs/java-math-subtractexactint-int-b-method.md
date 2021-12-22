# Java 数学减法精确(int a，int b)方法

> 原文:[https://www . geesforgeks . org/Java-math-减法-int-b-method/](https://www.geeksforgeeks.org/java-math-subtractexactint-int-b-method/)

**java.lang.Math .减法精确()**是 java 中的一个内置数学函数，它返回
参数的差值。如果结果溢出一个 int，它将引发异常。由于减法精确(int a，int b)是**静态的**，所以不需要创建
对象。

**语法:**

```
public static int subtractExact(int a, int b)
Parameter :
 a : the first value
 b : the second value to be subtracted from the first
Return :
This method returns the difference of the arguments .
Exception :
It throws ArithmeticException - if the result overflows an int

```

**示例:**展示 **java.lang.Math .减法精确()**方法的工作。

```
// Java program to demonstrate working
// of java.lang.Math.subtractExact() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {
        int a = 300;
        int b = 200;

        System.out.println(Math.subtractExact(a, b));
    }
}
```

**输出:**

```
100

```

```
// Java program to demonstrate working
// of java.lang.Math.subtractExact() method
import java.lang.Math;

class Gfg2 {

    // driver code
    public static void main(String args[])
    {
        int x = Integer.MIN_VALUE;
        int y = 10;

        System.out.println(Math.subtractExact(x, y));
    }
}
```

**输出:**

```
Runtime Error :
Exception in thread "main" java.lang.ArithmeticException: integer overflow
    at java.lang.Math.subtractExact(Math.java:829)
    at Gfg2.main(File.java:13)

```