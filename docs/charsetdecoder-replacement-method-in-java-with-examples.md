# Java 中的 CharsetDecoder 替换()方法，示例

> 原文:[https://www . geeksforgeeks . org/charsetdecoder-replacement-in-Java-method-with-examples/](https://www.geeksforgeeks.org/charsetdecoder-replacement-method-in-java-with-examples/)

**replacement()** 方法是**Java . nio . charset . charset decoder 类**的内置方法，返回该解码器的替换值。需要设置替换值才能获得有效的替换值。

**语法** :

```
public final Charset replacement()
```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回该解码器的替换值。

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

        System.out.println("Replacement Value: "
                           + decoder.replacement());
    }
}
```

**输出:**

```
CharsetDecoder: sun.nio.cs.ext.ISO2022_CN$Decoder@232204a1
Replacement Value: ?

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

        System.out.println("Replacement Value: "
                           + decoder.replacement());
    }
}
```

**输出:**

```
CharsetDecoder: sun.nio.cs.ext.DoubleByte$Decoder@232204a1
Replacement Value: ?

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charset/charset decoder . html # replacement–](https://docs.oracle.com/javase/9/docs/api/java/nio/charset/CharsetDecoder.html#replacement--)