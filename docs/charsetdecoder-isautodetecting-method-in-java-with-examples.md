# CharsetDecoder 是 Java 中的一个自动检测()方法，示例

> 原文:[https://www . geesforgeks . org/charsetdecoder-isaautodetection-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charsetdecoder-isautodetecting-method-in-java-with-examples/)

**isaautodetecting()**方法是**Java . nio . charset . charset decoder 类**的内置方法，它告诉这个解码器是否实现了自动检测字符集。

**语法** :

```
public boolean isAutoDetecting()
```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回一个布尔值，说明该字符集解码器是否实现了自动检测字符集。

下面是上述功能的实现:

**程序 1:**

```
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

        System.out.println("Is CharsetDecoder auto-detecting: "
                           + decoder.isAutoDetecting());
    }
}
```

**输出:**

```
CharsetDecoder: sun.nio.cs.ext.ISO2022_CN$Decoder@232204a1
Is CharsetDecoder auto-detecting: false

```

**程序二:**

```
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

        System.out.println("Is CharsetDecoder auto-detecting: "
                           + decoder.isAutoDetecting());
    }
}
```

**输出:**

```
CharsetDecoder: sun.nio.cs.ext.DoubleByte$Decoder@232204a1
Is CharsetDecoder auto-detecting: false

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charset/charset decoder . html # isaautodetecting–](https://docs.oracle.com/javase/9/docs/api/java/nio/charset/CharsetDecoder.html#isAutoDetecting--)