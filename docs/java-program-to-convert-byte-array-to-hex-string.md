# 将字节数组转换为十六进制字符串的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-convert-byte-array-to-hex-string/](https://www.geeksforgeeks.org/java-program-to-convert-byte-array-to-hex-string/)

**字节数组–**Java 字节数组是一个仅用于存储**字节**数据类型的数组。字节数组每个元素的默认值是 0。

**十六进制字符串–**十六进制字符串是由**数字 0-9** 和**字符 A-F** 组合而成，就像二进制字符串只包含 0 和 1 一样。例如:“245FC”是十六进制字符串。

**问题陈述–**给定一个字节数组，任务是将**字节数组**转换为**十六进制字符串**。

**示例:**

```java
Input : byteArray = { 9, 2, 14, 10 }
Output: 9 2 E A

Input : byteArray = { 7, 12, 13, 127 }
Output: 7 C D 7F
```

字节数组到十六进制字符串的转换包括将字节数据类型数组更改为字符串形式的十六进制值。有许多方法可以做到这一点；下面列出了其中的一些。

**接近:**

*   在 Java 中使用 Format()方法
*   使用按位移位运算符
*   使用整数/长类中的预定义方法
*   Java 中大整数的十六进制表示

### **方法 1–**在 Java 中使用 Format()方法

[Java String Format()](https://www.geeksforgeeks.org/java-string-format-examples/) 方法可以用于指定的转换。为此，

1.  迭代数组中的每个字节，并计算它的十六进制等价物。
2.  string.format()用于打印十六进制值的位数，并将该值存储在字符串中。
3.  %02X 用于打印在两个十六进制值之间添加两个空格(十六进制的(X))。

以下是上述方法的实施:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to convert byte
// array to hex string

// Approach 1 -  Using Format() Method in Java

import java.io.*;

public class GFG {
    public static void convertByteToHexadecimal(byte[] byteArray)
    {
        String hex = "";

        // Iterating through each byte in the array
        for (byte i : byteArray) {
            hex += String.format("%02X", i);
        }

        System.out.print(hex);
    }

    public static void main(String[] args)
    {
        byte[] byteArray = { 7, 12, 13, 127 };
        convertByteToHexadecimal(byteArray);
    }
}
```

**Output**

```java
070C0D7F
```

### 方法 2–使用按位移位运算符

在前面的方法中，如果字节数组变大，过程就会变得很慢。字节操作用于将字节数组转换为十六进制值，以提高效率。

这里使用“> > >”[无符号右移运算符](https://www.geeksforgeeks.org/bitwise-shift-operators-in-java/)。并且， [toCharArray()](https://www.geeksforgeeks.org/java-string-tochararray-example/#:~:text=The%20java%20string%20toCharArray(),a%20newly%20allocated%20character%20array.) 方法将给定的字符串转换为字符序列。

以下是上述方法的实施–

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to convert byte
// array to hex string

// Approach 2 - Using Bitwise Shift Operators

import java.io.*;

public class GFG {
    public static void
        convertByteToHexadecimal(byte[] byteArray)
    {
        int len = byteArray.length;

        // storing the hexadecimal values
        char[] hexValues = "0123456789ABCDEF".toCharArray();
        char[] hexCharacter = new char[len * 2];

        // using  byte operation converting byte
        // array to hexadecimal value
        for (int i = 0; i < len; i++) {
            int v = byteArray[i] & 0xFF;
            hexCharacter[i * 2] = hexValues[v >>> 4];
            hexCharacter[i * 2 + 1] = hexValues[v & 0x0F];
        }

        System.out.println(hexCharacter);
    }

    public static void main(String[] args)
    {
        byte[] bytes = { 9, 2, 14, 127 };
        convertByteToHexadecimal(bytes);
    }
}
```

**Output**

```java
09020E7F
```

### 方法 3–在整数/长类中使用预定义的方法

Integer 类有[to exstring()](https://www.geeksforgeeks.org/java-lang-integer-tohexstring-method-examples/)方法，可以将一个整数转换为它的十六进制等价物。我们现在需要将字节数组转换为整数(对于 4 大小的)或长(对于 8 大小的)并使用这个方法(因为这个方法存在于两个类中，即具有相同名称的整数和长)。为了将字节数组转换为整数或长，我们可以使用字节缓冲类的[包装方法](https://www.geeksforgeeks.org/bytebuffer-wrap-method-in-java-with-examples/)。

以下是上述方法的实施–

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to convert byte
// array to hex string

// Approach 3 - Using the predefined method 
// in Integer/Long Class

import java.io.*;
// Importing packages to use wrap methods 
// of ByteBuffer Class
import java.nio.*;

public class GFG {
    public static String toHexadecimal(byte[] bytes)
    {
        StringBuilder result = new StringBuilder();

        for (byte i : bytes) {
            int decimal = (int)i & 0XFF;
            String hex = Integer.toHexString(decimal);

            if (hex.length() % 2 == 1) {
                hex = "0" + hex;
            }

            result.append(hex);
        }
        return result.toString();
    }

    public static void main(String[] args)
    {
        byte[] byteArray = { 9, 2, 14, 127 };
        System.out.println(toHexadecimal(byteArray));
    }
}
```

**Output**

```java
09020e7f
```

### 方法 4–在 Java 中使用 BigInteger 的十六进制表示

在 Java 中使用 BigInteger 类的十六进制表示是一种避免将字节数组转换为十六进制字符串的方法，因为它的速度很慢。这里还可以观察到，由于我们处理的是数字，而不是任意字节字符串，因此在某些情况下可能会省略前导零。

以下是上述方法的实施–

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to convert byte
// array to hex string

// Approach 4 - Using Hexadecimal Representation
// of BigInteger in Java

import java.io.*;
// Importing the BigInteger class
import java.math.BigInteger;

public class GFG {
    public static void toHexString(byte[] byteArray)
    {
        // Printing the hexadecimal equivalent as string
        // representation from the BigInteger class.
        System.out.print(
            new BigInteger(1, byteArray).toString(16));
    }

    public static void main(String[] args)
    {
        byte[] byteArray = { 17, 2, 14, 127 };
        toHexString(byteArray);
    }
}
```

**Output**

```java
11020e7f
```