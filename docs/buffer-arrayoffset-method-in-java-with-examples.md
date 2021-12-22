# Java 中的缓冲区 arrayOffset()方法，带示例

> 原文:[https://www . geesforgeks . org/buffer-arrayoffset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/buffer-arrayoffset-method-in-java-with-examples/)

**java.nio.Buffer** 类的 **arrayOffset()** 方法用于返回给定缓冲区的后备数组中缓冲区第一个元素的偏移量。

如果这个缓冲区由一个数组支持，那么缓冲区位置 p 对应于数组索引 p + arrayOffset()。

在调用此方法之前，调用 **hasArray** 方法，以确保此缓冲区具有可访问的后备数组。

**语法:**

```
public abstract int arrayOffset()
```

**返回值:**该方法返回该缓冲区数组中缓冲区第一个元素的偏移量

**异常::**如果此缓冲区由数组支持但为只读，则此方法将引发*readonlybufferenexception，*。

以下是说明 arrayOffset()方法的示例:

**例 1:**

```
// Java program to demonstrate
// arrayOffset() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 4;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the int to byte
            // typecast value in ByteBuffer
            bb.put((byte)20);
            bb.put((byte)30);
            bb.put((byte)40);
            bb.put((byte)50);

            // Typecasting ByteBuffer into Buffer
            Buffer buffer = (Buffer)bb;

            // offset within this buffer's array
            // of the first element of the buffer
            // using arrayOffset() method
            int offset = buffer.arrayOffset();

            // print the array
            System.out.println("arrayOffset is : "
                               + offset);
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("buffer is backed by an "
                               + "array but is read-only");
            System.out.println("Exception throws: " + e);
        }
    }
}
```

**输出:**

```
arrayOffset is : 0

```

**例 2:** 为 readonly buffer exception

```
// Java program to demonstrate
// arrayOffset() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 4;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the int to byte typecast
            // value in ByteBuffer
            bb.put((byte)20);
            bb.put((byte)30);
            bb.put((byte)40);
            bb.put((byte)50);

            // Creating a read-only copy of  ByteBuffer
            // using asReadOnlyBuffer() method
            ByteBuffer bb1 = bb.asReadOnlyBuffer();

            // Typecasting read-only ByteBuffer
            // into read-only Buffer
            Buffer buffer = (Buffer)bb1;

            // offset within this buffer's array
            // of the first element of the buffer
            // using arrayOffset() method
            int offset = buffer.arrayOffset();

            // print the array
            System.out.println("arrayOffset is : "
                               + offset);
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("buffer is backed by "
                               + "an array but is read-only");
            System.out.println("Exception throws: " + e);
        }
    }
}
```

T5】输出:

```
buffer is backed by an array but is read-only
Exception throws: java.nio.ReadOnlyBufferException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/buffer . html # arrayOffset–](https://docs.oracle.com/javase/9/docs/api/java/nio/Buffer.html#arrayOffset--)