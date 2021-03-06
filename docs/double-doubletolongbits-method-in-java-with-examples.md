# Java 中 doubleToLongBits()方法，带示例

> 原文:[https://www . geesforgeks . org/double-double tolongbits-method-in-Java-with-examples/](https://www.geeksforgeeks.org/double-doubletolongbits-method-in-java-with-examples/)

[java Double 类](https://www.geeksforgeeks.org/java-lang-double-class-java/)的**Java . lang . Double . Double TolongBits()**方法是 Java 中的内置函数，根据 IEEE 754 浮点“双格式”位布局返回指定浮点值的表示。

**语法:**

```java
public static long doubleToLongBits(double val)

```

**参数:**该方法只接受一个指定双精度浮点数的参数*值*。

**返回值:**函数返回代表浮点数的位。以下是一些特例:

*   如果参数为正**无穷大**，则结果为**7ff 000000000000001**。
*   如果参数为负**无穷大**，则结果为**0xfff 00000000000000000000000000000000000000000000000000000000000000000000000**
*   如果参数是 **NaN** ，结果是**0x7ff 800000000000000000000000000000000000000000000000000000000000000000000000**

下面的程序说明了*Java . lang . double . double tolongbits()*方法的使用:

**程序 1:**

```java
// Java program to demonstrate
// Double.doubleToLongBits() method

import java.lang.*;

class Gfg1 {

    public static void main(String args[])
    {

        double val = 1.5d;

        // function call
        long answer = Double.doubleToLongBits(val);

        // print
        System.out.println(val + " in long bits: "
                           + answer);
    }
}
```

**输出:**

```java
1.5 in long bits: 4609434218613702656

```

**程序二:**

```java
// Java program to demonstrate
// Double.doubleToLongBits() method

import java.lang.*;

class Gfg1 {

    public static void main(String args[])
    {

        double val = Double.POSITIVE_INFINITY;
        double val1 = Double.NEGATIVE_INFINITY;
        double val2 = Double.NaN;

        // function call
        long answer = Double.doubleToLongBits(val);

        // print
        System.out.println(val + " in long bits: "
                           + answer);

        // function call
        answer = Double.doubleToLongBits(val1);

        // print
        System.out.println(val1 + " in long bits: "
                           + answer);

        // function call
        answer = Double.doubleToLongBits(val2);

        // print
        System.out.println(val2 + " in long bits: "
                           + answer);
    }
}
```

**输出:**

```java
Infinity in long bits: 9218868437227405312
-Infinity in long bits: -4503599627370496
NaN in long bits: 9221120237041090560

```

**参考:**T2【https://docs . Oracle . com/javase/7/docs/API/Java/lang/double . html # double tolongbits(double)