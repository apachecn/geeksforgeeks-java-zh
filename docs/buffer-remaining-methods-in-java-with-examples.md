# Java 中的缓冲剩余()方法，示例

> 原文:[https://www . geesforgeks . org/buffer-restrict-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/buffer-remaining-methods-in-java-with-examples/)

**[Java . nio . buffer Class](https://www.geeksforgeeks.org/tag/java-bytebuffer/)**的**(剩余)**方法用于返回当前位置与极限之间的元素个数。

**语法:**

```java
public final int remaining()
```

**返回值:**这个方法返回这个缓冲区中剩余的元素数量。

以下是说明剩余()方法的示例:

**示例 1:**

```java
// Java program to demonstrate
// remaining() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declare and initialize the byte array
        byte[] bb = { 10, 20, 30 };

        // wrap the byte array into ByteBuffer
        // using wrap() method
        ByteBuffer byteBuffer = ByteBuffer.wrap(bb);

        // Typecast ByteBuffer to Buffer
        Buffer buffer = (Buffer)byteBuffer;

        // get the number of element present in the Buffer
        // using remaining() method
        int element = buffer.remaining();

        // print the buffer
        System.out.println("Remaining element in buffer : "
                           + element);
    }
}
```

**输出:**

```java
Remaining element in buffer : 3

```

**示例 2:**

```java
// Java program to demonstrate
// remaining() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // defining and allocating ByteBuffer
        // using allocate() method
        ByteBuffer byteBuffer = ByteBuffer.allocate(7);

        // put byte value in byteBuffer
        // using put() method
        byteBuffer.put((byte)20); // 1 byte space required
        byteBuffer.put((byte)30); // 1 byte space required
        byteBuffer.putInt(40); // 4 byte space required

        // Typecast ByteBuffer to Buffer
        Buffer buffer = (Buffer)byteBuffer;

        // get the number of element present in the Buffer
        // using remaining() method
        int element = buffer.remaining();

        // print the buffer
        System.out.println("Remaining element in buffer : "
                           + element);
    }
}
```

**输出:**

```java
Remaining element in buffer : 1

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/buffer . html #剩余–](https://docs.oracle.com/javase/9/docs/api/java/nio/Buffer.html#remaining--)