# Java 中的 CharsetEncoder reset()方法，示例

> 原文:[https://www . geesforgeks . org/charsetencoder-reset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charsetencoder-reset-method-in-java-with-examples/)

**reset()** 方法是**Java . nio . charset . charset encoder**的内置方法，重置该编码器，如果有内部状态，则清除所有内部状态。它还重置独立于字符集的状态，并调用 implReset 方法来执行任何特定于字符集的重置操作。

**语法** :

```java
public final CharsetEncoder reset()
```

**参数**:该功能不接受任何参数。

**返回值**:该功能复位特定的编码器。

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
        CharsetEncoder encoder
            = Charset.forName("US-ASCII")
                  .newEncoder();

        // It will reset the encoder
        // and clear all internal activities if there are
        encoder.reset();

        // Prints the encoder after resetting it
        System.out.println(encoder);
    }
}
```

**输出:**

```java
sun.nio.cs.US_ASCII$Encoder@232204a1

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
        CharsetEncoder encoder
            = Charset.forName("UTF8")
                  .newEncoder();

        // It will reset the encoder
        // and clear all internal activities if there are
        encoder.reset();

        // Prints the encoder after resetting it
        System.out.println(encoder);
    }
}
```

**输出:**

```java
sun.nio.cs.UTF_8$Encoder@232204a1

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/nio/charset/charsetencoder . html # reset()](https://docs.oracle.com/javase/10/docs/api/java/nio/charset/CharsetEncoder.html#reset())