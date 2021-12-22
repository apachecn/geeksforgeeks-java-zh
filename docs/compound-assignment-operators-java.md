# Java 中的复合赋值运算符

> 原文:[https://www . geesforgeks . org/compound-assignment-operators-Java/](https://www.geeksforgeeks.org/compound-assignment-operators-java/)

复合赋值运算符为赋值算术或按位运算符的结果提供了更短的语法。在将结果赋给第一个操作数之前，它们对两个操作数执行运算。
**以下是 java 中所有可能的赋值运算符:**

```java
1\.    += (compound addition assignment operator)
2\.    -=  (compound subtraction assignment operator)
3\.    *= (compound multiplication assignment operator)
4\.    /= (compound division assignment operator)
5\.    %= (compound modulo assignment operator)
6\.    &= (compound Bitwise & assignment operator)
7\.    |= (compound Bitwise | assignment operator)
8\.    ^= (compound Bitwise ^ assignment operator)
9\.    >>= (compound right-shift assignment operator)
10\.    >>>=(compound right-shift filled 0 assignment operator)
11\.    <<=(compound left-shift assignment operator)

```

**所有复合赋值运算符的实现**

```java
// Java program to illustrate
// Compound assignment operators
class Main {
public static void main(String args[])
    {
        byte b = 120;
        b += 10;
        byte b1 = 120;
        b1 *= 10;
        short s = 330;
        s -= 30;
        byte b2 = 127;
        b2 %= 7;
        byte b3 = 120;
        b3 &= 40;
        short s1 = 300;
        s1 ^= 100;
        byte b4 = 127;
        b4 >>= 3;
        short s2 = 200;
        s2 <<= 3;
        short s3 = 300;
        s3 >> >= 4;
        System.out.println(b);
        System.out.println(b1);
        System.out.println(b2);
        System.out.println(b3);
        System.out.println(b4);
        System.out.println(s);
        System.out.println(s1);
        System.out.println(s2);
        System.out.println(s3);
    }
}
```

输出:

```java
-126
-80
1
40
15
300
328
1600
18

```

**复合赋值运算符的解析规则**

在运行时，表达式的计算方式有两种。根据编程条件:

1.  **如果左侧操作数表达式不是数组访问表达式，则:**
    *   首先，计算左边的操作数以产生一个变量。如果此评估突然完成，则赋值表达式出于同样的原因突然完成；右边的操作数不会被求值，也不会发生赋值。
    *   否则，保存左侧操作数的值，然后计算右侧操作数。如果此评估突然完成，则赋值表达式出于同样的原因突然完成，并且不发生赋值。
    *   否则，左侧变量的保存值和右侧操作数的值用于执行复合赋值运算符指示的二进制运算。如果此操作突然完成，则赋值表达式出于同样的原因突然完成，并且不发生赋值。
    *   否则，二进制运算的结果被转换为左侧变量的类型，经过值集转换为适当的标准值集，并且转换的结果被存储到变量中。
2.  **如果左边的操作数表达式是数组访问表达式，那么:**
    *   首先，计算左侧操作数数组访问表达式的数组引用子表达式。如果此评估突然完成，则赋值表达式出于同样的原因突然完成；(左侧操作数数组访问表达式的)索引子表达式和右侧操作数不会被计算，也不会发生赋值。
    *   否则，计算左侧操作数数组访问表达式的索引子表达式。如果此计算突然完成，则赋值表达式出于同样的原因突然完成，右侧的操作数不会被计算，也不会发生赋值。
    *   否则，如果数组引用子表达式的值为空，则不发生赋值，并引发 NullPointerException。
    *   否则，数组引用子表达式的值确实引用了一个数组。如果索引子表达式的值小于零，或者大于或等于数组的长度，则不会发生赋值，并且会引发 ArrayIndexOutOfBoundsException。
    *   否则，索引子表达式的值用于选择数组引用子表达式的值所引用的数组的一个组件。保存该组件的值，然后计算右边的操作数。如果此评估突然完成，则赋值表达式出于同样的原因突然完成，并且不发生赋值。

**示例:使用复合赋值运算符解析语句**

我们都知道，每当我们给一个较小的数据类型变量分配一个较大的值时，我们必须执行显式类型转换，以获得没有任何编译时错误的结果。如果我们没有执行显式类型转换，那么我们将得到编译时错误。但是在复合赋值操作符的情况下，内部类型转换将自动执行，即使我们将更大的值赋给更小的数据类型变量，但也有可能丢失数据信息。程序员不负责执行显式类型转换。让我们看下面的例子，找出正规赋值运算符和复合赋值运算符的区别。
E1 op = E2 形式的复合赋值表达式等价于 E1 = (T) ((E1) op (E2))，其中 T 是 E1 的类型，只是 E1 只被求值一次。

例如，以下代码是正确的:

```java
short x = 4;
x += 6.6;

```

并且导致 x 具有值 7，因为它相当于:

```java
short x = 4;
x = (short)(x + 6.6);
x=10

```

因为这里的 6.6 是双精度的，自动转换为短类型，没有显式的类型转换。

**参考:[何时需要类型转换？](https://www.geeksforgeeks.org/type-conversion-java-examples/)T3】**

```java
// Java program to illustrate the
// behavior of normal addition operator
public class Test {
public static void main(String[] args)
    {
        // Normal assignment operator
        byte b = 10;
        b = b + 10;
        System.out.println(b);
    }
}
```

输出:

```java
error: incompatible types: possible lossy conversion from int to byte

```

**说明:**在上面的例子中，我们使用的是正规赋值运算符。这里我们将一个 int (b+1=20)值赋给字节变量(即 b)，这会导致编译时错误。这里我们必须进行类型转换才能得到结果。

```java
// Java program to illustrate the
// behavior of compound addition assignment operator
public class Test {
public static void main(String[] args)
    {
        // compound assignment operator
        byte b = 10;
        b += 10;
        System.out.println(b);
    }
}
```

输出:

```java
20

```

**说明:**在上面的例子中，我们使用的是复合赋值运算符。这里我们将一个 int (b+1=20)值赋给字节变量(即 b)，除此之外，我们得到的结果是 20，因为在复合赋值运算符中，类型转换是通过编译自动完成的。这里我们不需要做类型转换就能得到结果。

```java
// Java program to illustrate the
// behavior of normal multiplication operator
public class Test {
public static void main(String[] args)
    {
        // Normal multiplication operator
        short s = 1270;
        s = s * 100;
        System.out.println(s);
    }
}
```

输出:

```java
Error: incompatible types: possible lossy conversion from int to short

```

```java
// Java program to illustrate the
// behavior of compound multiplication operator
public class Test {
public static void main(String[] args)
    {
        // Compound multiplication operator
        short s = 1270;
        s *= 100;
        System.out.println(s);
    }
}
```

输出:

```java
-4072

```

```java
// Java program to illustrate the
// behavior of normal addition operator on float
public class Test {
public static void main(String[] args)
    {
        // Normal addition operator
        float f = 1270.00f;
        f = f + 127.00;
        System.out.println(f);
    }
}
```

输出:

```java
error: incompatible types: possible lossy conversion from double to float

```

```java
// Java program to illustrate the
// behavior of compound addition operator on float
public class Test {
public static void main(String[] args)
    {
        // Compound addition operator
        float f = 1270.00f;
        f += 127.00;
        System.out.println(f);
    }
}
```

输出:

```java
1397.0

```

**参考:**http://docs . Oracle . com/javase/specs/jls/se7/html/jls-15 . html # jls-15 . 26 . 2

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。