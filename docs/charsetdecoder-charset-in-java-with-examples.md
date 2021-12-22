# Java 中的 CharsetDecoder charset()，示例

> 原文:[https://www . geeksforgeeks . org/charset decoder-charset-in-Java-with-examples/](https://www.geeksforgeeks.org/charsetdecoder-charset-in-java-with-examples/)

**CharsetDecoder.charset()** 是 CharsetDecoder 类的 Java 内置方法，返回创建此解码器的字符集。

**语法:**

```java
public final Charset charset()

```

**参数:**函数不接受任何参数。

**返回值:**函数返回解码器的字符集。

下面的程序演示了上述功能:

**程序 1:**

```java
// Java program below demonstrate
// CharsetDecoder.charset function

import java.nio.charset.Charset;
import java.nio.charset.CharsetDecoder;

public class Main {
    public static void main(String[] argv) throws Exception
    {
        Charset charset = Charset.forName("ISO-8859-1");

        // initialising CharsetDecoder cd
        CharsetDecoder cd = charset.newDecoder();
        // print charset of decoder cd
        System.out.println(cd.charset());
    }
}
```

**Output:**

```java
ISO-8859-1

```

**程序 2:**

```java
// Java program below demonstrate
// CharsetDecoder.charset function

import java.nio.charset.Charset;
import java.nio.charset.CharsetDecoder;

public class Main {
    public static void main(String[] argv) throws Exception
    {
        Charset charset = Charset.forName("ISO-8859-2");

        // initialising CharsetDecoder cd
        CharsetDecoder cd = charset.newDecoder();
        // print charset of decoder cd
        System.out.println(cd.charset());
    }
}
```

**Output:**

```java
ISO-8859-2

```