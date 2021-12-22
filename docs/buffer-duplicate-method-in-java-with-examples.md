# 用示例缓冲 Java 中的重复()方法

> 原文:[https://www . geesforgeks . org/buffer-replicate-method-in-Java-with-examples/](https://www.geeksforgeeks.org/buffer-duplicate-method-in-java-with-examples/)

**[java.nio.Buffer](https://www.geeksforgeeks.org/tag/java-buffer/)** 类的**replicate()**方法用于创建共享该缓冲区内容的新缓冲区。新缓冲区的内容将是该缓冲区的内容。对此缓冲区内容的更改将在新缓冲区中可见，反之亦然；两个缓冲器的位置、极限和标记值将是独立的。新缓冲器的容量、极限、位置和标记值将与该缓冲器相同。如果且仅当该缓冲区是直接的，则新缓冲区将是直接的；如果且仅当该缓冲区是只读的，则新缓冲区将是只读的。

**语法:**

```java
public abstract Buffer duplicate()
```

**返回值:**该方法返回携带先前缓冲区内容的新缓冲区。

以下是说明*复制()*方法的示例:

**示例 1:** 使用直接字节缓冲

```java
// Java program to demonstrate
// duplicate() method

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
            ByteBuffer bb1
                = ByteBuffer.allocate(capacity);

            // putting the int to byte typecast
            // value in ByteBuffer
            bb1.put((byte)20);
            bb1.put((byte)30);
            bb1.put((byte)40);
            bb1.put((byte)50);
            bb1.rewind();

            // print the Original ByteBuffer
            System.out.println("Original ByteBuffer:  "
                               + Arrays.toString(bb1.array()));

            // Creating a duplicate copy of ByteBuffer
            // using duplicate() method
            ByteBuffer bb2 = bb1.duplicate();

            // print the duplicate copy of ByteBuffer
            System.out.print("\nDuplicate ByteBuffer: "
                             + Arrays.toString(bb2.array()));
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

T5】输出:

```java
Original ByteBuffer:  [20, 30, 40, 50]

Duplicate ByteBuffer: [20, 30, 40, 50]

```

**示例 2:** 使用只读字节缓冲

```java
// Java program to demonstrate
// duplicate() method

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
            ByteBuffer bb1
                = ByteBuffer.allocate(capacity);

            // putting the int to byte typecast
            // value in ByteBuffer
            bb1.put((byte)20);
            bb1.put((byte)30);
            bb1.put((byte)40);
            bb1.put((byte)50);
            bb1.rewind();

            // print the Original ByteBuffer
            System.out.println("Original ByteBuffer:  "
                               + Arrays.toString(bb1.array()));

            // Creating a read-only copy of ByteBuffer
            // using asReadOnlyBuffer() method
            ByteBuffer readonly = bb1.asReadOnlyBuffer();

            // print the read-only copy of ByteBuffer
            System.out.print("\nRead-only ByteBuffer:  ");
            while (readonly.hasRemaining())
                System.out.print(readonly.get() + ", ");
            System.out.println("");

            // Rewinding the readonly ByteBuffer
            readonly.rewind();

            // Creating a duplicate copy of ByteBuffer
            // using duplicate() method
            ByteBuffer bb2 = readonly.duplicate();

            // print the duplicate copy of ByteBuffer
            System.out.print("\nDuplicate copy of "
                             + "read-only ByteBuffer:  ");

            while (bb2.hasRemaining())
                System.out.print(bb2.get() + ", ");
            System.out.println("");
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

**输出:**

```java
Original ByteBuffer:  [20, 30, 40, 50]

Read-only ByteBuffer:  20, 30, 40, 50, 

Duplicate copy of read-only ByteBuffer:  20, 30, 40, 50,

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/buffer . html #重复–](https://docs.oracle.com/javase/9/docs/api/java/nio/Buffer.html#duplicate--)