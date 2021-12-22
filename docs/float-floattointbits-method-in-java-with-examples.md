# Java 中的 Float floatToIntBits()方法，带示例

> 原文:[https://www . geesforgeks . org/float-float pointbits-method-in-Java-with-examples/](https://www.geeksforgeeks.org/float-floattointbits-method-in-java-with-examples/)

中的**Float pointbits()**方法是 java 中的内置函数，根据 *IEEE 754* 浮点“单一格式”位布局返回指定浮点值的表示。

**语法:**

```
public static int floatToIntBits(float val)

```

**参数:**该方法只接受一个参数*值*，该参数指定要转换为整数位的浮点数。

**返回值:**该函数返回代表浮点数的**整数位**。以下是一些特例:

*   如果参数为正**无穷大**，则结果为 **0x7f800000** 。
*   如果参数为负**无穷大**，则结果为 **0xff800000** 。
*   如果参数为 **NaN** ，则结果为 **0x7fc00000** 。

下面的程序说明了*float . float pointbits()*方法的使用:

**程序 1:**

```
// Java program to demonstrate
// Float.floatToIntBits() method
import java.lang.*;

class Gfg1 {

    public static void main(String args[])
    {

        float val = 1.5f;

        // function call
        int answer = Float.floatToIntBits(val);

        // print
        System.out.println(val + " in int bits: "
                           + answer);
    }
}
```

**输出:**

```
1.5 in int bits: 1069547520

```

**程序二:**

```
// Java program to demonstrate
// Float.floatToIntBits() method

import java.lang.*;

class Gfg1 {

    public static void main(String args[])
    {

        float val = Float.POSITIVE_INFINITY;
        float val1 = Float.NEGATIVE_INFINITY;
        float val2 = Float.NaN;

        // function call
        int answer = Float.floatToIntBits(val);

        // print
        System.out.println(val + " in int bits: "
                           + answer);

        // function call
        answer = Float.floatToIntBits(val1);

        // print
        System.out.println(val1 + " in int bits: "
                           + answer);

        // function call
        answer = Float.floatToIntBits(val);

        // print
        System.out.println(val2 + " in int bits: "
                           + answer);
    }
}
```

**输出:**

```
Infinity in int bits: 2139095040
-Infinity in int bits: -8388608
NaN in int bits: 2139095040

```

**参考:**T2【https://docs . Oracle . com/javase/7/docs/API/Java/lang/float . html # float pointbits(float)