# Java 中的 CharBuffer compact()方法

> 原文:[https://www . geesforgeks . org/char buffer-compact-method-in-Java/](https://www.geeksforgeeks.org/charbuffer-compact-method-in-java/)

**java.nio.CharBuffer** 类的 **compact()** 方法用于压缩给定的缓冲区。

缓冲区的当前位置与其限制之间的值被复制到缓冲区的开头。然后，缓冲器的位置被设置为 n+1，其极限被设置为其容量。缓冲区的位置被设置为复制的浮点数。

**语法:**

```java
public abstract CharBuffer compact()
```

**返回值:**该方法返回与该缓冲区内容相同的**新 CharBuffer** 。

**异常:**如果这个缓冲区是只读的，这个方法抛出**readonlybufferrexception**。

下面的程序说明了**紧凑()**的方法:

**例 1:**

```java
// Java program to demonstrate
// compact() method
import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the CharBuffer
        int capacity = 10;

        // Creating the CharBuffer

        // creating object of Intbuffer
        // and allocating size capacity
        CharBuffer ic = CharBuffer.allocate(capacity);

        // putting the value in Intbuffer
        ic.put('a');
        ic.put('b');
        ic.put('c');

        // print the CharBuffer
        System.out.println("Original CharBuffer: "
                           + Arrays.toString(ic.array()));

        System.out.println("Position: " + ic.position());

        System.out.println("limit: " + ic.limit());

        // Creating a compacted CharBuffer of same CharBuffer
        // using compact() method
        CharBuffer CharBuffer = ic.compact();

        // print the CharBuffer
        System.out.println("\nCompacted CharBuffer: "
                           + Arrays.toString(CharBuffer.array()));

        System.out.println("Position: " + CharBuffer.position());

        System.out.println("limit: " + CharBuffer.limit());

        // putting the value in compacted Intbuffer
        CharBuffer.put('g');

        // print the CharBuffer
        System.out.println("\nUpdated Compacted CharBuffer: "
                           + Arrays.toString(CharBuffer.array()));
        System.out.println("Position: " + CharBuffer.position());
        System.out.println("limit: " + CharBuffer.limit());
    }
}
```

**Output:**

```java
Original CharBuffer: [a, b, c, , , , , , , ]
Position: 3
limit: 10

Compacted CharBuffer: [, , , , , , , , , ]
Position: 7
limit: 10

Updated Compacted CharBuffer: [, , , , , , , g, , ]
Position: 8
limit: 10

```

**例 2:**

```java
// Java program to demonstrate
// compact() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the CharBuffer
        int capacity = 10;

        // Creating the CharBuffer
        try {

            // creating object of CharBuffer
            // and allocating size capacity
            CharBuffer cb = CharBuffer.allocate(capacity);

            // putting the value in CharBuffer
            cb.put('a');
            cb.put('b');
            cb.put('b');
            cb.rewind();

            // Creating a read-only copy of CharBuffer
            // using asReadOnlyBuffer() method
            CharBuffer cb1 = cb.asReadOnlyBuffer();

            // print the ReadOnlyBuffer
            System.out.print("ReadOnlyBuffer CharBuffer: ");
            while (cb1.hasRemaining())
                System.out.print(cb1.get() + ", ");
            System.out.println("");

            // print the Position of CharBuffer cb
            System.out.println("\nPosition: " + cb.position());

            // print the Limit of CharBuffer cb
            System.out.println("\nlimit: " + cb.limit());

            // Creating a compacted CharBuffer of same ReadOnlyBuffer
            // using compact() method
            System.out.println("\nTrying to compact the ReadOnlyBuffer cb1");
            CharBuffer CharBuffer = cb1.compact();
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
ReadOnlyBuffer CharBuffer: a, b, b, , , , , , , , 

Position: 0

limit: 10

Trying to compact the ReadOnlyBuffer cb1
Exception throws java.nio.ReadOnlyBufferException

```