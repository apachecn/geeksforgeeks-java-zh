# 字节缓冲区有一个 Java 中的 Array()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-hasarray-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-hasarray-method-in-java-with-examples/)

**[Java . nio . bytebuffer](https://www.geeksforgeeks.org/tag/java-bytebuffer/)**类的 **hasArray()** 方法用于确保给定的缓冲区是否由可访问的字节数组支持。如果该缓冲区有可访问的后备数组，则返回 true，否则返回 false。如果此方法返回 true，则可以安全地调用 array()和 arrayOffset()方法，因为它们在支持数组上工作。

**语法:**

```java
public final boolean hasArray()
```

**返回:**如果且仅当该缓冲区由数组支持且不是只读的，则该方法将返回**真**。否则返回**假**。

以下是说明 **hasArray()** 方法的例子:

**示例 1:** 当缓冲区由数组

```java
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

            // checking FloatBuffer fb is backed by array or not
            boolean isArray = bb.hasArray();

            // checking if else condition
            if (isArray)
                System.out.println("ByteBuffer bb is"
                                   + " backed by array");
            else
                System.out.println("ByteBuffer bb is"
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

```java
ByteBuffer bb is backed by array

```

**示例 2:** 当缓冲区由数组

```java
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

            // checking ByteBuffer bb is backed by array or not
            boolean isArray = bb1.hasArray();

            // checking if else condition
            if (isArray)
                System.out.println("ByteBuffer bb is"
                                   + " backed by array");
            else
                System.out.println("ByteBuffer bb is"
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

```java
ByteBuffer bb is not backed by any array

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # hasArray–](https://docs.oracle.com/javase/9/docs/api/java/nio/ByteBuffer.html#hasArray--)