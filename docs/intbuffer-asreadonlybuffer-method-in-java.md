# Java 中的 IntBuffer asReadOnlyBuffer()方法

> 原文:[https://www . geesforgeks . org/int buffer-as readonly buffer-in-method-in-Java/](https://www.geeksforgeeks.org/intbuffer-asreadonlybuffer-method-in-java/)

**java.nio.IntBuffer 类**的 **asReadOnlyBuffer()** 方法用于用该缓冲区的内容创建一个新的**只读 int buffer** 。新缓冲区是该缓冲区的副本。因此，对此缓冲区内容所做的更改将在新缓冲区中可见。

由于新缓冲区是只读的，因此不允许对其内容进行任何修改。两个缓冲器的位置、极限和标记值将是独立的。新缓冲区的容量、限制、位置和标记值将与该缓冲区相同。如果此缓冲区本身是只读的，则此方法的行为方式与复制方法完全相同。

**语法:**

```java
public abstract IntBuffer asReadOnlyBuffer()
```

**返回值:**该方法返回**新的只读 int 缓冲区**，其内容与该缓冲区相同。

下面是说明 asReadOnlyBuffer()方法的示例:

**实施例 1:**

```java
// Java program to demonstrate
// asReadOnlyBuffer() method

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
            ib.put(8);
            ib.put(2, 9);
            ib.rewind();

            // print the IntBuffer
            System.out.println("Original IntBuffer:  "
                               + Arrays.toString(ib.array()));

            // Creating a read-only copy of IntBuffer
            // using asReadOnlyBuffer() method
            IntBuffer IntBuffer = ib.asReadOnlyBuffer();

            // print the IntBuffer
            System.out.print("\nReadOnlyBuffer IntBuffer: ");

            while (IntBuffer.hasRemaining())
                System.out.print(IntBuffer.get() + ", ");
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
Original IntBuffer:  [8, 0, 9, 0, 0, 0, 0, 0, 0, 0]

ReadOnlyBuffer IntBuffer: 8, 0, 9, 0, 0, 0, 0, 0, 0, 0,

```

**实施例 2:**

```java
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

        // Creating the IntBuffer
        try {

            // creating object of Intbuffer ib
            // and allocating size capacity
            IntBuffer ib = IntBuffer.allocate(capacity1);

            // putting the value in ib
            ib.put(8);
            ib.put(2, 9);
            ib.rewind();

            // print the IntBuffer
            System.out.println("IntBuffer ib: "
                               + Arrays.toString(ib.array()));

            // ib1
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
IntBuffer ib: [8, 0, 9, 0, 0, 0, 0, 0, 0, 0]

IntBuffer ib1:  [0, 4, 6, 0, 0]

ReadOnlyBuffer IntBuffer: 8, 0, 9, 0, 0, 0, 0, 0, 0, 0, 

Trying to get the array from ReadOnlyib for editing
Exception thrown: java.nio.ReadOnlyBufferException

```