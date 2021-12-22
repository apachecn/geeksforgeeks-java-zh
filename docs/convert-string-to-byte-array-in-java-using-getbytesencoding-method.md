# 使用 getBytes(编码)方法将字符串转换为 Java 中的字节数组

> 原文:[https://www . geesforgeks . org/convert-string-to-byte-array-in-Java-using-getbytesencoding-method/](https://www.geeksforgeeks.org/convert-string-to-byte-array-in-java-using-getbytesencoding-method/)

在 Java 中，双引号内的任何字符序列都被视为字符串。String 类表示字符串文本。字符串类存在于 java.lang 包中。java 中的所有字符串都是不可变的，也就是说，一旦创建，它们的值就不能改变。在 Java 中，字符串以 Unicode 字符数组的形式存储。字节数组是字节数组。我们可以使用字节数组来存储二进制数据的集合。

为了将字符串文字转换为字节数组，我们必须首先将字符序列转换为字节序列，对于这种转换，我们可以使用**字符集的实例。**

它是存在于[**java.nio 包**](https://www.geeksforgeeks.org/introduction-to-java-nio-with-examples/) 中的抽象类，用于定义十六位 **UTF-16** 代码单元序列之间的映射，即字符序列和字节序列。基本上，它主要用于字符集和 unicode 的编码和解码。我们在上面讨论的将字符串转换成字节数组的过程被定义为编码，即我们将字符串的每个字符编码成一个字节。

**语法:**

```
public byte[] getBytes(String charsetName) throws UnsupportedEncodingException  
```

此方法使用命名字符集将字符串编码为字节，并返回字节数组，但是如果不支持命名字符集，此方法可能会引发 UnsupportedEncodingException。所以为了处理异常，我们使用 try-catch 块。

**进场:**

*   在下面的程序中**[**getBytes()**](https://www.geeksforgeeks.org/java-lang-string-getbyte-java/)**方法通过使用 UTF-16 (16 是一个位数)编码常量将字符串文字转换为字节。****
*   ****其中 UTF 是 Unicode 转换格式，用于对字符进行编码。UTF 有很多变体，如 UTF-8，它在编码字符时最少使用一个字节，其中 UTF-16 使用 2 个字节，UTF-32 使用 4 个字节。****
*   ****在下面的程序中，我们使用 UTF-16，它至少需要 2 个字节来编码一个字符，也就是为什么结果字节数组的长度与给定字符串的长度不同。但是如果你使用 UTF-8，你得到的结果数组的长度和输入字符串的长度一样，因为 UTF-8 需要一个字节来编码一个字符。****

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
**// Java program to Convert String to Byte Array
// Using getBytes(encoding)

import java.io.*;
import java.lang.*;
import java.nio.*;
import java.nio.charset.Charset;
import java.util.*;

// class to convert string literal into byte array
class GFG {
    public static void main(String[] args)
    {

        // using try-catch to handle the exception
        try {

            // taking unput string
            String s = "GeeksForGeeks";

            // name of supported charset
            // UTF-16 is an encoding constant
            String charsetName = "UTF-16";

            // UTF-16 charset encoding and storing the
            // resultant bytearray.
            byte[] byteArray = s.getBytes("UTF-16");

            // printing the byte array to convert it into
            // string
            System.out.println(Arrays.toString(byteArray));

            // printing the length of input string and
            // resultant byte array
            System.out.println("Length of String"
                               + " " + s.length() + " "
                               + "Length of byte Array"
                               + " " + byteArray.length);
        }
        catch (UnsupportedEncodingException e) {
            System.out.println("Unsupported cahrset :" + e);
        }
    }
}**
```

******Output**

```
[-2, -1, 0, 71, 0, 101, 0, 101, 0, 107, 0, 115, 0, 70, 0, 111, 0, 114, 0, 71, 0, 101, 0, 101, 0, 107, 0, 115]
Length of String 13 Length of byte Array 28

```****