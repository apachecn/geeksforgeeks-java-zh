# Java 数学 toIntExact(长值)方法

> 原文:[https://www . geesforgeks . org/Java-math-to texactlong-value-method/](https://www.geeksforgeeks.org/java-math-tointexactlong-value-method/)

**java . lang . math . ToinTextact()**是 Java 中的内置数学函数，它返回长参数的值。如果结果溢出一个 int，它将引发异常。由于 toIntExact(长值)是**静态的**，所以对象创建不是
必需的。

**语法:**

```
public static int toIntExact(long value)
Parameter :
value : the long value
Return :
This method returns the input argument as an int(integer) .
Exception :
It throws ArithmeticException - if the result overflows an int

```

**示例:**展示**Java . lang . math . To textact()**方法的工作。

```
// Java program to demonstrate working
// of java.lang.Math.toIntExact() method
import java.lang.Math;

class Gfg1 {
    // driver code
    public static void main(String args[])
    {
        long a = 499;
        System.out.println(Math.toIntExact(a));
    }
}
```

**输出:**

```
499

```

```
// Java program to demonstrate working
// of java.lang.Math.toIntExact() method
import java.lang.Math;

class Gfg2 {

    // driver code
    public static void main(String args[])
    {
        long x = Long.MAX_VALUE;

        System.out.println(Math.toIntExact(x));
    }
}
```

**输出:**

```
Runtime Error :
Exception in thread "main" java.lang.ArithmeticException: integer overflow
    at java.lang.Math.toIntExact(Math.java:1011)
    at Gfg2.main(File.java:12)

```