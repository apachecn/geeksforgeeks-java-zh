# Java 中的 CharsetDecoder isCharsetDetected()方法，示例

> 原文:[https://www . geeksforgeeks . org/charsetdecoder-is arsetdetected-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charsetdecoder-ischarsetdetected-method-in-java-with-examples/)

**isCharsetDetected()** 方法是**Java . nio . charset . charset decoder 类**的内置方法，它告诉这个解码器是否已经检测到一个字符集。该方法的默认实现总是抛出**不支持操作异常**。一旦输入字符集确定，自动检测解码器应将其置位，使其返回真。

**语法** :

```java
public boolean isCharsetDetected()
```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回一个布尔值，说明该字符集解码器是否已经检测到字符集。

**异常:**如果解码器没有实现自动检测字符集，它将抛出**不支持操作异常**

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
        Charset charset = Charset.forName("ISO-8859-1");

        // Get the CharsetDecoder
        CharsetDecoder decoder = charset.newDecoder();

        // Prints the CharsetDecoder
        System.out.println("CharsetDecoder: " + decoder);

        try {
            System.out.println("Is Charset yet detected: "
                               + decoder.isCharsetDetected());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
CharsetDecoder: sun.nio.cs.ISO_8859_1$Decoder@232204a1
java.lang.UnsupportedOperationException

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

        // Prints the CharsetDecoder
        System.out.println("CharsetDecoder: " + decoder);

        try {
            System.out.println("Is Charset yet detected: "
                               + decoder.isCharsetDetected());
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
CharsetDecoder: sun.nio.cs.ext.DoubleByte$Decoder@232204a1
java.lang.UnsupportedOperationException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charset/charset decoder . html # isCharsetDetected–](https://docs.oracle.com/javase/9/docs/api/java/nio/charset/CharsetDecoder.html#isCharsetDetected--)