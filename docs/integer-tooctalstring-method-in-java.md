# Java 中的整数 toOctalString()方法

> 原文:[https://www . geesforgeks . org/integer-tooctalstring-method-in-Java/](https://www.geeksforgeeks.org/integer-tooctalstring-method-in-java/)

八进制是以 8 为基数的数字系统，在运算中使用数字 0 到 7。八进制被广泛用于 PDP-8 等系统的计算，IBM 大型机采用 12 位、24 位或 36 位字。
Java . lang . integer . tooctalstring()方法是 Java 中的内置函数，用于将整数参数的字符串表示形式作为基数为 8 的无符号整数返回。
**语法:**

```
public static String toOctalString(*int num*)
```

**参数:**该方法接受需要转换为字符串的整数类型的单个参数*数*。
**返回值:**该函数将整数参数的字符串表示形式返回为基数为 8 的无符号整数。
**示例:**

```
 Consider an integer a = 86
 Octal output = 126

Consider an integer a = 186 
Octal output = 272        
```

以下程序说明了 Integer.toOctalString()方法的工作:
**程序 1:** 对于正整数:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate working
// of Integer.toOctalString() method

import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        int a = 527;
        System.out.println("Integral Number = " + a);

        // returns the string representation of the unsigned int value
        // represented by the argument in octal (base 8)
        System.out.println("Octal Number = " + Integer.toOctalString(a));
    }
}
```

**Output:** 

```
Integral Number = 527
Octal Number = 1017
```