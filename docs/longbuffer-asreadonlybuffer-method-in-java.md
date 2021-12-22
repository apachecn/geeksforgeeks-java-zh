# Java 中的 LongBuffer asReadOnlyBuffer()方法

> 原文:[https://www . geesforgeks . org/longbuffer-as readonly buffer-in-method-in-Java/](https://www.geeksforgeeks.org/longbuffer-asreadonlybuffer-method-in-java/)

使用 java.nio.LongBuffer 类的 **asReadOnlyBuffer()** 方法，用该缓冲区的内容创建一个新的只读长缓冲区。新缓冲区是该缓冲区的副本。因此，对此缓冲区内容所做的更改将在新缓冲区中可见。

由于新缓冲区是只读的，因此不允许对其内容进行任何修改。两个缓冲器的位置、极限和标记值将是独立的。新缓冲区的容量、限制、位置和标记值将与该缓冲区相同。如果此缓冲区本身是只读的，则此方法的行为方式与复制方法完全相同。

**语法:**

```
public abstract LongBuffer asReadOnlyBuffer()
```

**返回值:**该方法返回新的只读长缓冲区，其内容与该缓冲区相同。

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

            // prLong the LongBuffer
            System.out.println("Original LongBuffer:  "
                               + Arrays.toString(ib.array()));

            // Creating a read-only copy of LongBuffer
            // using asReadOnlyBuffer() method
            LongBuffer LongBuffer = ib.asReadOnlyBuffer();

            // prLong the LongBuffer
            System.out.print("\nReadOnlyBuffer LongBuffer: ");

            while (LongBuffer.hasRemaining())
                System.out.print(LongBuffer.get() + ", ");
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
Original LongBuffer:  [8, 0, 9, 0, 0, 0, 0, 0, 0, 0]

ReadOnlyBuffer LongBuffer: 8, 0, 9, 0, 0, 0, 0, 0, 0, 0,

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

        // Declaring the capacity of the ib
        int capacity1 = 10;

        // Declaring the capacity of the ib1
        int capacity2 = 5;

        // Creating the LongBuffer
        try {
            // creating object of Longbuffer ib
            // and allocating size capacity
            LongBuffer ib = LongBuffer.allocate(capacity1);

            // putting the value in ib
            ib.put(8);
            ib.put(2, 9);
            ib.rewind();

            // prLong the LongBuffer
            System.out.println("LongBuffer ib: "
                               + Arrays.toString(ib.array()));

            // ib1
            // creating object of Longbuffer ib1
            // and allocating size capacity
            LongBuffer ib1 = LongBuffer.allocate(capacity2);

            // putting the value in ib1
            ib1.put(1, 4);
            ib1.put(2, 6);
            ib1.rewind();

            // prLong the LongBuffer
            System.out.println("\nLongBuffer ib1:  "
                               + Arrays.toString(ib1.array()));

            // Creating a read-only copy of LongBuffer
            // using asReadOnlyBuffer() method
            LongBuffer readOnlyib = ib.asReadOnlyBuffer();

            // prLong the LongBuffer
            System.out.print("\nReadOnlyBuffer LongBuffer: ");

            while (readOnlyib.hasRemaining())
                System.out.print(readOnlyib.get() + ", ");

            // try to change readOnlyib
            System.out.println("\n\nTrying to get the array"
                               + " from ReadOnlyib for editing");
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
LongBuffer ib: [8, 0, 9, 0, 0, 0, 0, 0, 0, 0]

LongBuffer ib1:  [0, 4, 6, 0, 0]

ReadOnlyBuffer LongBuffer: 8, 0, 9, 0, 0, 0, 0, 0, 0, 0, 

Trying to get the array from ReadOnlyib for editing

```