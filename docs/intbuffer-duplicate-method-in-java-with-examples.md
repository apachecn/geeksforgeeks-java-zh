# Java 中的 IntBuffer 重复()方法，示例

> 原文:[https://www . geesforgeks . org/int buffer-replicate-method-in-Java-with-examples/](https://www.geeksforgeeks.org/intbuffer-duplicate-method-in-java-with-examples/)

**java.nio.IntBuffer** 类的**replicate()**方法用于创建一个新的 IntBuffer，它共享给定缓冲区的内容，在所有方面都是相同的。

**语法:**

```java
public abstract IntBuffer duplicate()
```

**返回值:**这个方法返回**新的 IntBuffer** ，它携带了之前 IntBuffer 的内容

以下是说明**复制()**方法的示例:

**示例 1:** 使用直接输入缓冲区

```java
// Java program to demonstrate duplicate() method

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
            IntBuffer ib1 = IntBuffer.allocate(capacity);

            // putting the value in Intbuffer
            ib1.put(8);
            ib1.put(2, 9);
            ib1.rewind();

            // print the Original IntBuffer
            System.out.println("Original IntBuffer:  "
                               + Arrays.toString(ib1.array()));

            // Creating a duplicate copy of IntBuffer
            // using duplicate() method
            IntBuffer ib2 = ib1.duplicate();

            // print the duplicate copy of IntBuffer
            System.out.print("Duplicate IntBuffer: "
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
Original IntBuffer:  [8, 0, 9, 0, 0, 0, 0, 0, 0, 0]
Duplicate IntBuffer: [8, 0, 9, 0, 0, 0, 0, 0, 0, 0]

```

**示例 2:** 使用只读 intbuffer

```java
// Java program to demonstrate
// duplicate() method
// using read-onlyIntbuffer

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
            IntBuffer ib1 = IntBuffer.allocate(capacity);

            // putting the value in Intbuffer
            ib1.put(8);
            ib1.put(2, 9);
            ib1.rewind();

            // print the Original IntBuffer
            System.out.println("Original IntBuffer:  "
                               + Arrays.toString(ib1.array()));

            // Creating a read-only copy of IntBuffer
            // using asReadOnlyBuffer() method
            IntBuffer readonly = ib1.asReadOnlyBuffer();

            // print the read-only copy of IntBuffer
            System.out.print("read-only IntBuffer:  ");

            while (Readonly.hasRemaining())
                System.out.print(readonly.get() + ", ");

            System.out.println("");

            // Rewinding the readonly IntBuffer
            readonly.rewind();

            // Creating a duplicate copy of IntBuffer
            // using duplicate() method
            IntBuffer ib2 = readonly.duplicate();

            // print the duplicate copy of IntBuffer
            System.out.print("Duplicate copy of read-only IntBuffer:  ");

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
Original IntBuffer:  [8, 0, 9, 0, 0, 0, 0, 0, 0, 0]
Read-only IntBuffer:  8, 0, 9, 0, 0, 0, 0, 0, 0, 0, 
Duplicate copy of read-only IntBuffer:  8, 0, 9, 0, 0, 0, 0, 0, 0, 0,

```