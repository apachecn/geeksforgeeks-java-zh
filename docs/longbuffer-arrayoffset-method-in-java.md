# Java 中的 LongBuffer arrayOffset()方法

> 原文:[https://www . geesforgeks . org/longbuffer-arrayoffset-method-in-Java/](https://www.geeksforgeeks.org/longbuffer-arrayoffset-method-in-java/)

**java.nio.LongBuffer** 类的 **arrayOffset()** 方法用于返回缓冲区第一个元素在缓冲区后备数组中的偏移量。这意味着如果这个缓冲区由一个数组支持，那么缓冲区位置 p 对应于数组索引 p + arrayOffset()。

为了检查这个缓冲区是否有后备数组，可以使用 *hasArray()* 方法。它确保这个缓冲区有一个可访问的后备数组。

**语法:**

```java
public final Long arrayOffset()
```

**返回值:**该方法返回该缓冲区数组中缓冲区第一个元素的*偏移量*。

**异常:**如果此缓冲区由数组支持但为只读，则此方法将引发*readonlybufferrexception*

下面的程序说明了 *arrayOffset()* 方法。

**程序 1:**

```java
// Java program to demonstrate
// arrayOffset() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the LongBuffer
        int capacity = 10;

        // Creating the LongBuffer
        try {

            // creating object of Longbuffer
            // and allocating size capacity
            LongBuffer ib = LongBuffer.allocate(capacity);

            // putting the value in Longbuffer
            ib.put(8);
            ib.put(2, 9);

            // prLong the LongBuffer
            System.out.println("LongBuffer: "
                               + Arrays.toString(ib.array()));

            // prLong the arrayOffset
            System.out.println("arrayOffset: "
                               + ib.arrayOffset());
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

```java
LongBuffer: [8, 0, 9, 0, 0, 0, 0, 0, 0, 0]
arrayOffset: 0

```

**程序 2:** 演示 ReadOnlyBufferException。

```java
// Java program to demonstrate
// arrayOffset() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the LongBuffer
        int capacity = 10;

        // Creating the LongBuffer
        try {

            // creating object of Longbuffer
            // and allocating size capacity
            LongBuffer ib = LongBuffer.allocate(capacity);

            // putting the value in Longbuffer
            ib.put(8);
            ib.put(2, 9);
            ib.rewind();

            // Creating a read-only copy of LongBuffer
            // using asReadOnlyBuffer() method
            LongBuffer ib1 = ib.asReadOnlyBuffer();

            // prLong the LongBuffer
            System.out.print("Read only buffer : ");
            while (ib1.hasRemaining())
                System.out.print(ib1.get() + ", ");

            // next line
            System.out.println("");

            // prLong the arrayOffset
            System.out.println("\nTry to prLong the array offset"
                               + " of read only buffer");
            System.out.println("arrayOffset: " + ib1.arrayOffset());
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

```java
Read only buffer : 8, 0, 9, 0, 0, 0, 0, 0, 0, 0, 

Try to prLong the array offset of read only buffer
Exception throws: java.nio.ReadOnlyBufferException

```