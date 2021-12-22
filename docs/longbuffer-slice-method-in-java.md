# Java 中的 LongBuffer slice()方法

> 原文:[https://www . geesforgeks . org/longbuffer-slice-method-in-Java/](https://www.geeksforgeeks.org/longbuffer-slice-method-in-java/)

类的 **slice()** 方法用于创建一个新的长缓冲区，其内容是给定缓冲区内容的共享子序列。

新缓冲区的内容将从该缓冲区的当前位置开始。对此缓冲区内容的更改将在新缓冲区中可见，反之亦然。两个缓冲器的位置、极限和标记值将是独立的。

新缓冲区的位置将为零，其容量和限制将是该缓冲区中剩余的 Longegers 的数量，并且其标记将是未定义的。如果且仅当该缓冲区是直接的，则新缓冲区将是直接的；如果且仅当该缓冲区是只读的，则新缓冲区将是只读的。

**语法:**

```
public abstract LongBuffer slice()
```

**返回值:**该方法返回*新的 Long 缓冲区。*

下面是说明 slice()方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// slice() method

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
            ib1.put(9);

            // prLong the LongBuffer
            System.out.println("Original LongBuffer: "
                               + Arrays.toString(ib1.array()));

            // prLong the LongBuffer position
            System.out.println("position: " + ib1.position());

            // prLong the LongBuffer capacity
            System.out.println("capacity: " + ib1.capacity());

            // Creating a shared subsequence buffer of given LongBuffer
            // using slice() method
            LongBuffer ib2 = ib1.slice();

            // prLong the shared subsequence buffer
            System.out.println("shared subsequence LongBuffer: "
                               + Arrays.toString(ib2.array()));

            // prLong the LongBuffer position
            System.out.println("position: " + ib2.position());

            // prLong the LongBuffer capacity
            System.out.println("capacity: " + ib2.capacity());
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

**Output**

```
Original LongBuffer: [8, 9, 0, 0, 0, 0, 0, 0, 0, 0]
position: 2
capacity: 10
shared subsequence LongBuffer: [8, 9, 0, 0, 0, 0, 0, 0, 0, 0]
position: 0
capacity: 8
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// slice() method

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

            // putting the value in floatbuffer
            ib1.put(8);
            ib1.put(9);
            ib1.put(5);
            ib1.put(3);

            // prLong the LongBuffer
            System.out.println("Original LongBuffer: "
                               + Arrays.toString(ib1.array()));

            // prLong the LongBuffer position
            System.out.println("position: " + ib1.position());

            // prLong the LongBuffer capacity
            System.out.println("capacity: " + ib1.capacity());

            // Creating a shared subsequence buffer of given LongBuffer
            // using slice() method
            LongBuffer ib2 = ib1.slice();
            ib2.put(2);
            ib2.put(6);

            // prLong the shared subsequence buffer
            System.out.println("shared subsequence LongBuffer: "
                               + Arrays.toString(ib2.array()));

            // prLong the LongBuffer position
            System.out.println("position: " + ib2.position());

            // prLong the LongBuffer capacity
            System.out.println("capacity: " + ib2.capacity());
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

**Output**

```
Original LongBuffer: [8, 9, 5, 3, 0, 0, 0, 0, 0, 0]
position: 4
capacity: 10
shared subsequence LongBuffer: [8, 9, 5, 3, 2, 6, 0, 0, 0, 0]
position: 2
capacity: 6
```