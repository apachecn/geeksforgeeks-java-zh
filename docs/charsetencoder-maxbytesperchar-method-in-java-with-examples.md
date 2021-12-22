# Java 中的 CharsetEncoder maxBytesPerChar()方法，带示例

> 原文:[https://www . geesforgeks . org/charsetencoder-maxbytesperchar-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charsetencoder-maxbytesperchar-method-in-java-with-examples/)

**maxBytesPerChar()** 方法是**Java . nio . charset . charset encoder**的内置方法，返回输入的每个字符将产生的最大字节数。这样返回的值用于获取给定输入句子在最坏情况下所需的输出缓冲区大小。

**语法** :

```
public final float maxBytesPerChar()
```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回每个输入字符将产生的最大字节数

下面是上述功能的实现:

**程序 1:**

```
// Java program to implement
// the above function
import java.nio.CharBuffer;
import java.nio.charset.Charset;
import java.nio.charset.CharsetEncoder;

public class Main {
    public static void main(String[] args) throws Exception
    {
        // Gets the encoder
        CharsetEncoder encoder = Charset.forName("UTF8").newEncoder();

        // Prints max bytes per char
        System.out.println(encoder.maxBytesPerChar());
    }
}
```

**输出:**

```
3.0

```

**程序二:**

```
// Java program to implement
// the above function
import java.nio.CharBuffer;
import java.nio.charset.Charset;
import java.nio.charset.CharsetEncoder;

public class Main {
    public static void main(String[] args) throws Exception
    {
        // Gets the encoder
        CharsetEncoder encoder = Charset.forName("US-ASCII").newEncoder();

        // Prints max bytes per char
        System.out.println(encoder.maxBytesPerChar());
    }
}
```

**输出:**

```
1.0

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/nio/charset/charsetencoder . html # maxBytesPerChar()](https://docs.oracle.com/javase/10/docs/api/java/nio/charset/CharsetEncoder.html#maxBytesPerChar())