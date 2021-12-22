# Java 中 ByteBuffer asShortBuffer()方法示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-as short buffer-in-Java-method-with-examples/](https://www.geeksforgeeks.org/bytebuffer-asshortbuffer-method-in-java-with-examples/)

**java.nio.ByteBuffer** 类的 **asShortBuffer()** 方法用于创建该字节缓冲区作为短缓冲区的视图。
新缓冲区的内容将从该缓冲区的当前位置开始。对此缓冲区内容的更改将在新缓冲区中可见，反之亦然；两个缓冲器的位置、极限和标记值将是独立的。
新缓冲区的位置将为零，其容量和限制将是该缓冲区中剩余的字节数除以 2，其标记将是未定义的。如果且仅当该缓冲区是直接的，则新缓冲区将是直接的；如果且仅当该缓冲区是只读的，则新缓冲区将是只读的。
**语法:**

```
public abstract ShortBuffer asShortBuffer()
```

**返回值:**这个方法返回一个新的短缓冲区。
以下是举例说明 *asShortBuffer()* 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// asShortBuffer() method
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
            // ShortBuffer
            ShortBuffer cb = bb.asShortBuffer();

            // putting the value in ShortBuffer
            cb.put((short)20);
            cb.put((short)30);
            cb.put((short)40);
            cb.put((short)50);
            cb.rewind();

            // Declaring variable c
            short c;

            // print the ByteBuffer
            System.out.print("ShortBuffer : ");
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

```
ShortBuffer : 20  30  40  50
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// asShortBuffer() method
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
            // ShortBuffer
            IntBuffer cb = bb.asIntBuffer();

            // putting the int to short typecast value in ShortBuffer
            cb.put((short)10);
            cb.put((short)20);
            cb.put((short)30);
            cb.rewind();

            // Declaring variable c
            int c;

            // print the ByteBuffer
            System.out.print("ShortBuffer : ");
            while ((c = cb.get()) != 0)
                System.out.print(c + "  ");

            // Creating a read-only copy of ByteBuffer
            // using asReadOnlyBuffer() method
            ByteBuffer bb1 = bb.asReadOnlyBuffer();

            // changing read-only bytebuffer into
            // read-only ShortBuffer
            ShortBuffer cb1 = bb1.asShortBuffer();

            // putting the int to short typecast value in read-only ShortBuffer
            System.out.println("\n\nTrying to put the value "
                               + "in read only ShortBuffer");
            cb1.put((short)10);
            cb1.put((short)20);
            cb1.put((short)30);
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
ShortBuffer : 10  20  30  

Trying to put the value in read only ShortBuffer
Exception thrown : java.nio.ReadOnlyBufferException
```