# Java 中的 CharsetDecoder maxCharsPerByte()方法，带示例

> 原文:[https://www . geesforgeks . org/charsetdecoder-maxcharsperbyte-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charsetdecoder-maxcharsperbyte-method-in-java-with-examples/)

**maxCharsPerByte()** 方法是**Java . nio . charset . charset decoder 类**的内置方法，它返回每个输入字节将产生的最大字符数。该值可用于计算给定输入序列所需的输出缓冲器的最坏情况大小。

**语法** :

```java
public final float maxCharsPerByte()
```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回输入的每个字节将产生的最大字符数。

下面是上述功能的实现:

**程序 1:**

```java
// Java program to demonstrate
// the above function

import java.nio.charset.*;
import java.util.Iterator;
import java.util.Map;

public class GFG {

    public static void main(String[] args)
    {

        // Gets the charset
        Charset charset = Charset.forName("ISO-2022-CN");

        // Get the CharsetDecoder
        CharsetDecoder decoder = charset.newDecoder();

        // Prints the maxCharsPerByte
        System.out.println("The maxCharsPerByte for "
                           + "ISO-2022-CN is "
                           + decoder.maxCharsPerByte());
    }
}
```

**输出:**

```java
The maxCharsPerByte for ISO-2022-CN is 1.0

```

**程序二:**

```java
// Java program to demonstrate
// the above function

import java.nio.charset.*;
import java.util.Iterator;
import java.util.Map;

public class GFG {

    public static void main(String[] args)
    {

        // Gets the charset
        Charset charset = Charset.forName("x-windows-949");

        // Get the CharsetDecoder
        CharsetDecoder decoder = charset.newDecoder();

        // Prints the maxCharsPerByte
        System.out.println("The maxCharsPerByte for "
                           + "ISO-2022-CN is "
                           + decoder.maxCharsPerByte());
    }
}
```

**输出:**

```java
The maxCharsPerByte for ISO-2022-CN is 1.0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charset/charset decoder . html # maxCharsPerByte–](https://docs.oracle.com/javase/9/docs/api/java/nio/charset/CharsetDecoder.html#maxCharsPerByte--)