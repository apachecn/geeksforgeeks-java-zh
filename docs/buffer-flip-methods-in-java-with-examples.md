# Java 中的缓冲区翻转()方法，示例

> 原文:[https://www . geesforgeks . org/buffer-flip-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/buffer-flip-methods-in-java-with-examples/)

**[java.nio.ByteBuffer 类](https://www.geeksforgeeks.org/tag/java-bytebuffer/)** 的 **flip()** 方法用来翻转这个缓冲区。极限被设置为当前位置，然后位置被设置为零。如果标记被定义，那么它被丢弃。在一系列通道读取或放置操作之后，调用此方法为一系列通道写入或相关的获取操作做准备。

**例如:**

```
buf.put(magic);    // Prepend header
in.read(buf);      // Read data into rest of buffer
buf.flip();        // Flip buffer
out.write(buf);    // Write header + data to channel

```

当从一个地方向另一个地方传输数据时，此方法通常与 compact()方法结合使用。

**语法:**

```
public Buffer flip()
```

**返回值:**这个方法返回这个缓冲区。

下面是一些示例来说明 flip()方法:

**示例 1:**

```
// Java program to demonstrate
// flip() method

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

        // set position at index 1
        buffer.position(1);

        // print the buffer
        System.out.println("Buffer before flip: "
                           + Arrays.toString((byte[])buffer.array())
                           + "\nPosition: " + buffer.position()
                           + "\nLimit: " + buffer.limit());

        // Flip the Buffer
        // using flip() method
        buffer.flip();

        // print the buffer
        System.out.println("\nBuffer after flip: "
                           + Arrays.toString((byte[])buffer.array())
                           + "\nPosition: " + buffer.position()
                           + "\nLimit: " + buffer.limit());
    }
}
```

**输出:**

```
Buffer before flip: [10, 20, 30]
Position: 1
Limit: 3

Buffer after flip: [10, 20, 30]
Position: 0
Limit: 1

```

**示例 2:**

```
// Java program to demonstrate
// flip() method

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
        byteBuffer.put((byte)30);

        // Typecast ByteBuffer to Buffer
        Buffer buffer = (Buffer)byteBuffer;

        // set position at index 1
        buffer.position(1);

        // print the buffer
        System.out.println("Buffer before flip: "
                           + Arrays.toString((byte[])buffer.array())
                           + "\nPosition: " + buffer.position()
                           + "\nLimit: " + buffer.limit());

        // Flip the Buffer
        // using flip() method
        buffer.flip();

        // print the buffer
        System.out.println("\nBuffer after flip: "
                           + Arrays.toString((byte[])buffer.array())
                           + "\nPosition: " + buffer.position()
                           + "\nLimit: " + buffer.limit());
    }
}
```

**输出:**

```
Buffer before flip: [20, 30, 0, 0]
Position: 1
Limit: 4

Buffer after flip: [20, 30, 0, 0]
Position: 0
Limit: 1

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/buffer . html # flip–](https://docs.oracle.com/javase/9/docs/api/java/nio/Buffer.html#flip--)