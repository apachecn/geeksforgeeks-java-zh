# Java 中 ByteBuffer asLongBuffer()方法示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-as long buffer-in-Java-method-with-examples/](https://www.geeksforgeeks.org/bytebuffer-aslongbuffer-method-in-java-with-examples/)

**java.nio.ByteBuffer** 类的 **asLongBuffer()** 方法用于创建该字节缓冲区作为长缓冲区的视图。
新缓冲区的内容将从该缓冲区的当前位置开始。对此缓冲区内容的更改将在新缓冲区中可见，反之亦然；两个缓冲器的位置、极限和标记值将是独立的。
新缓冲区的位置将为零，其容量和限制将是该缓冲区中剩余的字节数除以 8，其标记将是未定义的。如果且仅当该缓冲区是直接的，则新缓冲区将是直接的；如果且仅当该缓冲区是只读的，则新缓冲区将是只读的。
**语法:**

```
public abstract LongBuffer asLongBuffer()
```

**返回值:**这个方法返回一个新的长缓冲区。
以下是举例说明 *asLongBuffer()* 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// asLongBuffer() method
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
            // LongBuffer
            LongBuffer lb = bb.asLongBuffer();

            // putting the value in LongBuffer
            lb.put(1000000);
            lb.put(2000000);
            lb.put(3000000);
            lb.put(3000000);
            lb.rewind();

            // Declaring variable c
            long c;

            // print the ByteBuffer
            System.out.print("LongBuffer : ");
            while ((c = lb.get()) != 0)
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

```
LongBuffer : 1000000  2000000  3000000  3000000
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// asLongBuffer() method
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
            // LongBuffer
            LongBuffer lb = bb.asLongBuffer();

            // putting the value in LongBuffer
            lb.put(1000000);
            lb.put(2000000);
            lb.put(3000000);
            lb.rewind();

            // Declaring variable c
            long c;

            // print the ByteBuffer
            System.out.print("LongBuffer : ");
            while ((c = lb.get()) != 0)
                System.out.print(c + "  ");

            // Creating a read-only copy of ByteBuffer
            // using asReadOnlyBuffer() method
            ByteBuffer bb1 = bb.asReadOnlyBuffer();

            // changing read-only bytebuffer into
            // read-only LongBuffer
            LongBuffer lb1 = bb1.asLongBuffer();

            // putting the value in read-only LongBuffer
            System.out.println("\n\nTrying to put the value "
                               + "in read only LongBuffer");
            lb1.put(10);
            lb1.put(20);
            lb1.put(30);
            lb1.rewind();
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
LongBuffer : 1000000  2000000  3000000  

Trying to put the value in read only LongBuffer
Exception thrown : java.nio.ReadOnlyBufferException
```