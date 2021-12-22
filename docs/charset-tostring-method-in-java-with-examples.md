# Java 中的 Charset toString()方法，带示例

> 原文:[https://www . geesforgeks . org/charset-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charset-tostring-method-in-java-with-examples/)

**toString()** 方法是 **java.nio.charset** 的内置方法，它返回一个描述所涉及的字符集的字符串。

**语法** :

```java
public final String toString()
```

**参数**:该功能不接受任何参数。

**返回值**:函数返回描述该字符集的字符串。

下面是上述功能的实现:

**程序 1:**

```java
// Java program to demonstrate
// the above function

import java.nio.charset.Charset;
import java.nio.charset.CharsetDecoder;
import java.nio.charset.CharsetEncoder;

public class GFG {

    public static void main(String[] args)
    {

        // Gets charset
        Charset Charset1 = Charset.forName("UTF8");

        // Print
        System.out.println(Charset1.toString());
    }
}
```

**输出:**

```java
UTF-8

```

**程序二:**

```java
// Java program to demonstrate
// the above function

import java.nio.charset.Charset;
import java.nio.charset.CharsetDecoder;
import java.nio.charset.CharsetEncoder;

public class GFG {

    public static void main(String[] args)
    {

        // Gets charset
        Charset Charset1 = Charset.forName("UTF16");

        // Print
        System.out.println(Charset1.toString());
    }
}
```

**输出:**

```java
UTF-16

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charset/charset . html # toString–](https://docs.oracle.com/javase/9/docs/api/java/nio/charset/Charset.html#toString--)