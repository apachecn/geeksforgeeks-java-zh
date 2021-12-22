# 使用 getBytes(Charset)方法将字符串转换为 Java 中的字节数组

> 原文:[https://www . geesforgeks . org/convert-string-to-byte-array-in-Java-using-getbytesharset-method/](https://www.geeksforgeeks.org/convert-string-to-byte-array-in-java-using-getbytescharset-method/)

在 Java 中，字符串是由一个字符数组在内部支持的对象。所以要将一个字符串转换成一个字节数组，我们需要一个**获取字节(字符集)**的方法。此方法使用给定的字符集将给定的字符串转换为字节序列，并返回字节数组。它是字符串类的预定义函数。这里，在这个方法中我们使用了一个 Charset 类的实例，这个类提供了一个字符序列和一个字节序列之间的命名映射。定义了许多字符集，下面将进行讨论。

*   **美国-ASCII:** 七位 ASCII，又名 ISO646-美国，又名 Unicode 字符集的基本拉丁块
*   **ISO-8859-1:** ISO 拉丁字母 1 号，a.k.a. ISO-LATIN-1
*   **UTF-8:** 八位 UCS 转换格式
*   **UTF-16BE:** 十六位 UCS 转换格式，大端字节顺序
*   **UTF-16LE:** 十六位 UCS 转换格式，小端字节顺序
*   **UTF-16:** 十六位 UCS 转换格式，字节顺序由可选的字节顺序标记标识。

**语法:**

```
public byte[] getBytes(Charset charset)
```

**参数:**此函数接受一个参数，即用于编码字符串的字符集

**返回类型:**该函数返回产生的字节数组。

**注:**

*   此方法总是用字符集的默认替换字节数组替换格式错误的输入和不可映射的字符序列。
*   如果给定的字符集不是有效的字符集，那么这个方法将抛出*unsupportdencodinegexception。*
*   字节数组的长度与给定的字符串不同，它取决于字符编码。

让我们借助给定的示例来讨论如何将字符串转换为字节数组:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate how to
// convert a string to byte array
// Using getBytes(Charset charset)

import java.io.*;

class GFG{

public static void main (String[] args) 
{

    // Initializing String 
    String ss = "Hello GeeksforGeeks";

    // Display the string before conversion
    System.out.println("String: " + ss);

    try
    { 

        // Converting string to byte array
        // Using getBytes(Charset charset) method
        // Here, we converts into UTF-16 values
        byte[] res = ss.getBytes("UTF-16"); 

        // Displaying converted string after conversion 
        // into UTF-16 
        System.out.println("Result : "); 

        for(int i = 0; i < res.length; i++)
        {
            System.out.print(res[i]); 
        } 

    } 
    catch (UnsupportedEncodingException g) 
    {
        System.out.println("Unsupported character set" + g); 
    } 
}
}
```

**Output**

```
String: Hello GeeksforGeeks
Result : 
-2-1072010101080108011103207101010101010701150102011101140710101010101070115
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate how to
// convert a string to byte array
// Using getBytes(Charset charset)

import java.io.*;
import java.util.Arrays;

class GFG{

public static void main (String[] args) 
{

    // Initializing String 
    String ss = "Hello GFG";

    // Display the string before conversion
    System.out.println("String: " + ss);

    try
    { 
        // Converting string to byte array
        // Using getBytes(Charset charset) method
        // Here, we converts into US-ASCII values
        byte[] res = ss.getBytes("US-ASCII"); 

        // Displaying converted string after conversion 
        // into US-ASCII 
        System.out.println("Byte Array:" + Arrays.toString(res));
    } 

    catch (UnsupportedEncodingException g) 
    {
        System.out.println("Unsupported character set" + g); 
    } 
}
}
```

**Output**

```
String: Hello GFG
Byte Array:[72, 101, 108, 108, 111, 32, 71, 70, 71]

```