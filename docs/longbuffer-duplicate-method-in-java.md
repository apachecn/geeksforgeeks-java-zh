# Java 中的 LongBuffer 重复()方法

> 原文:[https://www . geesforgeks . org/longbuffer-replicate-in-method-Java/](https://www.geeksforgeeks.org/longbuffer-duplicate-method-in-java/)

**java.nio.LongBuffer** 类的**replicate()**方法用于创建共享给定缓冲区内容的新的**长缓冲区**。

**语法:**

```java
public abstract LongBuffer duplicate()
```

**返回值:**该方法返回携带前一个长缓冲区内容的**新长缓冲区**

以下是说明**复制()**方法的示例:

**实施例 1:** 使用直接长臂

```java
// Java program to demonstrate
// duplicate() method
// Using direct Longbuffer

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
            LongBuffer ib1 = LongBuffer.allocate(capacity);

            // putting the value in Longbuffer
            ib1.put(8);
            ib1.put(2, 9);
            ib1.rewind();

            // prLong the Original LongBuffer
            System.out.println("Original LongBuffer: "
                               + Arrays.toString(ib1.array()));

            // Creating a duplicate copy of LongBuffer
            // using duplicate() method
            LongBuffer ib2 = ib1.duplicate();

            // prLong the duplicate copy of LongBuffer
            System.out.println("Duplicate LongBuffer: "
                               + Arrays.toString(ib2.array()));
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

```java
Original LongBuffer: [8, 0, 9, 0, 0, 0, 0, 0, 0, 0]
Duplicate LongBuffer: [8, 0, 9, 0, 0, 0, 0, 0, 0, 0]

```

**示例 2:** 使用只读 Longbuffer

```java
// Java program to demonstrate
// duplicate() method
// using read-onlyLongbuffer

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
            LongBuffer ib1 = LongBuffer.allocate(capacity);

            // putting the value in Longbuffer
            ib1.put(8);
            ib1.put(2, 9);
            ib1.rewind();

            // prLong the Original LongBuffer
            System.out.println("Original LongBuffer:  "
                               + Arrays.toString(ib1.array()));

            // Creating a read-only copy of LongBuffer
            // using asReadOnlyBuffer() method
            LongBuffer readonly = ib1.asReadOnlyBuffer();

            // prLong the read-only copy of LongBuffer
            System.out.print("read-only LongBuffer:  ");
            while (readonly.hasRemaining())
                System.out.print(readonly.get() + ", ");
            System.out.println("");

            // Rewinding the readonly LongBuffer
            readonly.rewind();

            // Creating a duplicate copy of LongBuffer
            // using duplicate() method
            LongBuffer ib2 = readonly.duplicate();

            // prLong the duplicate copy of LongBuffer
            System.out.print("duplicate copy of read-only LongBuffer:  ");

            while (ib2.hasRemaining())
                System.out.print(ib2.get() + ", ");
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

```java
Original LongBuffer:  [8, 0, 9, 0, 0, 0, 0, 0, 0, 0]
read-only LongBuffer:  8, 0, 9, 0, 0, 0, 0, 0, 0, 0, 
duplicate copy of read-only LongBuffer:  8, 0, 9, 0, 0, 0, 0, 0, 0, 0,

```