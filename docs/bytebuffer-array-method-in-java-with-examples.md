# Java 中的 ByteBuffer 数组()方法，带示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-array-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-array-method-in-java-with-examples/)

**java.nio.ByteBuffer** 类的**数组()**方法用于返回支持所取缓冲区的字节数组。
修改此缓冲区的内容将导致返回数组的内容被修改，反之亦然。
在调用此方法之前调用 hasArray()方法，以确保此缓冲区具有可访问的后备数组。

**语法:**

```
public final byte[] array()
```

**返回值:**这个方法返回支持这个缓冲区的数组。
**异常:**如果该缓冲区由数组支持但为只读，则该方法抛出*readonlybufferection*。

下面是说明 array()方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// array() method

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

            // print the ByteBuffer
            System.out.println("ByteBuffer:  "
                               + Arrays.toString(bb.array()));

            // getting byte array from ByteBuffer
            // using array() method
            byte[] arr = bb.array();

            // print the byte array
            System.out.println("\nbyte array: " +
                                    Arrays.toString(arr));
        }

        catch (IllegalArgumentException e) {

            System.out.println("Exception throws: " + e);
        }
    }
}
```

**Output:** 

```
ByteBuffer:  [20, 30, 40, 50]

byte array: [20, 30, 40, 50]
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// array() method

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

            // putting the int to byte typecast value
            // in ByteBuffer
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
            bb1.rewind();

            // print the ByteBuffer
            System.out.print("\nReadOnlyBuffer ByteBuffer : ");

            while (bb1.hasRemaining())
                System.out.print(bb1.get() + ", ");

            // getting byte array from read-only
            // ByteBuffer using array() method
            System.out.println("\n\nTrying to get the array"
                               + " from bb1 for editing");
            byte[] arr = bb1.array();
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
Original ByteBuffer:  [20, 30, 40, 50]

ReadOnlyBuffer ByteBuffer : 20, 30, 40, 50, 

Trying to get the array from bb1 for editing
Exception throws: java.nio.ReadOnlyBufferException
```