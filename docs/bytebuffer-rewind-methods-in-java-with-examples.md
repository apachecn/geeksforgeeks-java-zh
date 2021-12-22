# Java 中的字节缓冲倒带()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-rewind-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-rewind-methods-in-java-with-examples/)

[java.nio.ByteBuffer 类](https://www.geeksforgeeks.org/tag/java-bytebuffer/)的**倒带()**方法用来倒带这个缓冲区。位置设置为零，标记被丢弃。假设已经适当地设置了限制，则在一系列通道写入或获取操作之前调用此方法。调用此方法既不会改变也不会丢弃标记的值。

**语法:**

```java
public ByteBuffer rewind()
```

**返回值:**这个方法返回这个缓冲区。

以下是说明 rewind()方法的示例:

**示例 1:**

```java
// Java program to demonstrate
// rewind() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating ByteBuffer
        // using allocate() method
        ByteBuffer byteBuffer = ByteBuffer.allocate(4);

        // put byte value in byteBuffer
        // using put() method
        byteBuffer.put((byte)20);
        byteBuffer.put((byte)'a');

        // print the byte buffer
        System.out.println("Buffer before operation: "
                           + Arrays.toString(byteBuffer.array())
                           + "\nPosition: " + byteBuffer.position()
                           + "\nLimit: " + byteBuffer.limit());

        // rewind the Buffer
        // using rewind() method
        byteBuffer.rewind();

        // print the bytebuffer
        System.out.println("\nBuffer after operation: "
                           + Arrays.toString(byteBuffer.array())
                           + "\nPosition: " + byteBuffer.position()
                           + "\nLimit: " + byteBuffer.limit());
    }
}
```

**输出:**

```java
Buffer before operation: [20, 97, 0, 0]
Position: 2
Limit: 4

Buffer after operation: [20, 97, 0, 0]
Position: 0
Limit: 4

```

**示例 2:**

```java
// Java program to demonstrate
// rewind() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating ByteBuffer
        // using allocate() method
        ByteBuffer byteBuffer = ByteBuffer.allocate(5);

        // put byte value in byteBuffer
        // using put() method
        byteBuffer.put((byte)20);
        byteBuffer.put((byte)30);
        byteBuffer.put((byte)40);

        // mark will be going to discarded by rewind()
        byteBuffer.mark();

        // print the buffer
        System.out.println("Buffer before operation: "
                           + Arrays.toString(byteBuffer.array())
                           + "\nPosition: " + byteBuffer.position()
                           + "\nLimit: " + byteBuffer.limit());

        // Rewind the Buffer
        // using rewind() method
        byteBuffer.rewind();

        // print the buffer
        System.out.println("\nBuffer after operation: "
                           + Arrays.toString(byteBuffer.array())
                           + "\nPosition: " + byteBuffer.position()
                           + "\nLimit: " + byteBuffer.limit());
    }
}
```

**输出:**

```java
Buffer before operation: [20, 30, 40, 0, 0]
Position: 3
Limit: 5

Buffer after operation: [20, 30, 40, 0, 0]
Position: 0
Limit: 5

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # rewind–](https://docs.oracle.com/javase/9/docs/api/java/nio/ByteBuffer.html#rewind--)