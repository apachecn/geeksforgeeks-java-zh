# 字节缓冲区是 Java 中的直接()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-is direct-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-isdirect-methods-in-java-with-examples/)

**[java.nio.ByteBuffer 类](https://www.geeksforgeeks.org/tag/java-bytebuffer/)** 的 **isDirect()** 方法用来判断这个字节缓冲区是否是直接的。

**语法:**

```java
public abstract boolean isDirect()
```

**返回值:**当且仅当该缓冲区是直接的时，该方法返回真。

以下是说明**是直接()**方法的例子:

**示例 1:**

```java
// Java program to demonstrate
// isDirect() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating ByteBuffer
        // using allocate() method
        ByteBuffer byteBuffer
            = ByteBuffer.allocateDirect(4);

        // check the byteBuffer
        // using isDirect() method
        boolean val = byteBuffer.isDirect();

        // checking the condition
        if (val)
            System.out.println("buffer is direct");
        else
            System.out.println("buffer is not direct");
    }
}
```

**输出:**

```java
buffer is direct

```

**示例 2:**

```java
// Java program to demonstrate
// isDirect() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating ByteBuffer
        // using allocate() method
        ByteBuffer byteBuffer = ByteBuffer.allocate(4);

        // check the byteBuffer
        // using isDirect() method
        boolean val = byteBuffer.isDirect();

        // checking the condition
        if (val)
            System.out.println("buffer is direct");
        else
            System.out.println("buffer is not direct");
    }
}
```

**输出:**

```java
buffer is not direct

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # isDirect–](https://docs.oracle.com/javase/9/docs/api/java/nio/ByteBuffer.html#isDirect--)