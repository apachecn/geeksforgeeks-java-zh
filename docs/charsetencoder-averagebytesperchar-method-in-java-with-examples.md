# Java 中的 CharsetEncoder averageBytesPerChar()方法，示例

> 原文:[https://www . geeksforgeeks . org/charsetencoder-averagebytesperchar-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charsetencoder-averagebytesperchar-method-in-java-with-examples/)

**averageBytesPerChar()** 方法是**Java . nio . charset . charset encoder**的内置方法，它返回所提供的每个输入字符将产生的平均字节数。启发式值因此被用于估计给定输入序列所需的输出缓冲器的大小。

**语法** :

```java
public final float averageBytesPerChar()
```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回输入的每个字符产生的平均字节数。

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

        // Gets the new encoder
        CharsetEncoder encoder = Charset.forName("US-ASCII").newEncoder();

        // Prints the average bytes
        System.out.println(encoder.averageBytesPerChar());
    }
}
```

**输出:**

```java
1.0

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

        // Gets the new encoder
        CharsetEncoder encoder = Charset.forName("UTF8").newEncoder();

        // Prints the average bytes
        System.out.println(encoder.averageBytesPerChar());
    }
}
```

**输出:**

```java
1.1

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/nio/charset/charsetencoder . html # averageBytesPerChar()](https://docs.oracle.com/javase/10/docs/api/java/nio/charset/CharsetEncoder.html#averageBytesPerChar())