# Java 中的 CharBuffer asReadOnlyBuffer()方法

> 原文:[https://www . geesforgeks . org/char buffer-as readonly buffer-in-method-in-Java/](https://www.geeksforgeeks.org/charbuffer-asreadonlybuffer-method-in-java/)

**java.nio.CharBuffer 类**的 **asReadOnlyBuffer()** 方法用于用该缓冲区的内容创建一个新的**只读字符缓冲区**。新缓冲区是该缓冲区的副本。因此，对此缓冲区内容所做的更改将在新缓冲区中可见。

由于新缓冲区是只读的，因此不允许对其内容进行任何修改。两个缓冲器的位置、极限和标记值将是独立的。新缓冲区的容量、限制、位置和标记值将与该缓冲区相同。如果此缓冲区本身是只读的，则此方法的行为方式与复制方法完全相同。

**语法:**

```
public abstract CharBuffer asReadOnlyBuffer()
```

**返回值:**该方法返回**新的只读字符缓冲区**，其内容与该缓冲区相同。

下面是说明 asReadOnlyBuffer()方法的示例:

**实施例 1:**

```
// Java program to demonstrate
// asReadOnlyBuffer() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the CharBuffer
        int capacity = 10;

        // Creating the CharBuffer
        try {

            // creating object of charbuffer
            // and allocating size capacity
            CharBuffer cb = CharBuffer.allocate(capacity);

            // putting the value in charbuffer
            cb.put('a');
            cb.put(2, 'b');
            cb.rewind();

            // print the charBuffer
            System.out.println("Original CharBuffer:  "
                               + Arrays.toString(cb.array()));

            // Creating a read-only copy of CharBuffer
            // using asReadOnlyBuffer() method
            CharBuffer charBuffer = cb.asReadOnlyBuffer();

            // print the CharBuffer
            System.out.print("\nReadOnlyBuffer CharBuffer: ");

            while (charBuffer.hasRemaining())
                System.out.print(charBuffer.get() + ", ");
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
Original CharBuffer:  [a,  , b,  ,  ,  ,  ,  ,  ,  ]

ReadOnlyBuffer CharBuffer: a,  , b,  ,  ,  ,  ,  ,  ,  ,

```

**实施例 2:**

```
// Java program to demonstrate
// asReadOnlyBuffer() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args) throws Exception
    {

        // Declaring the capacity of the cb
        int capacity1 = 10;

        // Declaring the capacity of the cb1
        int capacity2 = 5;

        // Creating the CharBuffer
        try {

            //
            // cb
            //
            // creating object of charbuffer cb
            // and allocating size capacity
            CharBuffer cb = CharBuffer.allocate(capacity1);

            // putting the value in cb
            cb.put('a');
            cb.put(2, 'b');
            cb.rewind();

            // print the CharBuffer
            System.out.println("CharBuffer cb: "
                               + Arrays.toString(cb.array()));

            //
            // cb1
            //
            // creating object of charbuffer cb1
            // and allocating size capacity
            CharBuffer cb1 = CharBuffer.allocate(capacity2);

            // putting the value in cb1
            cb1.put(1, 'c');
            cb1.put(2, 'd');
            cb1.rewind();

            // print the CharBuffer
            System.out.println("\nCharBuffer cb1: "
                               + Arrays.toString(cb1.array()));

            // Creating a read-only copy of CharBuffer
            // using asReadOnlyBuffer() method
            CharBuffer readOnlyCb = cb.asReadOnlyBuffer();

            // print the CharBuffer
            System.out.print("\nReadOnlyBuffer CharBuffer: ");

            while (readOnlyCb.hasRemaining())
                System.out.print(readOnlyCb.get() + ", ");

            // try to change readOnlyCb
            System.out.println("\n\nTrying to get the array"
                               + " from ReadOnlyCb for editing");

            char[] fbarr = readOnlyCb.array();
        }
        catch (IllegalArgumentException e) {
            System.out.println("IllegalArgumentException catched");
        }
        catch (ReadOnlyBufferException e) {
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output:**

```
CharBuffer cb: [a,  , b,  ,  ,  ,  ,  ,  ,  ]

CharBuffer cb1: [ , c, d,  ,  ]

ReadOnlyBuffer CharBuffer: a,  , b,  ,  ,  ,  ,  ,  ,  , 

Trying to get the array from ReadOnlyCb for editing
Exception thrown: java.nio.ReadOnlyBufferException

```