# Java 中的 CharsetDecoder malformedingputaction()方法，带示例

> 原文:[https://www . geeksforgeeks . org/charsetdecoder-malformedinputation-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charsetdecoder-malformedinputaction-method-in-java-with-examples/)

**malformedinputation()**方法是**Java . nio . charset . charset decoder 类**的一个内置方法，该类返回该解码器针对格式错误的输入错误的当前操作。

**语法** :

```java
public CodingErrorAction malformedInputAction()
```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回该解码器对格式错误输入错误的当前操作。

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

        // Prints the CharsetDecoder
        System.out.println("CharsetDecoder: " + decoder);

        System.out.println("Current action for "
                           + "malformed-input errors: "
                           + decoder.malformedInputAction());
    }
}
```

**输出:**

```java
CharsetDecoder: sun.nio.cs.ext.ISO2022_CN$Decoder@232204a1
Current action for malformed-input errors: REPORT

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

        System.out.println("Current action for "
                           + "malformed-input errors: "
                           + decoder.malformedInputAction());
    }
}
```

**输出:**

```java
CharsetDecoder: sun.nio.cs.ext.DoubleByte$Decoder@232204a1
Current action for malformed-input errors: REPORT

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charset/charset decoder . html # malformedingputaction–](https://docs.oracle.com/javase/9/docs/api/java/nio/charset/CharsetDecoder.html#malformedInputAction--)