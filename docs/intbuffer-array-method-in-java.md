# Java 中的 IntBuffer 数组()方法

> 原文:[https://www . geesforgeks . org/int buffer-array-method-in-Java/](https://www.geeksforgeeks.org/intbuffer-array-method-in-java/)

**java.nio.IntBuffer** 类的**数组()**方法用于返回支持该缓冲区的 int 数组。对此缓冲区内容的修改将导致返回数组的内容被修改，反之亦然。Invoke()在调用此方法之前使用 hasArray()方法，以确保此缓冲区具有可访问的后备数组

**语法:**

```java
public final int[] array()
```

**返回值:**该方法返回支持该缓冲区的**数组**。

**异常:**该方法抛出**readonlybufferenexception**(如果该缓冲区由数组支持但为只读)

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

        // Declaring the capacity of the IntBuffer
        int capacity = 10;

        // Creating the IntBuffer
        try {

            // creating object of Intbuffer
            // and allocating size capacity
            IntBuffer ib = IntBuffer.allocate(capacity);

            // putting the value in Intbuffer
            ib.put(7);
            ib.put(2, 6);
            ib.rewind();

            // getting array from ib IntBuffer using array() method
            int[] ibb = ib.array();

            // printing the IntBuffer ib
            System.out.println("IntBuffer:  "
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

**Output:**

```java
IntBuffer:  [7, 0, 6, 0, 0, 0, 0, 0, 0, 0]

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

        // Creating the IntBuffer
        try {
            //
            // ib
            //
            // creating object of Intbuffer ib
            // and allocating size capacity
            IntBuffer ib = IntBuffer.allocate(capacity1);

            // putting the value in ib
            ib.put(7);
            ib.put(2, 6);
            ib.put(3, 7);
            ib.rewind();

            // print the IntBuffer
            System.out.println("IntBuffer ib: "
                               + Arrays.toString(ib.array()));

            //
            // ib1
            //
            // creating object of Intbuffer ib1
            // and allocating size capacity
            IntBuffer ib1 = IntBuffer.allocate(capacity2);

            // putting the value in ib1
            ib1.put(1, 4);
            ib1.put(2, 6);
            ib1.rewind();

            // print the IntBuffer
            System.out.println("\nIntBuffer ib1:  "
                               + Arrays.toString(ib1.array()));

            // Creating a read-only copy of IntBuffer
            // using asReadOnlyBuffer() method
            IntBuffer readOnlyib = ib.asReadOnlyBuffer();

            // print the IntBuffer
            System.out.print("\nReadOnlyBuffer IntBuffer: ");

            while (readOnlyib.hasRemaining())
                System.out.print(readOnlyib.get() + ", ");

            // try to change readOnlyib
            System.out.println("\n\nTrying to get the array"
                               + " from ReadOnlyib for editing");

            int[] ibarr = readOnlyib.array();
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

```java
IntBuffer ib: [7, 0, 6, 7, 0, 0, 0, 0, 0, 0]

IntBuffer ib1:  [0, 4, 6, 0, 0]

ReadOnlyBuffer IntBuffer: 7, 0, 6, 7, 0, 0, 0, 0, 0, 0, 

Trying to get the array from ReadOnlyib for editing
Exception thrown: java.nio.ReadOnlyBufferException

```