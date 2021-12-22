# Java 中 BufferedInputStream markSupported()方法，示例

> 原文:[https://www . geeksforgeeks . org/bufferedinputstream-marksupported-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bufferedinputstream-marksupported-method-in-java-with-examples/)

Java 中 **BufferedInputStream** 类的 **markSupported()** 方法用于验证输入流是否支持**标记**、**重置**方法。如果输入流不支持这两种方法中的任何一种，那么程序将返回 false 否则返回 true。

**语法:**

```java
public boolean markSupported()

```

**参数:**此方法不接受任何参数。

**返回值:**此方法返回一个**布尔值**，指示标记和重置方法的可支持性。

**覆盖:**该方法被 **FilterInputStream** 类中的*标记支持的*覆盖。

**异常:**此方法不抛出任何异常。

下面的程序说明了 IO 包中 BufferedInputStream 类中的 markSupported()方法:

**程序 1:** 假设文件“c:/demo.txt”存在。

```java
// Java program to illustrate
// BufferedInputStream markSupported() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
    {

        // Create input stream 'demo.txt'
        // for reading containing text "GEEKS"
        FileInputStream inputStream
            = new FileInputStream(
                "c:/demo.txt");

        // Convert inputStream to
        // bufferedInputStream
        BufferedInputStream buffInputStr
            = new BufferedInputStream(
                inputStream);

        // Returns true if mark()
        // and reset () supports
        boolean bool
            = buffInputStr
                  .markSupported();

        System.out.println(
"Support for mark()"
+" and reset(): "
 + bool);
    }
}
```

**输出:**

```java
Support for mark() and reset() : true

```

**程序二:**假设文件“c:/demo.txt”存在。

```java
// Java program to illustrate
// BufferedInputStream.markSupported() method

import java.io.*;

public class GFG {
    public static void main(String[] args)
    {

        // Create input stream 'demo.txt'
        // for reading containing text "MRNOTSUPP"
        FileInputStream inputStream
            = new FileInputStream("c:/demo.txt");

        // Convert inputStream to
        // bufferedInputStream
        BufferedInputStream buffInputStr
            = new BufferedInputStream(inputStream);

        // Returns false if mark()
// and reset () not supported
        boolean bool
 = buffInputStr.markSupported();

        System.out.println(
"Support for mark()"
+" and reset(): "
 + bool);
    }
}
```

**输出:**

```java
Support for mark() and reset() : false

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/io/bufferedinputstream . html # markSupported()](https://docs.oracle.com/javase/10/docs/api/java/io/BufferedInputStream.html#markSupported())