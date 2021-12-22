# Java 中的 CharsetEncoder charset()方法，带示例

> 原文:[https://www . geeksforgeeks . org/charset encoder-charset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charsetencoder-charset-method-in-java-with-examples/)

**字符集()**方法是**Java . nio . charset . charset encoder**的内置方法，返回创建此编码器的字符集。

**语法** :

```java
public final Charset charset()
```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回该编码器的字符集。

下面是上述功能的实现:

**程序 1:**

```java
// Java program to implement
// the above function
import java.nio.CharBuffer;
import java.nio.charset.Charset;
import java.nio.charset.CharsetEncoder;

public class Main {
    public static void main(String[] args) throws Exception
    {
        // Gets the encoder
        CharsetEncoder encoder = Charset.forName("UTF16").newEncoder();

        // Prints CodingErrorAction
        System.out.println(encoder.charset());
    }
}
```

**输出:**

```java
UTF-16

```

**程序二:**

```java
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

        // Prints CodingErrorAction
        System.out.println(encoder.charset());
    }
}
```

**输出:**

```java
UTF-8

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/nio/charset/charset encoder . html # charset()](https://docs.oracle.com/javase/10/docs/api/java/nio/charset/CharsetEncoder.html#charset())