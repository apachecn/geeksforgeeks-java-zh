# Java 中的 ByteBuffer arrayOffset()方法，带示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-arrayoffset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-arrayoffset-method-in-java-with-examples/)

**java.nio.ByteBuffer** 类的 **arrayOffset()** 方法用于返回给定缓冲区的后备数组中缓冲区第一个元素的偏移量。

如果这个缓冲区由一个数组支持，那么缓冲区位置 p 对应于数组索引 p + arrayOffset()。

在调用此方法之前，调用 **hasArray** 方法，以确保此缓冲区具有可访问的后备数组。

**语法:**

```
public final int arrayOffset()
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

            // putting the int to byte typecast value in ByteBuffer
            bb.put((byte)20);
            bb.put((byte)30);
            bb.put((byte)40);
            bb.put((byte)50);
            bb.rewind();

            // print the ByteBuffer
            System.out.println("ByteBuffer: "
                               + Arrays.toString(bb.array()));

            // print the arrayOffset
            System.out.println("arrayOffset: "
                               + bb.arrayOffset());
        }

        catch (IllegalArgumentException e) {
            System.out.println("IllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {
            System.out.println("Exception throws" + e);
        }
    }
}
```

**Output:**

```
ByteBuffer: [20, 30, 40, 50]
arrayOffset: 0

```

**例 2:**

```
// Java program to demonstrate
// arrayOffset() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the  ByteBuffer
        int capacity = 3;

        // Creating the  ByteBuffer
        try {

            // creating object of  ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the value in  ByteBuffer
            bb.put((byte)20);
            bb.put((byte)30);
            bb.put((byte)40);
            bb.rewind();

            // Creating a read-only copy of  ByteBuffer
            // using asReadOnlyBuffer() method
            ByteBuffer bb1 = bb.asReadOnlyBuffer();

            // print the  ByteBuffer
            System.out.print("Read only buffer : ");
            while (bb1.hasRemaining())
                System.out.print(bb1.get() + ", ");

            // next line
            System.out.println("");

            // print the arrayOffset
            System.out.println("\nTry to print the array offset"
                               + " of read only buffer");
            System.out.println("arrayOffset: " + bb1.arrayOffset());
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception throws: " + e);
        }

        catch (ReadOnlyBufferException e) {
            System.out.println("Exception throws: " + e);
        }
    }
}
```

**Output:**

```
Read only buffer : 20, 30, 40, 

Try to print the array offset of read only buffer
Exception throws: java.nio.ReadOnlyBufferException

```