# 用示例缓冲 Java 中的 isReadOnly()方法

> 原文:[https://www . geesforgeks . org/buffer-is readonly-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/buffer-isreadonly-methods-in-java-with-examples/)

**[java.nio.Buffer](https://www.geeksforgeeks.org/tag/java-bytebuffer/)** 类的 **isReadOnly()** 方法用来判断这个缓冲区是否是只读的。

**语法:**

```
public abstract boolean isReadOnly()
```

**返回:**当且仅当该缓冲区为只读时，该方法将返回**真**。

以下是说明 **isReadOnly()** 方法的示例:

**示例 1:**

```
// Java program to demonstrate
// isReadOnly() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 10;

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
        boolean isReadOnly = buffer.isReadOnly();

        // checking if else condition
        if (isReadOnly)
            System.out.println("buffer is"
                               + " ReadOnly buffer");
        else
            System.out.println("buffer is not"
                               + " ReadOnly buffer");
    }
}
```

**输出:**

```
buffer is not ReadOnly buffer

```

**示例 2:**

```
// Java program to demonstrate
// isReadOnly() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 10;

        // creating object of bytebuffer
        // and allocating size capacity
        ByteBuffer bb = ByteBuffer.allocate(capacity);

        // putting the value in bytebuffer
        bb.put((byte)10);
        bb.put((byte)20);
        bb.rewind();

        // Creating a read-only copy of ByteBuffer
        // using asReadOnlyBuffer() method
        ByteBuffer bb1 = bb.asReadOnlyBuffer();

        // Typecast read-only ByteBuffer to read-only buffer
        Buffer buffer = (Buffer)bb1;

        // checking buffer is backed by array or not
        boolean isReadOnly = buffer.isReadOnly();

        // checking if else condition
        if (isReadOnly)
            System.out.println("buffer is"
                               + " ReadOnly buffer");
        else
            System.out.println("buffer is not"
                               + " ReadOnly buffer");
    }
}
```

**输出:**

```
buffer is ReadOnly buffer

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/buffer . html # isReadOnly–](https://docs.oracle.com/javase/9/docs/api/java/nio/Buffer.html#isReadOnly--)