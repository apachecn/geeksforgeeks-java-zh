# Java 中的 Charset newDecoder()方法，带示例

> 原文:[https://www . geesforgeks . org/charset-new decoder-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charset-newdecoder-method-in-java-with-examples/)

**newDecoder()** 方法是 **java.nio.charset** 的内置方法，为这个 charset 构造一个新的解码器。
。

**语法**:

```java
public abstract CharsetDecoder newDecoder()
```

**参数**:该功能不接受任何参数。

**返回值**:该函数为该字符集返回一个新的解码器

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

        // Creates charset
        Charset Charset1 = Charset.forName("UTF8");

        // Creates Decoder
        CharsetDecoder Decoder = Charset1.newDecoder();

        // Prints decoder
        System.out.println(Decoder);
    }
}
```

**Output:**

```java
sun.nio.cs.UTF_8$Decoder@232204a1

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

        // Creates charset
        Charset Charset1 = Charset.forName("UTF-16");

        // Creates Decoder
        CharsetDecoder Decoder = Charset1.newDecoder();

        // Prints decoder
        System.out.println(Decoder);
    }
}
```

**Output:**

```java
sun.nio.cs.UTF_16$Decoder@232204a1

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charset/charset . html # new decoder–](https://docs.oracle.com/javase/9/docs/api/java/nio/charset/Charset.html#newDecoder--)