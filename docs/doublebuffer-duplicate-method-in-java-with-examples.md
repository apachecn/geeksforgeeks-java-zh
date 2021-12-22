# Java 中的 DoubleBuffer 重复()方法，示例

> 原文:[https://www . geesforgeks . org/double buffer-用示例复制 java 中的方法/](https://www.geeksforgeeks.org/doublebuffer-duplicate-method-in-java-with-examples/)

**java.nio.DoubleBuffer** 类的**replicate()**方法用于创建共享给定缓冲区内容的新浮动缓冲区。

新缓冲区的内容将是该缓冲区的内容。对此缓冲区内容的更改将在新缓冲区中可见，反之亦然；两个缓冲器的位置、极限和标记值将是独立的。

新缓冲区的容量、限制、位置和标记值将与该缓冲区相同。如果且仅当该缓冲区是直接的，则新缓冲区将是直接的；如果且仅当该缓冲区是只读的，则新缓冲区将是只读的。

**语法:**

```
public abstract DoubleBuffer duplicate()
```

**返回值:**这个方法返回**新的双缓冲区**，它携带了之前的双缓冲区内容

下面是说明 duplicate()方法的示例:

**程序 1:**

```
// Java program to demonstrate
// duplicate() method
// Using direct Doublebuffer

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the DoubleBuffer
        int capacity = 10;

        // Creating the DoubleBuffer
        try {

            // creating object of Doublebuffer
            // and allocating size capacity
            DoubleBuffer db1 = DoubleBuffer.allocate(capacity);

            // putting the value in Doublebuffer
            db1.put(8.56F);
            db1.put(2, 9.61F);
            db1.rewind();

            // print the Original DoubleBuffer
            System.out.println("Original DoubleBuffer:  "
                               + Arrays.toString(db1.array()));

            // Creating a duplicate copy of DoubleBuffer
            // using duplicate() method
            DoubleBuffer db2 = db1.duplicate();

            // print the duplicate copy of DoubleBuffer
            System.out.print("\nDuplicate DoubleBuffer: "
                             + Arrays.toString(db2.array()));
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
Original DoubleBuffer:  [8.5600004196167, 0.0, 9.609999656677246, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]

Duplicate DoubleBuffer: [8.5600004196167, 0.0, 9.609999656677246, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]

```

**例 2:**

```
// Java program to demonstrate
// duplicate() method
// using read-onlyDoublebuffer

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the DoubleBuffer
        int capacity = 10;

        // Creating the DoubleBuffer
        try {

            // creating object of Doublebuffer
            // and allocating size capacity
            DoubleBuffer db1 = DoubleBuffer.allocate(capacity);

            // putting the value in Doublebuffer
            db1.put(8.56F);
            db1.put(2, 9.61F);
            db1.rewind();

            // print the Original DoubleBuffer
            System.out.println("Original DoubleBuffer:  "
                               + Arrays.toString(db1.array()));

            // Creating a read-only copy of DoubleBuffer
            // using asReadOnlyBuffer() method
            DoubleBuffer readonly = db1.asReadOnlyBuffer();

            // print the read-only copy of DoubleBuffer
            System.out.print("\nread-only DoubleBuffer:  ");
            while (readonly.hasRemaining())
                System.out.print(readonly.get() + ", ");
            System.out.println("");

            // Rewinding the readonly DoubleBuffer
            readonly.rewind();

            // Creating a duplicate copy of DoubleBuffer
            // using duplicate() method
            DoubleBuffer db2 = readonly.duplicate();

            // print the duplicate copy of DoubleBuffer
            System.out.print("\nduplicate copy of read-only DoubleBuffer:  ");

            while (db2.hasRemaining())
                System.out.print(db2.get() + ", ");
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
Original DoubleBuffer:  [8.5600004196167, 0.0, 9.609999656677246, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]

read-only DoubleBuffer:  8.5600004196167, 0.0, 9.609999656677246, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 

duplicate copy of read-only DoubleBuffer:  8.5600004196167, 0.0, 9.609999656677246, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0,

```