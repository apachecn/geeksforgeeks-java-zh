# 用示例缓冲 Java 中的 hasArray()方法

> 原文:[https://www . geesforgeks . org/buffer-hasarray-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/buffer-hasarray-methods-in-java-with-examples/)

**[java.nio.Buffer](https://www.geeksforgeeks.org/tag/java-bytebuffer/)** 类的 **hasArray()** 方法用于判断该缓冲区是否由可访问数组支持。如果此方法返回 true，则可以安全地调用数组和 arrayOffset()方法。

**语法:**

```
public abstract boolean hasArray()
```

**返回:**如果且仅当该缓冲区由数组支持且不是只读的，则该方法将返回**真**。否则返回**假**。

以下是说明 **hasArray()** 方法的例子:

**示例 1:** 当缓冲区由数组

```
// Java program to demonstrate
// hasArray() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 10;

        // Creating the ByteBuffer
        try {

            // creating object of bytebuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the value in bytebuffer
            bb.put((byte)10);
            bb.put((byte)20);
            bb.rewind();

            // Typecast bytebuffer to Buffer
            Buffer buffer = (Buffer)bb;

            // checking buffer is backed by array or not
            boolean isArray = buffer.hasArray();

            // checking if else condition
            if (isArray)
                System.out.println("buffer is"
                                   + " backed by array");
            else
                System.out.println("buffer is"
                                   + " not backed by any array");
        }

        catch (IllegalArgumentException e) {
            System.out.println("IllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {
            System.out.println("ReadOnlyBufferException catched");
        }
    }
}
```

**支持时，输出:**

```
buffer is backed by array

```

**示例 2:** 当缓冲区没有数组支持时

```
// Java program to demonstrate
// hasArray() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 10;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the value in ByteBuffer
            bb.put((byte)8.56F);
            bb.put((byte)10);
            bb.rewind();

            // Creating a read-only copy of ByteBuffer
            // using asReadOnlyBuffer() method
            ByteBuffer bb1 = bb.asReadOnlyBuffer();

            // Typecast read-only ByteBuffer to read-only buffer
            Buffer buffer = (Buffer)bb1;

            // checking Buffer buffer is backed by array or not
            boolean isArray = buffer.hasArray();

            // checking if else condition
            if (isArray)
                System.out.println("buffer is"
                                   + " backed by array");
            else
                System.out.println("buffer is"
                                   + " not backed by any array");
        }

        catch (IllegalArgumentException e) {
            System.out.println("IllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {
            System.out.println("ReadOnlyBufferException catched");
        }
    }
}
```

**输出:**

```
buffer is not backed by any array

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/buffer . html # hasArray–](https://docs.oracle.com/javase/9/docs/api/java/nio/Buffer.html#hasArray--)