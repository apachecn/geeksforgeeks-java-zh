# Java 中的 LongBuffer compact()方法

> 原文:[https://www . geesforgeks . org/longbuffer-compact-in-method-Java/](https://www.geeksforgeeks.org/longbuffer-compact-method-in-java/)

**java.nio.LongBuffer** 类的 **compact()** 方法用于压缩给定的缓冲区。

缓冲区的当前位置与其限制之间的值被复制到缓冲区的开头。然后，缓冲器的位置被设置为 n+1，其极限被设置为其容量。缓冲区的位置被设置为复制的浮点数。

**语法:**

```
public abstract LongBuffer compact()
```

**返回值:**该方法返回与该缓冲区内容相同的**新龙虎符**。

**异常:**如果这个缓冲区是只读的，这个方法抛出**readonlybufferrexception**。

下面的程序说明了**紧凑()**的方法:

**实施例 1:**

```
// Java program to demonstrate
// compact() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the LongBuffer
        int capacity = 10;

        // Creating the LongBuffer

        // creating object of Longbuffer
        // and allocating size capacity
        LongBuffer ib = LongBuffer.allocate(capacity);

        // putting the value in Longbuffer
        ib.put(8);
        ib.put(9);
        ib.put(9);

        // prLong the LongBuffer
        System.out.println("Original LongBuffer: "
                           + Arrays.toString(ib.array()));

        System.out.println("Position: " + ib.position());

        System.out.println("limit: " + ib.limit());

        // Creating a compacted  LongBuffer of same LongBuffer
        // using compact() method
        LongBuffer LongBuffer = ib.compact();

        // prLong the LongBuffer
        System.out.println("\nCompacted LongBuffer: "
                           + Arrays.toString(LongBuffer.array()));

        System.out.println("Position: " + LongBuffer.position());

        System.out.println("limit: " + LongBuffer.limit());

        // putting the value in compacted Longbuffer
        LongBuffer.put(9);

        // prLong the LongBuffer
        System.out.println("\nUpdated Compacted LongBuffer: "
                           + Arrays.toString(LongBuffer.array()));
        System.out.println("Position: " + LongBuffer.position());
        System.out.println("limit: " + LongBuffer.limit());
    }
}
```

**Output:**

```
Original LongBuffer: [8, 9, 9, 0, 0, 0, 0, 0, 0, 0]
Position: 3
limit: 10

Compacted LongBuffer: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
Position: 7
limit: 10

Updated Compacted LongBuffer: [0, 0, 0, 0, 0, 0, 0, 9, 0, 0]
Position: 8
limit: 10

```

**实施例 2:**

```
// Java program to demonstrate
// compact() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the LongBuffer
        int capacity = 10;

        // Creating the LongBuffer
        try {

            // creating object of LongBuffer
            // and allocating size capacity
            LongBuffer ib = LongBuffer.allocate(capacity);

            // putting the value in Longbuffer
            ib.put(8);
            ib.put(9);
            ib.put(9);
            ib.rewind();

            // Creating a read-only copy of LongBuffer
            // using asReadOnlyBuffer() method
            LongBuffer ib1 = ib.asReadOnlyBuffer();

            // prLong the ReadOnlyBuffer
            System.out.print("ReadOnlyBuffer LongBuffer: ");
            while (ib1.hasRemaining())
                System.out.print(ib1.get() + ", ");
            System.out.println("");

            // prLong the Position of LongBuffer ib
            System.out.println("\nPosition: " + ib.position());

            // prLong the Limit of LongBuffer ib
            System.out.println("\nlimit: " + ib.limit());

            // Creating a compacted  LongBuffer of same ReadOnlyBuffer
            // using compact() method
            System.out.println("\nTrying to compact the ReadOnlyBuffer ib1");
            LongBuffer LongBuffer = ib1.compact();
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception throws " + e);
        }

        catch (ReadOnlyBufferException e) {
            System.out.println("Exception throws " + e);
        }
    }
}
```

**Output:**

```
ReadOnlyBuffer LongBuffer: 8, 9, 9, 0, 0, 0, 0, 0, 0, 0, 

Position: 0

limit: 10

Trying to compact the ReadOnlyBuffer ib1
Exception throws java.nio.ReadOnlyBufferException

```