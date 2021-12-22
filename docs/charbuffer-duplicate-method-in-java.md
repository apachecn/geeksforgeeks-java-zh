# Java 中的 CharBuffer 重复()方法

> 原文:[https://www . geesforgeks . org/char buffer-replicate-in-method-Java/](https://www.geeksforgeeks.org/charbuffer-duplicate-method-in-java/)

**java.nio.CharBuffer** 类的**replicate()**方法用于创建共享给定缓冲区内容的新的 **char buffer** 。

新缓冲区的内容将是该缓冲区的内容。对此缓冲区内容的更改将在新缓冲区中可见，反之亦然；两个缓冲器的位置、极限和标记值将是独立的。

新缓冲区的容量、限制、位置和标记值将与该缓冲区相同。如果且仅当该缓冲区是直接的，则新缓冲区将是直接的；如果且仅当该缓冲区是只读的，则新缓冲区将是只读的。

**语法:**

```
public abstract CharBuffer duplicate()
```

**返回值:**该方法返回**新的 char 缓冲区**，其携带**以前的 char 缓冲区**内容

以下是说明**复制()**方法的示例:

**实施例 1:** 使用直接 charbuffer

```
// Java program to demonstrate
// duplicate() method
// Using direct intbuffer

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the CharBuffer
        int capacity = 10;

        // Creating the CharBuffer
        try {

            // creating object of Intbuffer
            // and allocating size capacity
            CharBuffer cb1 = CharBuffer.allocate(capacity);

            // putting the value in Intbuffer
            cb1.put('a');
            cb1.put(2, 'b');
            cb1.rewind();

            // print the Original CharBuffer
            System.out.println("Original CharBuffer: "
                               + Arrays.toString(cb1.array()));

            // Creating a duplicate copy of CharBuffer
            // using duplicate() method
            CharBuffer cb2 = cb1.duplicate();

            // print the duplicate copy of CharBuffer
            System.out.print("Duplicate CharBuffer: "
                             + Arrays.toString(cb2.array()));
        }

        catch (IllegalArgumentException e) {

            System.out.println("IllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("ReadOnlyBufferException catched");
        }
    }
}
```

**Output:**

```
Original CharBuffer: [a, , b, , , , , , , ]
Duplicate CharBuffer: [a, , b, , , , , , , ]

```

**示例 2:** 使用只读 intbuffer

```
// Java program to demonstrate
// duplicate() method
// using read-onlyIntbuffer

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the CharBuffer
        int capacity = 10;

        // Creating the CharBuffer
        try {

            // creating object of Intbuffer
            // and allocating size capacity
            CharBuffer cb1 = CharBuffer.allocate(capacity);

            // putting the value in Intbuffer
            cb1.put('a');
            cb1.put(2, 'b');
            cb1.rewind();

            // print the Original CharBuffer
            System.out.println("Original CharBuffer: "
                               + Arrays.toString(cb1.array()));

            // Creating a read-only copy of CharBuffer
            // using asReadOnlyBuffer() method
            CharBuffer readonly = cb1.asReadOnlyBuffer();

            // print the read-only copy of CharBuffer
            System.out.print("read-only CharBuffer: ");
            while (readonly.hasRemaining())
                System.out.print(readonly.get() + ", ");
            System.out.println("");

            // Rewinding the readonly CharBuffer
            readonly.rewind();

            // Creating a duplicate copy of CharBuffer
            // using duplicate() method
            CharBuffer cb2 = readonly.duplicate();

            // print the duplicate copy of CharBuffer
            System.out.print("duplicate copy of read-only CharBuffer: ");

            while (cb2.hasRemaining())
                System.out.print(cb2.get() + ", ");
            System.out.println("");
        }

        catch (IllegalArgumentException e) {

            System.out.println("IllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("ReadOnlyBufferException catched");
        }
    }
}
```

**Output:**

```
Original CharBuffer: [a, , b, , , , , , , ]
read-only CharBuffer: a, , b, , , , , , , , 
duplicate copy of read-only CharBuffer: a, , b, , , , , , , , 

```