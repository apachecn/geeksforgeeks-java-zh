# Java 中的 CharsetEncoder isLegalReplacement()方法，带示例

> 原文:[https://www . geesforgeks . org/charsetencoder-islegalreplacement-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charsetencoder-islegalreplacement-method-in-java-with-examples/)

**isLegalReplacement()** 方法是**Java . nio . charset . charset encoder**的一个内置方法，它向我们指示给定的字节数组是否是该编码器的合法替换值。如果可以将替换内容解码为一个或多个十六位 Unicode 字符，则替换内容是合法的。

**语法** :

```
public boolean isLegalReplacement(byte[] repl)
```

**参数**:函数接受一个强制参数 **repl** ，指定要测试的字节数组。

**返回值**:该函数返回一个布尔值。如果字节数组是编码器的合法替代，则返回 true，否则返回 false。

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

        // Prints if legal or not
        System.out.println(encoder.isLegalReplacement(new byte[] {}));
    }
}
```

**输出:**

```
true

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

        // Prints if legal or not
        System.out.println(encoder.isLegalReplacement(new byte[] {}));
    }
}
```

**输出:**

```
true

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/nio/charset/charsetencoder . html # isLegalReplacement(字节%5B%5D)](https://docs.oracle.com/javase/10/docs/api/java/nio/charset/CharsetEncoder.html#isLegalReplacement(byte%5B%5D))