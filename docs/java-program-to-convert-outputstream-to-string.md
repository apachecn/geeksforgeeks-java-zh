# 将输出流转换为字符串的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-convert-outputstream-to-string/](https://www.geeksforgeeks.org/java-program-to-convert-outputstream-to-string/)

[OutputStream](https://www.geeksforgeeks.org/java-io-outputstream-class-java/) 是一个抽象类，可在 java.io 包中获得。因为它是一个抽象类，为了使用它的功能，我们可以使用它的子类。一些子类是[文件输出流](https://www.geeksforgeeks.org/fileoutputstream-in-java/)、[字节数组输出流](https://www.geeksforgeeks.org/io-bytearrayoutputstream-class-java/)、[对象输出流](https://www.geeksforgeeks.org/java-io-objectoutputstream-class-java-set-1/)等。字符串只不过是一个字符序列，用双引号来表示。方法使用字符集转换流。

**方法 1:**

1.  创建字节数组输出流的对象。
2.  创建一个字符串变量并初始化它。
3.  使用 [write](https://www.geeksforgeeks.org/bytearrayoutputstream-write-method-in-java-with-examples/) 方法，将字符串的内容复制到 ByteArrayoutputStream 的对象中。
4.  打印出来。

**示例:**

```
Input : String = "Hello World"
Output: Hello World
```

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate conversion
// from outputStream to string

import java.io.*;

class GFG {

    // we know that main will throw
    // IOException so we are ducking it
    public static void main(String[] args)
        throws IOException
    {

        // declaring ByteArrayOutputStream
        ByteArrayOutputStream stream
            = new ByteArrayOutputStream();

        // Initializing string
        String st = "Hello Geek!";

        // writing the specified byte to the output stream
        stream.write(st.getBytes());

        // converting stream to byte array
        // and typecasting into string
        String finalString
            = new String(stream.toByteArray());

        // printing the final string
        System.out.println(finalString);
    }
}
```

**Output**

```
Hello Geek!
```

**方法 2:**

1.  创建一个字节数组并存储字符的 ASCII 值。
2.  创建字节数组输出流的对象。
3.  使用 [write](https://www.geeksforgeeks.org/bytearrayoutputstream-write-method-in-java-with-examples/) 方法将内容从字节数组复制到对象中。
4.  打印出来。

**示例:**

```
Input : array = [71, 69, 69, 75]
Output: GEEK 
```

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate conversion
// from outputStream to string

import java.io.*;

class GFG {
    public static void main(String[] args)
        throws IOException
    {

        // Initializing empty string
        // and byte array
        String str = "";
        byte[] bs = { 71, 69, 69, 75, 83, 70, 79,
                      82, 71, 69, 69, 75, 83 };

        // create new ByteArrayOutputStream
        ByteArrayOutputStream stream
            = new ByteArrayOutputStream();

        // write byte array to the output stream
        stream.write(bs);

        // converts buffers using default character set
        // toString is a method for casting into String type
        str = stream.toString();

        // print
        System.out.println(str);
    }
}
```

**Output**

```
GEEKSFORGEEKS
```