# Java 中的 Charset newEncoder()方法，带示例

> 原文:[https://www . geesforgeks . org/charset-new encoder-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charset-newencoder-method-in-java-with-examples/)

**newEncoder()** 方法是 **java.nio.charset** 的内置方法，为这个 charset 构造一个新的编码器。

**语法** :

```java
public abstract CharsetEncoder newEncoder()
```

**参数**:该功能不接受任何参数。

**返回值**:该函数为该字符集返回一个新的编码器

**错误和异常**:如果字符集不支持编码，函数抛出**不支持操作异常**。

下面是上述功能的实现:

**程序 1:**

```java
// Java program to demonstrate
// the above function

import java.nio.charset.Charset;
import java.nio.charset.CharsetDecoder;
import java.nio.charset.CharsetEncoder;

public class GFG {

    public static void main(String[] args)
    {

        // Generates charset
        Charset Charset1 = Charset.forName("UTF8");

        // Gets encoder
        CharsetEncoder outEncoder = Charset1.newEncoder();

        // Prints it
        System.out.println(outEncoder);
    }
}
```

**输出:**

```java
sun.nio.cs.UTF_8$Encoder@232204a1

```

**程序 2:**

```java
// Java program to demonstrate
// the above function
import java.nio.charset.Charset;
import java.nio.charset.CharsetDecoder;
import java.nio.charset.CharsetEncoder;
public class GFG {

    public static void main(String[] args)
    {

        // Generates charset
        Charset Charset1 = Charset.forName("UTF16");

        // Gets encoder
        CharsetEncoder outEncoder = Charset1.newEncoder();

        // Prints it
        System.out.println(outEncoder);
    }
}
```

**输出:**

```java
sun.nio.cs.UTF_16$Encoder@232204a1

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charset/charset . html # new encoder–](https://docs.oracle.com/javase/9/docs/api/java/nio/charset/Charset.html#newEncoder--)