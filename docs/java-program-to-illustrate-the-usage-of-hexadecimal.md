# 说明十六进制用法的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-design-of-usage-十六进制/](https://www.geeksforgeeks.org/java-program-to-illustrate-the-usage-of-hexadecimal/)

一个*十进制数* 是数字的总和乘以一个的 10 次方。十进制数用基数 10 表示，而*十六进制数* 是数字的总和乘以 16 的幂，不知何故它们的内部工作有相似的特征，只是它们是表示一个数的两种不同方式。十六进制系统有 16 个不同的数字符号。使用从 0 到 15 的数字组合可以生成不同的数字。从 0 到 9，十六进制系统中的表示与十进制数字系统相同，但此后会发生变化。

**表示:**

> 十进制数等效十六进制数
> 
>         0      —>      0
> 
> : :
> 
>         9      —>      9
> 
> 10 —> A
> 
> 11 —>乙
> 
> 12 —>摄氏度
> 
> 13 —> D
> 
> 14 —> E
> 
> 15 —>华氏

**图解:**内部工作

```
A. Decimal to Hexadecimal Number System

(1) (13)10 --> (D)16
    Directly can be writen 13 as D in hexadecimal system

(2) (16)10 ---> (10)16
    ( 16 )16 = ( 1 x 161) + ( 0 * 160)

(3) (59)10 ---> (3B)16
   ( 59 )10 --> ( 3 * 161) + (11 * 160)
```

**结论:**

```
For a Decimal Number system-> ( 421 )10 = (4 x 102) + (2 x 101) + (1 x 100)
```

```
B. Similarly ,Hexadecimal to Decimal Number System
 (8A)16 ---> (138)10
(8A)16 --> (8 x 161) + (10 x 160)
```

**结论:**

```
In Java programs, hexadecimal numbers are written by placing 0x before numbers.
```

下面是 4 个例子来说明十六进制数的用法

1.  将十六进制数转换为十进制数
2.  将十进制数转换为十六进制数
3.  将十六进制数转换为长数字
4.  将长数字转换为十六进制数字

**示例 1:** 将十六进制数转换为十进制数的 Java 程序

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert Hex number to Decimal number

// Importing input/output java library
import java.io.*;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Hexadecimal number stored in a string
        String hexNum = "100";

        /* Random hexadecimal number */

        // Passing hexnum and base as parameters
        // which is 16 to parseInt function
        int decimal = Integer.parseInt(hexNum, 16);

        // Printing the output result as
        // decimal equivalent of hexa-decimal
        System.out.println("Decimal value is " + decimal);
    }
}
```

**Output**

```
Decimal value is 256
```

**示例 2:** 将十进制数转换为十六进制数的 Java 程序

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate the Usage of HexaDecimal

// Importing input/output java library
import java.io.*;

class GFG {

    // Main driver function
    public static void main(String[] args)
    {

        /* Decimal number to be converted */
        int i = 257;

        // Using toHexString() method for getting decNum and
        // Storing the hexaDecNum in a string
        String hex = Integer.toHexString(i);

        // Printing hexaDecNum of decNum
        System.out.println("Hex value is " + hex);
    }
}
```

**Output**

```
Hex value is 101
```

**示例 3:** 将十六进制数转换为长数字的 Java 程序

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate the Usage of HexaDecimal

// Importing input/output java library
import java.io.*;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Hexadecimal number stored in a string
        String hexNum = "10000";

        // passing hexnum and base as parameters
        // which is 16 to parseLong function
        long num = Long.parseLong(hexNum, 16);

        // Printing long value of HexaDecNum
        System.out.println("Long value is " + num);
    }
}
```

**Output**

```
Long value is 65536
```

**示例 4:** 将长数字转换为十六进制数的 Java 程序

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate the Usage of HexaDecimal

// Importing java input/output library
import java.io.*;

class GFG {

    // Main driver function
    public static void main(String[] args)
    {

        /* Long number to be converted */
        long i = 1024;

        // Storing the result in a string
        String hex = Long.toHexString(i);

        // Displaying Result
        System.out.println("Hex value is " + hex);
    }
}
```

**Output**

```
Hex value is 400
```

**注:**十六进制数还有两种约定，400h 或$400。它们都与 0x400 相同。