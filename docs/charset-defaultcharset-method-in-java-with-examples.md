# Java 中的 Charset defaultCharset()方法，带示例

> 原文:[https://www . geeksforgeeks . org/charset-defaultcharset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/charset-defaultcharset-method-in-java-with-examples/)

**defaultCharset()** 方法是 **java.nio.Charset** 的内置方法，它返回默认字符集的 charset 对象。默认字符集基本上由 Java 虚拟机决定，它基本上取决于机器底层操作系统中的字符集。总之，结果会因机器而异。

**语法** :

```java
public static Charset defaultCharset()
```

**参数**:该功能不接受任何参数。

**返回值**:该函数返回默认字符集的字符集对象。

下面是上述功能的实现:

**程序 1:**

```java
// Java program to demonstrate
// the above function
import java.nio.charset.Charset;
import java.util.Iterator;
import java.util.Map;

public class GFG {

    public static void main(String[] args)
    {

        // Get the default charset of the machine
        Charset cs = Charset.defaultCharset();

        System.out.println("The default charset of the machine is :" + cs.displayName());
    }
}
```

**输出:**

```java
The default charset of the machine is :US-ASCII

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/nio/charset/charset . html # defaultCharset()](https://docs.oracle.com/javase/10/docs/api/java/nio/charset/Charset.html#defaultCharset())