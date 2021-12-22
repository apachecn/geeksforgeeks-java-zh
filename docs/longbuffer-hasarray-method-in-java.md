# Java 中的 LongBuffer hasArray()方法

> 原文:[https://www . geesforgeks . org/longbuffer-hasarray-method-in-Java/](https://www.geeksforgeeks.org/longbuffer-hasarray-method-in-java/)

类的**数组()**方法用于返回支持该缓冲区的长数组。对此缓冲区内容的修改将导致返回数组的内容被修改，反之亦然。Invoke()在调用此方法之前使用 hasArray()方法，以确保此缓冲区具有可访问的后备数组

**语法:**

```java
public final Long[] array()
```

**返回值:**该方法返回支持该缓冲区的**数组**。

**抛出:**这个方法抛出**readonlybufferenexception**(如果这个缓冲区由数组支持，但是是只读的)

下面程序说明了**数组()**的方法:

**实施例 1:**

```java
// Java program to demonstrate
// array() method

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
            ib.put(7);
            ib.put(2, 6);
            ib.rewind();

            // getting array from ib LongBuffer using array() method
            long[] ibb = ib.array();

            // prLonging the LongBuffer ib
            System.out.println("LongBuffer:  "
                               + Arrays.toString(ibb));
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

**实施例 2:**

```java
// Java program to demonstrate
// array() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the ib
        int capacity1 = 10;

        // Declaring the capacity of the ib1
        int capacity2 = 5;

        // Creating the LongBuffer
        try {
            //
            // ib
            //
            // creating object of Longbuffer ib
            // and allocating size capacity
            LongBuffer ib = LongBuffer.allocate(capacity1);

            // putting the value in ib
            ib.put(7);
            ib.put(2, 6);
            ib.put(3, 7);
            ib.rewind();

            // prLong the LongBuffer
            System.out.println("LongBuffer ib: "
                               + Arrays.toString(ib.array()));

            //
            // ib1
            //
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

            long[] ibarr = readOnlyib.array();
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