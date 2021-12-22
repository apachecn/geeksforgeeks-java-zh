# Java 中的 Float floatToRawIntBits()方法，带示例

> 原文:[https://www . geeksforgeeks . org/float-floattorawintbits-method-in-Java-with-examples/](https://www.geeksforgeeks.org/float-floattorawintbits-method-in-java-with-examples/)

**[浮点类](https://www.geeksforgeeks.org/java-lang-float-class-in-java/)** 中的**floatittorawintbits()**方法是 java 中的一个内置函数，根据 IEEE 754 浮点“单一格式”位布局返回指定浮点值的表示形式，保留 Not-a-Number (NaN)值。

**语法:**

```java
public static int floatToRawIntBits(float val)
```

**参数:**该方法只接受一个指定浮点数的参数*值*。

**返回值:**函数返回代表浮点数的位。然而，有 3 种特殊情况:

*   如果参数为正**无穷大**，则结果为 **0x7f800000** 。
*   如果参数为负**无穷大**，则结果为 **0xff800000** 。
*   如果参数为 **NaN** ，则结果为 **0x7fc00000** 。

下面的程序说明了*float . float torawitbits()*方法的使用:

**程序 1:**

```java
// Java program to demonstrate
// Float.floatToRawIntBits() method
import java.lang.*;

class Gfg1 {

    public static void main(String args[])
    {

        float val = 1.5f;

        // function call
        int answer = Float.floatToRawIntBits(val);

        // print
        System.out.println(val + " in raw int bits: "
                           + answer);
    }
}
```

**输出:**

```java
1.5 in raw int bits: 1069547520

```

**程序二:**

```java
// Java program to demonstrate
// Float.floatToRawIntBits() method

import java.lang.*;

class Gfg1 {

    public static void main(String args[])
    {

        float val = Float.POSITIVE_INFINITY;
        float val1 = Float.NEGATIVE_INFINITY;
        float val2 = Float.NaN;

        // function call
        int answer = Float.floatToRawIntBits(val);

        // print
        System.out.println(val + " in raw int bits: "
                           + answer);

        // function call
        answer = Float.floatToRawIntBits(val1);

        // print
        System.out.println(val1 + " in raw int bits: "
                           + answer);

        // function call
        answer = Float.floatToRawIntBits(val);

        // print
        System.out.println(val2 + " in raw int bits: "
                           + answer);
    }
}
```

**输出:**

```java
Infinity in raw int bits: 2139095040
-Infinity in raw int bits: -8388608
NaN in raw int bits: 2139095040

```