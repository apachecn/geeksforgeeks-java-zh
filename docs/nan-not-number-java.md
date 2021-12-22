# Java 中的 NaN(不是数字)

> 原文:[https://www.geeksforgeeks.org/nan-not-number-java/](https://www.geeksforgeeks.org/nan-not-number-java/)

您能猜出以下代码片段的输出吗:

```java
public class Test
{
    public static void main(String[] args)
    {
        System.out.println(2 % 0);
    }
}       
```

是的，你猜对了:算术异常
输出:

```java
Exception in thread "main" java.lang.ArithmeticException: / by zero
	at traps.Test.main(Test.java:3)

```

现在猜测输出:

```java
public class Test
{
    public static void main(String[] args)
    {
        System.out.println(2.0 % 0);
    }
}       
```

你猜对了吗？
输出:

```java
NaN

```

 **什么是 NaN？**

“ **NaN** ”代表“不是数字”。如果浮点运算有一些输入参数，导致运算产生一些未定义的结果，就会产生“Nan”。例如， **0.0 除以 0.0** 在算术上是未定义的。找出负数的**平方根也是没有定义的。**

```java
//Java Program to illustrate NaN
public class Test
{
    public static void main(String[] args)
    {
        System.out.println(2.0 % 0);
        System.out.println(0.0 / 0);
        System.out.println(Math.sqrt(-1));
    }
}       
```

输出:

```java
NaN
NaN
NaN

```

在 javadoc 中，常量字段 NaN 在 Float 和 Double 类中分别声明如下。

```java
public static final float 	NaN = 0f / 0f;
public static final double      NaN = 0d / 0d;

```

**如何比较 NaN 值？**

所有以 NaN 作为操作数的数值运算都会产生 NaN 结果。这背后的原因是 NaN 是无序的，因此涉及一个或两个 NaN 的数值比较操作返回 false。

*   如果一个或两个操作数都是 NaN，则数字比较运算符和> =总是返回 false。( [15.20.1](http://docs.oracle.com/javase/specs/jls/se7/html/jls-15.html#jls-15.20.1) )
*   如果任一操作数为 NaN，等式运算符==返回 false。
*   不等式运算符！=如果任一操作数为 NaN，则返回 true。( [15.21.1](http://docs.oracle.com/javase/specs/jls/se7/html/jls-15.html#jls-15.21.1) )

```java
// Java program to test relational operator on NaN
public class ComparingNaN
{
    public static void main(String[] args)
    {
        // comparing NaN constant field defined in
        // Float Class
        System.out.print("Check if equal :");
        System.out.println(Float.NaN == Float.NaN);

        System.out.print("Check if UNequal: ");
        System.out.println(Float.NaN != Float.NaN);

        // comparing NaN constant field defined in Double Class
        System.out.print("Check if equal: ");
        System.out.println(Double.NaN == Double.NaN);

        System.out.print("Check if UNequal: ");
        System.out.println(Double.NaN != Double.NaN);

        // More Examples
        double NaN = 2.1 % 0;
        System.out.println((2.1%0) == NaN);
        System.out.println(NaN == NaN);
    }
}
```

输出:

```java
Check if equal :false
Check if UNequal: true
Check if equal: false
Check if UNequal: true
false
false

```

**isNaN()方法**

如果此对象表示的值是 NaN，则此方法返回 true 否则为假。

```java

import java.lang.*;

public class isNan
{

   public static void main(String[] args)
   {

     Double x = new Double(-2.0/0.0);
     Double y = new Double(0.0/0.0);

     // returns false if this Double value is not a Not-a-Number (NaN) 
     System.out.println(y + " = " + y.isNaN());

     // returns true if this Double value is a Not-a-Number (NaN) 
     System.out.println(x + " = " + x.isNaN());

   }
} 
```

输出:

```java
NaN = true
-Infinity = false

```

**浮点型在用数学值运算时不产生异常**

[IEEE 754](http://docs.oracle.com/javase/specs/jls/se7/html/jls-4.html#jls-4.2.3) 浮点数可以表示正无穷大或负无穷大，以及 NaN(不是数字)。这三个值来自结果未定义或无法准确表示的计算。
爪哇正在遵循已知的数学事实。1.0 / 0.0 是无穷大，但是其他的都是不定形式，Java 表示为 NaN(不是数字)。

```java
// Java program to illustrate output of floating
// point number operations
public class Test
{
    public static void main(String[] args)
    {
        System.out.println(2.0 / 0);
        System.out.println(-2.0 / 0);
        System.out.println(9.0E234 / 0.1E-234);
    }
}
```

输出:

```java
Infinity
-Infinity
Infinity

```

参考文献:
[https://docs . Oracle . com/javase/7/docs/API/Java/lang/double . html](https://docs.oracle.com/javase/7/docs/api/java/lang/Double.html)
T4【https://docs . Oracle . com/javase/specs/jls/se7/html/jls-4 . html

本文由 [**潘卡吉·库马尔**](https://in.linkedin.com/in/prakuj) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。