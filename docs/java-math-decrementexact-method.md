# Java 数学递减精确()方法

> 原文:[https://www . geeksforgeeks . org/Java-math-reduce exact-method/](https://www.geeksforgeeks.org/java-math-decrementexact-method/)

java . strict math . lang . reducture()是 Java 中的内置函数，它返回减 1 的参数，如果结果溢出指定的数据类型 long 或 int，将引发异常，具体取决于在方法参数上使用了哪种数据类型。因为这是减量，所以如果结果小于最小值，我们将遇到异常的唯一情况。最小值可以从龙导出。最小值或整数。最小值。

**语法:**

```
int decrementExact(int num)
long decrementExact(long num)

```

**参数:**该函数接受一个强制参数，如上所示，如下所述:
**num–**该参数指定必须递减的数字。

**返回值:**该函数返回减 1 的参数，如果结果溢出了指定的数据类型 long 或 int，则抛出异常，具体取决于方法参数使用了哪种数据类型。

**示例:**

```
Input : 12
Output : 11

Input : -3 
Output : -4

```

**程序 1:** 演示功能工作的程序

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate working
// of java.lang.Math.decrementExact() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {

        int y = 12;
        System.out.println(Math.decrementExact(y));

        int x = -3;
        System.out.println(Math.decrementExact(x));
    }
}
```

**输出:**

```
11
-4

```

**程序 2:** 演示函数溢出的程序

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate overflow
// of java.lang.Math.decrementExact() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {

        int y = Integer.MIN_VALUE;
        System.out.println(Math.decrementExact(y));
    }
}
```

**输出:**

```
Exception in thread "main" java.lang.ArithmeticException: integer overflow
    at java.lang.Math.decrementExact(Math.java:943)
    at Gfg1.main(File.java:12)

```