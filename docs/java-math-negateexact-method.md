# Java 数学求反精确()方法

> 原文:[https://www.geeksforgeeks.org/java-math-negateexact-method/](https://www.geeksforgeeks.org/java-math-negateexact-method/)

java . lang . math . avenue exact()是 Java 中的一个内置函数，它返回参数的否定结果，如果结果溢出了指定的数据类型 long 或 int，将引发异常，具体取决于在方法参数上使用了哪种数据类型。当数据类型 int 的最小值为-2147483648，最大值为 2147483647 时，它会引发错误。所以如果我们否定-2147483648，结果将是 2147483648，它已经超过了最大值。

**语法:**

```java
int negateExact(int num)
long negateExact(long num)
```

**参数:**该函数接受单个参数，如上所示，解释如下:

*   **num–**此参数指定必须返回否定结果的数字。

**返回值:**函数返回参数的否定结果，如果结果溢出指定的数据类型(long 或 int ),则抛出异常，具体取决于方法参数使用了哪种数据类型

示例:

```java
Input : 12
Output : -12

Input : -2
Output : 2 

```

程序 1:下面的程序演示了否定精确()方法的工作原理。

```java
// Java program to demonstrate working
// of java.lang.Math.negateExact() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {

        int y = 10;
        System.out.println(Math.negateExact(y));

        int x = -12;
        System.out.println(Math.negateExact(x));
    }
}
```

输出:

```java
-10
12
```

程序 2:下面的程序演示了否定精确()方法的溢出。

```java
// Java program to demonstrate overflow
// of java.lang.Math.negateExact() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {

        int y = Integer.MIN_VALUE;
        System.out.println(Math.negateExact(y));
    }
}
```

输出:

```java
Exception in thread "main" java.lang.ArithmeticException: integer overflow
    at java.lang.Math.negateExact(Math.java:977)
    at Gfg1.main(File.java:12)
```