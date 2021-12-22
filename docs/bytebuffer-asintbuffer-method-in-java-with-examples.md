# 字节缓冲区作为 Java 中的 Buffer()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-asintbuffer-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-asintbuffer-method-in-java-with-examples/)

**java.nio.ByteBuffer** 类的**Asitbuffer()**方法用于创建该字节缓冲区作为 int 缓冲区的视图。

新缓冲区的内容将从该缓冲区的当前位置开始。对此缓冲区内容所做的更改将在新缓冲区中可见，反之亦然；两个缓冲器的位置、极限和标记值将是独立的。

新缓冲区的位置将为零，其容量和限制将是该缓冲区中剩余的字节数除以 4，其标记将是未定义的。如果且仅当该缓冲区是直接的，则新缓冲区将是直接的；如果且仅当该缓冲区是只读的，则新缓冲区将是只读的。

**语法:**

```java
public abstract IntBuffer asIntBuffer()
```

**返回值:**这个方法返回一个新的 int buffe。

以下是说明 asIntBuffer()方法的示例:

**实施例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// asIntBuffer() method
// for ByteBuffer

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity  of the ByteBuffer
        int capacity = 50;

        // Creating the ByteBuffer
        try {

            // creating object of  ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // changing  bytebuffer into
            // IntBuffer
            IntBuffer cb = bb.asIntBuffer();

            // putting the value in IntBuffer()
            cb.put(10);
            cb.put(20);
            cb.put(30);
            cb.put(30);
            cb.rewind();

            // Declaring variable c
            int c;

            // print the ByteBuffer
            System.out.print("IntBuffer : ");
            while ((c = cb.get()) != 0)
                System.out.print(c + "  ");
        }

        catch (IllegalArgumentException e) {

            System.out.println("Exception thrown : " + e);
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
IntBuffer : 10  20  30  30
```

**实施例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// asIntBuffer() method
// for ByteBuffer

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity  of the ByteBuffer
        int capacity = 50;

        // Creating the ByteBuffer
        try {

            // creating object of  ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // changing  bytebuffer into
            // IntBuffer
            IntBuffer cb = bb.asIntBuffer();

            // putting the value in charbuffer
            cb.put(10);
            cb.put(20);
            cb.put(30);
            cb.rewind();

            // Declaring variable c
            int c;

            // print the ByteBuffer
            System.out.print("IntBuffer : ");
            while ((c = cb.get()) != 0)
                System.out.print(c + "  ");

            // Creating a read-only copy of ByteBuffer
            // using asReadOnlyBuffer() method
            ByteBuffer bb1 = bb.asReadOnlyBuffer();

            // changing read-only bytebuffer into
            // read-only IntBuffer
            IntBuffer cb1 = bb1.asIntBuffer();

            // putting the value in read-only IntBuffer
            System.out.println("\n\nTrying to put the value "
                               + "in read only IntBuffer");
            cb1.put(10);
            cb1.put(20);
            cb1.put(30);
            cb1.rewind();
        }

        catch (IllegalArgumentException e) {

            System.out.println("Exception thrown : " + e);
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
IntBuffer : 10  20  30  

Trying to put the value in read only IntBuffer
Exception thrown : java.nio.ReadOnlyBufferException
```