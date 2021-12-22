# Java Math addExact(int a，int b)方法

> 原文:[https://www . geeksforgeeks . org/Java-math-addexact-int-B- method/](https://www.geeksforgeeks.org/java-math-addexactint-int-b-method/)

**java . lang . math . addexact()**是 Java 中的一个内置数学函数，它返回其参数的总和。
如果结果溢出一个 int，它会抛出一个异常。由于 addExact(int a，int b)是**静态**，所以不需要创建对象
。

**语法:**

```
public static int addExact(int a, int b)
Parameter :
 a : the first value
 b : the second value
Return :
This method returns the sum of its arguments.
Exception :
It throws ArithmeticException - if the result overflows an int

```

**示例:**展示**Java . lang . math . addexact()**方法的工作。

```
// Java program to demonstrate working
// of java.lang.Math.addExact() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {
        int a = 100;
        int b = 200;

        System.out.println(Math.addExact(a, b));
    }
}
```

**输出:**

```
300

```

```
// Java program to demonstrate working
// of java.lang.Math.addExact() method
import java.lang.Math;

class Gfg2 {

    // driver code
    public static void main(String args[])
    {
        int x = Integer.MAX_VALUE;
        int y = 200;

        System.out.println(Math.addExact(x, y));
    }
}
```

**输出:**

```
Runtime Error :
Exception in thread "main" java.lang.ArithmeticException: integer overflow
    at java.lang.Math.addExact(Math.java:790)
    at Gfg2.main(File.java:13)

```