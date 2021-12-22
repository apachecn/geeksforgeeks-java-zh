# Java 中的 IntBuffer compact()方法

> 原文:[https://www . geesforgeks . org/int buffer-compact-method-in-Java/](https://www.geeksforgeeks.org/intbuffer-compact-method-in-java/)

**java.nio.IntBuffer** 类的 **compact()** 方法用于压缩给定的缓冲区。

缓冲区的当前位置与其限制之间的值被复制到缓冲区的开头。然后，缓冲器的位置被设置为 n+1，其极限被设置为其容量。缓冲区的位置被设置为复制的浮点数。

**语法:**

```java
public abstract IntBuffer compact()
```

**返回值:**该方法返回与该缓冲区内容相同的**新的 IntBuffer** 。

**异常:**如果这个缓冲区是只读的，这个方法抛出**readonlybufferrexception**。

下面的程序说明了**紧凑()**的方法:

**实施例 1:**

```java
// Java program to demonstrate
// compact() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the IntBuffer
        int capacity = 10;

        // Creating the IntBuffer

        // creating object of Intbuffer
        // and allocating size capacity
        IntBuffer ib = IntBuffer.allocate(capacity);

        // putting the value in Intbuffer
        ib.put(8);
        ib.put(9);
        ib.put(9);

        // print the IntBuffer
        System.out.println("Original IntBuffer: "
                           + Arrays.toString(ib.array()));

        System.out.println("Position: " + ib.position());

        System.out.println("limit: " + ib.limit());

        // Creating a compacted  IntBuffer of same IntBuffer
        // using compact() method
        IntBuffer IntBuffer = ib.compact();

        // print the IntBuffer
        System.out.println("\nCompacted IntBuffer: "
                           + Arrays.toString(IntBuffer.array()));

        System.out.println("Position: " + IntBuffer.position());

        System.out.println("limit: " + IntBuffer.limit());

        // putting the value in compacted Intbuffer
        IntBuffer.put(9);

        // print the IntBuffer
        System.out.println("\nUpdated Compacted IntBuffer: "
                           + Arrays.toString(IntBuffer.array()));
        System.out.println("Position: " + IntBuffer.position());
        System.out.println("limit: " + IntBuffer.limit());
    }
}
```

**Output:**

```java
Original IntBuffer: [8, 9, 9, 0, 0, 0, 0, 0, 0, 0]
Position: 3
limit: 10

Compacted IntBuffer: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
Position: 7
limit: 10

Updated Compacted IntBuffer: [0, 0, 0, 0, 0, 0, 0, 9, 0, 0]
Position: 8
limit: 10

```

**示例 2:** 演示 ReadOnlyBufferException

```java
// Java program to demonstrate
// compact() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the IntBuffer
        int capacity = 10;

        // Creating the IntBuffer
        try {

            // creating object of IntBuffer
            // and allocating size capacity
            IntBuffer ib = IntBuffer.allocate(capacity);

            // putting the value in Intbuffer
            ib.put(8);
            ib.put(9);
            ib.put(9);
            ib.rewind();

            // Creating a read-only copy of IntBuffer
            // using asReadOnlyBuffer() method
            IntBuffer ib1 = ib.asReadOnlyBuffer();

            // print the ReadOnlyBuffer
            System.out.print("ReadOnlyBuffer IntBuffer: ");

            while (ib1.hasRemaining())
                System.out.print(ib1.get() + ", ");
            System.out.println("");

            // print the Position of IntBuffer ib
            System.out.println("\nPosition: " + ib.position());

            // print the Limit of IntBuffer ib
            System.out.println("\nlimit: " + ib.limit());

            // Creating a compacted  IntBuffer of same ReadOnlyBuffer
            // using compact() method
            System.out.println("\nTrying to compact the ReadOnlyBuffer ib1");

            IntBuffer IntBuffer = ib1.compact();
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

```java
ReadOnlyBuffer IntBuffer: 8, 9, 9, 0, 0, 0, 0, 0, 0, 0, 

Position: 0

limit: 10

Trying to compact the ReadOnlyBuffer ib1
Exception throws java.nio.ReadOnlyBufferException

```