# Java lang integer . to exstring()方法示例

> 原文:[https://www . geesforgeks . org/Java-lang-integer-to exstring-method-examples/](https://www.geeksforgeeks.org/java-lang-integer-tohexstring-method-examples/)

Java . lang . integer . to exstring()是 Java 中的内置函数，它将整数参数的字符串表示形式作为基数为 16 的无符号整数返回。该函数在整数数据类型中接受单个参数作为参数。

**语法:**

```
public static String toHexString(int num)

Parameter : The function accepts a single mandatory parameter
num - This parameter specifies the number which is to be converted
to a Hexadecimal string. The data-type is int. 
```

**返回值:**该函数返回 int 参数的字符串表示形式，以 16 为底的无符号整数表示。

示例:

```
Input : 11
Output : b

Input : 12
Output : c

```

**程序 1:** 下面的程序演示了功能的工作。

```
// Java program to demonstrate working
// of java.lang.Integer.toHexString() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {

        int l = 234;

        // returns the string representation of the unsigned int value
        // represented by the argument in binary (base 2)
        System.out.println("Hex string is " + Integer.toHexString(l));

        l = 11;
        System.out.println("Hex string is " + Integer.toHexString(l));
    }
}
```

输出:

```
Hex string is ea
Hex string is b

```

**程序二**:下面的程序演示了负数通过时的工作功能。

```
// Java program to demonstrate
// of java.lang.Integer.toHexString() method
// negative number

import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {
        // when negative number is passed
        System.out.println("Hex is " + Integer.toHexString(-10));
    }
}
```

输出:

```
Hex is fffffff6

```

**错误和异常:**每当十进制数或字符串作为参数传递时，它都会返回一条错误消息，上面写着**“不兼容的类型”。**

**程序 3:** 下面的程序演示了当一个字符串数字被传递时的工作函数。

```
// Java program to demonstrate
// of java.lang.Integer.toHexString() method
// string number

import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {
        // when negative number is passed
        System.out.println("Hex is " + Integer.toHexString("12"));
    }
}
```

输出:

```
prog.java:13: error: incompatible types: String cannot be converted to int
    System.out.println("Hex is " + Integer.toHexString("12")); 
```

**程序 4:** 下面的程序演示了传递小数时的工作功能。

```
// Java program to demonstrate
// of java.lang.Integer.toHexString() method
// decimal

import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {
        // when decimal number is passed
        System.out.println("Hex is " + Integer.toHexString(12.34));
    }
}
```

输出:

```
prog.java:13: error: incompatible types: possible lossy conversion from double to int
    System.out.println("Hex is " + Integer.toHexString(12.34)); 
```