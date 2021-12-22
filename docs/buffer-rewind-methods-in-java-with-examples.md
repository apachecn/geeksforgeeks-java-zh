# Java 中的缓冲倒带()方法，示例

> 原文:[https://www . geesforgeks . org/buffer-rewind-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/buffer-rewind-methods-in-java-with-examples/)

[java.nio.ByteBuffer 类](https://www.geeksforgeeks.org/tag/java-bytebuffer/)的**倒带()**方法用来倒带这个缓冲区。位置设置为零，标记被丢弃。假设已经适当地设置了限制，则在一系列通道写入或获取操作之前调用此方法。调用此方法既不会改变也不会丢弃标记的值。

**语法:**

```
public ByteBuffer rewind()
```

**返回值:**这个方法返回这个缓冲区。

以下是说明 rewind()方法的示例:

**示例 1:**

```
// Java program to demonstrate
// rewind() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating ByteBuffer
        // using allocate() method
        ByteBuffer byteBuffer
            = ByteBuffer.allocate(4);

        // put byte value in byteBuffer
        // using put() method
        byteBuffer.put((byte)20);
        byteBuffer.put((byte)'a');

        // Typecast Bytebuffer to buffer
        Buffer buffer = (Buffer)byteBuffer;

        // print the byte buffer
        System.out.println("Buffer before operation: "
                           + Arrays.toString(
                                 (byte[])buffer.array())
                           + "\nPosition: "
                           + buffer.position()
                           + "\nLimit: "
                           + buffer.limit());

        // rewind the Buffer
        // using rewind() method
        buffer.rewind();

        // print the bytebuffer
        System.out.println("\nBuffer after operation: "
                           + Arrays.toString(
                                 (byte[])buffer.array())
                           + "\nPosition: "
                           + buffer.position()
                           + "\nLimit: "
                           + buffer.limit());
    }
}
```

**输出:**

```
Buffer before operation: [20, 97, 0, 0]
Position: 2
Limit: 4

Buffer after operation: [20, 97, 0, 0]
Position: 0
Limit: 4

```

**示例 2:**

```
// Java program to demonstrate
// rewind() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating ByteBuffer
        // using allocate() method
        ByteBuffer byteBuffer
            = ByteBuffer.allocate(5);

        // put byte value in byteBuffer
        // using put() method
        byteBuffer.put((byte)20);
        byteBuffer.put((byte)30);
        byteBuffer.put((byte)40);

        // mark will be going to discard
        // by rewind()
        byteBuffer.mark();

        // Typecast Bytebuffer to buffer
        Buffer buffer = (Buffer)byteBuffer;

        // print the buffer
        System.out.println("Buffer before operation: "
                           + Arrays.toString(
                                 (byte[])buffer.array())
                           + "\nPosition: "
                           + buffer.position()
                           + "\nLimit: "
                           + buffer.limit());

        // rewind the Buffer
        // using rewind() method
        buffer.rewind();

        // print the bytebuffer
        System.out.println("\nBuffer after operation: "
                           + Arrays.toString(
                                 (byte[])buffer.array())
                           + "\nPosition: "
                           + buffer.position()
                           + "\nLimit: "
                           + buffer.limit());
    }
}
```

**输出:**

```
Buffer before operation: [20, 30, 40, 0, 0]
Position: 3
Limit: 5

Buffer after operation: [20, 30, 40, 0, 0]
Position: 0
Limit: 5

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/buffer . html # rewind–](https://docs.oracle.com/javase/9/docs/api/java/nio/Buffer.html#rewind--)