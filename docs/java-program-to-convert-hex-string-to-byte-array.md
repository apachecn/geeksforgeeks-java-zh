# 将十六进制字符串转换为字节数组的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-convert-hex-string-to-byte-array/](https://www.geeksforgeeks.org/java-program-to-convert-hex-string-to-byte-array/)

**十六进制字符串–**十六进制字符串是由**数字 0-9** 和**字符 A-F** 组合而成，就像二进制字符串只包含 0 和 1 一样。例如:“245FC”是十六进制字符串。

**字节数组–**Java 字节数组是一个仅用于存储**字节**数据类型的数组。字节数组每个元素的默认值是 0。

给定一个字节数组，任务是将**十六进制字符串**转换为**字节数组**。

**示例:**

```
Input - Hex String : "2f4a33"
Output - Byte Array : 47 74 51

Input - Hex String : "3b4a11"
Output - Byte Array : 59 74 17
```

有许多方法可以将十六进制字符串转换为字节数组，下面列出了其中的一些方法。

**接近:**

*   在 Java 中使用整数类的 parseInt()方法
*   用字节数组表示 Java 中的大整数
*   使用按位移位运算符

### 方法 1–在 Java 中使用整数类的 parseInt()方法

Java 中的 [integer.parseInt()](https://www.geeksforgeeks.org/string-to-integer-in-java-parseint/) 方法将给定的字符串转换为整数。根据给定的问题语句，由于我们必须将十六进制字符串转换为字节数组，我们将首先将十六进制字符串的字符成对转换为特定的字节格式，并将该数字插入字节数组。在这种情况下，字节数组的初始化大小是十六进制字符串长度的一半。

以下是上述方法的实施–

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to convert hex
// string to byte array

// Approach 1 - Using parseInt() method of
// Integer class in Java

import java.io.*;

public class GFG {
   public static void main(String[] args)
   {

     // Initializing the hex string and byte array
     String s = "2f4a33";
     byte[] ans = new byte[s.length() / 2];

     System.out.println("Hex String : "+s);

     for (int i = 0; i < ans.length; i++) {
         int index = i * 2;

           // Using parseInt() method of Integer class
         int val = Integer.parseInt(s.substring(index, index + 2), 16);
         ans[i] = (byte)val;
     }

     // Printing the required Byte Array
     System.out.print("Byte Array : ");
     for (int i = 0; i < ans.length; i++) {
         System.out.print(ans[i] + " ");
     }
   }
}
```

**Output**

```
Hex String : 2f4a33
Byte Array : 47 74 51 
```

### 方法 2–在 Java 中使用大整数的字节数组表示

在这种方法中，我们将使用 BigInteger 类的 [toByteArray()](https://www.geeksforgeeks.org/biginteger-tobytearray-method-in-java/) 方法。在使用 parseInt()方法将十六进制数转换为整数值后，我们可以将整数转换为字节数组。BigInteger 类的 toByteArray()方法的作用来了，它将整数值转换成字节数组并返回。

以下是上述方法的实施–

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to convert hex
// string to byte array

// Approach 1 - Using Byte Array Representation
// of BigInteger in Java

import java.io.*;
// importing BigInteger class
import java.math.BigInteger;

class GFG {
    public static void main(String[] args)
    {
        String s = "3b4a11";

          // converting string to integer value
        int val = Integer.parseInt(s, 16);
        System.out.println("Hexadecimal String : " + s);

          // converting integer value to Byte Array
        BigInteger big = BigInteger.valueOf(val);
        byte[] ans = (big.toByteArray());

          // printing the byte array
        System.out.print("Byte Array : ");
        for (int i = 0; i < ans.length; i++)
            System.out.print(ans[i] + " ");
    }
}
```

**Output**

```
Hexadecimal String : 3b4a11
Byte Array : 59 74 17 
```

### 方法 3–使用按位移位运算符

将十六进制字符串转换为字节数组的另一种方法是使用 Java 的二进制移位运算符。这里使用 Java 中的“< Character.digit() 方法。

以下是上述方法的实施–

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert hex
// string to byte array

// Approach 3 - Using Bitwise Shift Operators

import java.io.*;

class GFG {
    public static void main (String[] args) {

         // initializing hex string and byte array
        String s ="1f3d44";
         System.out.println("Hex String : " + s);

          int len = s.length();
        byte[] ans = new byte[len / 2];

        for (int i = 0; i < len; i += 2) {
             // using left shift operator on every character
            ans[i / 2] = (byte) ((Character.digit(s.charAt(i), 16) << 4)
                    + Character.digit(s.charAt(i+1), 16));
        }

          // printing the required result
          System.out.print("Byte Array : ");

          for(int i=0;i<ans.length;i++){
             System.out.print(ans[i]+" ");
        }
    }
}
```

**Output**

```
Hex String : 1f3d44
Byte Array : 31 61 68 
```