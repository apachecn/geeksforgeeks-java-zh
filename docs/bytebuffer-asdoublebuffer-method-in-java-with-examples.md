# Java 中的 ByteBuffer asDoubleBuffer()方法，带示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-as double buffer-in-Java-method-with-examples/](https://www.geeksforgeeks.org/bytebuffer-asdoublebuffer-method-in-java-with-examples/)

**java.nio.ByteBuffer** 类的 **asDoubleBuffer()** 方法用于创建该字节缓冲区作为双缓冲区的视图。
新缓冲区的内容将从该缓冲区的当前位置开始。对此缓冲区内容所做的更改将在新缓冲区中可见，反之亦然；两个缓冲器的位置、极限和标记值将是独立的。

新缓冲区的位置将为零，其容量和限制将是该缓冲区中剩余的字节数除以 8，其标记将是未定义的。如果且仅当该缓冲区是直接的，则新缓冲区将是直接的；如果且仅当该缓冲区是只读的，则新缓冲区将是只读的。

**语法:**

```
public abstract DoubleBuffer asDoubleBuffer()
```

**返回值:**这个方法返回一个新的双缓冲区。

以下是说明 asDoubleBuffer()方法的示例:

**实施例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// asDoubleBuffer() method
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
            // DoubleBuffer
            DoubleBuffer cb = bb.asDoubleBuffer();

            // putting the value in DoubleBuffer
            cb.put(5001.99);
            cb.put(5002.99);
            cb.put(5003.99);
            cb.rewind();

            // Declaring variable c
            double c;

            // print the ByteBuffer
            System.out.print("DoubleBuffer : ");
            while ((c = cb.get()) != 0)
                System.out.print(c + " ");
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

```
DoubleBuffer : 5001.99 5002.99 5003.99
```

**实施例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// asDoubleBuffer() method
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
            // DoubleBuffer
            DoubleBuffer cb = bb.asDoubleBuffer();

            // putting the value in DoubleBuffer
            cb.put(5001.99);
            cb.put(5002.99);
            cb.put(5003.99);
            cb.rewind();

            // Declaring variable c
            double c;

            // print the ByteBuffer
            System.out.print("DoubleBuffer : ");
            while ((c = cb.get()) != 0)
                System.out.print(c + " ");

            // Creating a read-only copy of ByteBuffer
            // using asReadOnlyBuffer() method
            ByteBuffer bb1 = bb.asReadOnlyBuffer();

            // changing read-only bytebuffer into
            // read-only DoubleBuffer
            DoubleBuffer cb1 = bb1.asDoubleBuffer();

            // putting the value in read-only double buffer
            System.out.println("\n\nTrying to put the value "
                               + "in read only double buffer");
            cb1.put(5001.99);
            cb1.put(5002.99);
            cb1.put(5003.99);
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

```
DoubleBuffer : 5001.99 5002.99 5003.99 

Trying to put the value in read only double buffer
Exception thrown : java.nio.ReadOnlyBufferException
```