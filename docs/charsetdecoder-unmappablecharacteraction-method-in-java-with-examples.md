# Java 中的 CharsetDecoder unappablecharactor action()方法，示例

> 原文:[https://www . geesforgeks . org/charsetdecoder-unappablecharactor action-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charsetdecoder-unmappablecharacteraction-method-in-java-with-examples/)

**unappable character action()**方法是**Java . nio . charset . charsetdecoder 类**的一个内置方法，该类返回该解码器的当前操作以查找不可映射的字符错误。

**语法** :

```java
public CodingErrorAction unmappableCharacterAction()
```

**参数**:该功能不接受任何参数。

**返回值**:对于不可映射的字符错误，该函数返回该解码器的当前动作。

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
                           + "unmappable-character errors: "
                           + decoder.unmappableCharacterAction());
    }
}
```

**输出:**

```java
CharsetDecoder: sun.nio.cs.ext.ISO2022_CN$Decoder@232204a1
Current action for unmappable-character errors: REPORT

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
                           + "unmappable-character errors: "
                           + decoder.unmappableCharacterAction());
    }
}
```

**输出:**

```java
CharsetDecoder: sun.nio.cs.ext.DoubleByte$Decoder@232204a1
Current action for unmappable-character errors: REPORT

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charset/charset decoder . html # unappablecharactor action–](https://docs.oracle.com/javase/9/docs/api/java/nio/charset/CharsetDecoder.html#unmappableCharacterAction--)