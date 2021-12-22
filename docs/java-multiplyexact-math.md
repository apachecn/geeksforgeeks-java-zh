# 数学中的 Java multiplyExact()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/Java-multi-exact-math/

**java . lang . math . multiplyxact()**是一个内置的 Java 数学函数，它返回
参数的乘积。如果结果溢出一个 int，它将引发异常。由于 multiplyxact(int a，int b)是**静态**，所以不需要
对象创建。

**语法:**

```java
public static int multiplyExact(int a, int b)
public static double multiplyExact(int a, double b)
Parameter :
 a : the first value
 b : the second value
Return :
This method returns the product of the arguments.
Exception :
It throws ArithmeticException - if the result overflows an int

```

**示例:**展示**Java . lang . math . multiplyxact()**方法的工作。

```java
// Java program to demonstrate working
// of java.lang.Math.multiplyExact() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {
        int a = 25, b = 5;
        System.out.println(Math.multiplyExact(a, b));

        long c = 100, d = 50;
        System.out.println(Math.multiplyExact(c, d));
    }
}
```

**Output:**

```java
125
5000

```

```java
// Java program to demonstrate working
// of java.lang.Math.multiplyExact() method
import java.lang.Math;

class Gfg2 {

    // driver code
    public static void main(String args[])
    {
        int x = Integer.MAX_VALUE;
        int y = 2;

        System.out.println(Math.multiplyExact(x, y));
    }
}
```

**输出:**

```java
Runtime Error :
Exception in thread "main" java.lang.ArithmeticException: integer overflow
    at java.lang.Math.multiplyExact(Math.java:867)
    at Gfg2.main(File.java:13)

```