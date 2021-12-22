# Java 中的字符集解码器重置()方法，示例

> 原文:[https://www . geesforgeks . org/charsetdecoder-reset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charsetdecoder-reset-method-in-java-with-examples/)

**reset()** 方法是**Java . nio . charset . CharsetDecoder 类**的内置方法，用于重置该 charset decoder 并清除其内部状态。

**语法** :

```java
public final CharsetDecoder reset()
```

**参数**:该功能不接受任何参数。

**返回值**:函数复位后返回该字符集解码器。

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
        Charset charset
            = Charset.forName("ISO-2022-CN");

        // Get the CharsetDecoder
        CharsetDecoder decoder
            = charset.newDecoder();

        // Prints the CharsetDecoder
        System.out.println("Before reset: "
                           + decoder);

        // Reset the CharsetDecoder
        System.out.println("After reset: "
                           + decoder.reset());
    }
}
```

**输出:**

```java
Before reset: sun.nio.cs.ext.ISO2022_CN$Decoder@232204a1
After reset: sun.nio.cs.ext.ISO2022_CN$Decoder@232204a1

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
        Charset charset
            = Charset.forName("x-windows-949");

        // Get the CharsetDecoder
        CharsetDecoder decoder
            = charset.newDecoder();

        // Prints the CharsetDecoder
        System.out.println("Before reset: "
                           + decoder);

        // Reset the CharsetDecoder
        System.out.println("After reset: "
                           + decoder.reset());
    }
}
```

**输出:**

```java
Before reset: sun.nio.cs.ext.DoubleByte$Decoder@232204a1
After reset: sun.nio.cs.ext.DoubleByte$Decoder@232204a1

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charset/charset decoder . html # reset–](https://docs.oracle.com/javase/9/docs/api/java/nio/charset/CharsetDecoder.html#reset--)