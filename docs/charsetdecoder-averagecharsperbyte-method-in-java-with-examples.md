# Java 中的 CharsetDecoder averageCharsPerByte()方法，示例

> 原文:[https://www . geeksforgeeks . org/charsetdecoder-averagecharsperbyte-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charsetdecoder-averagecharsperbyte-method-in-java-with-examples/)

**averageCharsPerByte()** 方法是**Java . nio . charset . charset decoder 类**的内置方法，它返回每个输入字节将产生的平均字符数。该试探值可用于估计给定输入序列所需的输出缓冲器的大小。

**语法** :

```
public final float averageCharsPerByte()
```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回输入的每个字节将产生的平均字符数。

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

        // Prints the averageCharsPerByte
        System.out.println("The averageCharsPerByte "
                           + "for ISO-2022-CN is "
                           + decoder.averageCharsPerByte());
    }
}
```

**输出:**

```
The averageCharsPerByte for ISO-2022-CN is 1.0

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

        // Prints the averageCharsPerByte
        System.out.println("The averageCharsPerByte "
                           + "for ISO-2022-CN is "
                           + decoder.averageCharsPerByte());
    }
}
```

**输出:**

```
The averageCharsPerByte for ISO-2022-CN is 0.5

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charset/charset decoder . html # averageCharsPerByte–](https://docs.oracle.com/javase/9/docs/api/java/nio/charset/CharsetDecoder.html#averageCharsPerByte--)