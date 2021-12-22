# Java 中 ByteBuffer asReadOnlyBuffer()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-as readonly buffer-in-Java-method-with-examples/](https://www.geeksforgeeks.org/bytebuffer-asreadonlybuffer-method-in-java-with-examples/)

**java.nio.ByteBuffer** 类的 **asReadOnlyBuffer()** 方法用于创建一个共享该缓冲区内容的新的只读字节缓冲区。

新缓冲区的内容将是该缓冲区的内容。对此缓冲区内容的更改将在新缓冲区中可见；但是，新的缓冲区本身将是只读的，不允许修改共享内容。两个缓冲器的位置、极限和标记值将是独立的。

新缓冲区的容量、限制、位置和标记值将与该缓冲区相同。

如果此缓冲区本身是只读的，则此方法的行为方式与复制方法完全相同。

**语法:**

```
public abstract ByteBuffer asReadOnlyBuffer()
```

**返回值:**该方法返回新的只读字节缓冲区，其内容与该缓冲区的内容相同。

以下是举例说明*作为 ReadOnlyBuffer()* 方法的例子:

**实施例 1:**

```
// Java program to demonstrate
// asReadOnlyBuffer() method

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

            // putting the int to byte typecast value in ByteBuffer
            bb.put((byte)20);
            bb.put((byte)30);
            bb.put((byte)40);
            bb.put((byte)50);
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer:  "
                               + Arrays.toString(bb.array()));

            // Creating a read-only copy of ByteBuffer
            // using asReadOnlyBuffer() method
            ByteBuffer bb1 = bb.asReadOnlyBuffer();

            // print the ByteBuffer
            System.out.print("\nReadOnlyBuffer ByteBuffer: ");

            while (bb1.hasRemaining())
                System.out.print(bb1.get() + ", ");
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
Original ByteBuffer:  [20, 30, 40, 50]

ReadOnlyBuffer ByteBuffer: 20, 30, 40, 50,

```

**实施例 2:**

```
// Java program to demonstrate
// asReadOnlyBuffer() method

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

            // putting the int to byte typecast value in ByteBuffer
            bb.put((byte)20);
            bb.put((byte)30);
            bb.put((byte)40);
            bb.put((byte)50);
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer:  "
                               + Arrays.toString(bb.array()));

            // Creating a read-only copy of ByteBuffer
            // using asReadOnlyBuffer() method
            ByteBuffer bb1 = bb.asReadOnlyBuffer();

            // print the ByteBuffer
            System.out.print("\nReadOnlyBuffer ByteBuffer: ");

            while (bb1.hasRemaining())
                System.out.print(bb1.get() + ", ");

            // try to change read only bytebuffer
            System.out.println("\n\nTrying to get the array"
                               + " from bb1 for editing");

            byte[] bbarr = bb1.array();
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
Original ByteBuffer:  [20, 30, 40, 50]

ReadOnlyBuffer ByteBuffer: 20, 30, 40, 50, 

Trying to get the array from bb1 for editing
Exception thrown : java.nio.ReadOnlyBufferException

```