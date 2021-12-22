# Java lang Long.toOctalString()方法示例

> 原文:[https://www . geesforgeks . org/Java-lang-long-tooctalstring-method/](https://www.geeksforgeeks.org/java-lang-long-tooctalstring-method/)

Java.lang.Long.toOctalString()函数是 Java 中的内置函数，它将长参数的字符串表示形式作为基数为 8 的无符号整数返回。

**语法:**

```
public static int toOctalString(long num)

```

**参数:**该函数接受单个强制参数 *num，*，该参数将被转换为字符串。参数为
T5 长数据类型。
**返回:**函数返回长参数的字符串表示形式，以 8 为基数的无符号整数表示。

**示例:**

```
Input : 16
Output : 20

Input : 1234
Output : 2322

```

演示功能工作的程序:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate working
// of java.lang.Long.toOctalString() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {

        long l = 16;

        // returns the string representation of the unsigned int value
        // represented by the argument in octal (base 8)
        System.out.println("Octal string is " + Long.toOctalString(l));  

        l = 1234;
        System.out.println("Octal string is " + Long.toOctalString(l));  

    }
}
```

**输出:**

```
Octal string is 20
Octal string is 2322

```

**程序二**:下面的程序演示了负数通过时的工作功能。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// of java.lang.Long.toOctalString() method
// negative number

import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {
        // when negative number is passed
    System.out.println("Hex is " + Long.toOctalString(-14));
    }
}
```

**输出:**

```
Hex is 1777777777777777777762

```

**错误和异常:**每当十进制数或字符串作为参数传递时，它都会返回一条错误消息，上面写着**“不兼容的类型”。**

**程序 3:** 下面的程序演示了当一个字符串数字被传递时的工作函数。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// of java.lang.Long.toOctalString() method
// string number

import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {
        // when string number is passed
    System.out.println("Hex is " + Long.toOctalString("14"));
    }
}

```

**输出:**

```
prog.java:13: error: incompatible types: String cannot be converted to long
    System.out.println("Hex is " + Long.toOctalString("14"));

```

**程序 4:** 下面的程序演示了传递小数时的工作功能。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// of java.lang.Long.toOctalString() method
// decimal number

import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {
        // when decimal number is passed
    System.out.println("Hex is " + Long.toOctalString(15.67));
    }
}
```

**输出:**

```
prog.java:13: error: incompatible types: possible lossy conversion from double to long
    System.out.println("Hex is " + Long.toOctalString(15.67)); 

```