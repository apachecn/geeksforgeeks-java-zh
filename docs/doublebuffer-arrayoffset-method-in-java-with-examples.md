# Java 中的 DoubleBuffer arrayOffset()方法示例

> 原文:[https://www . geesforgeks . org/double buffer-arrayoffset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doublebuffer-arrayoffset-method-in-java-with-examples/)

**java.nio.DoubleBuffer** 类的 **arrayOffset()** 方法用于返回缓冲区第一个元素在缓冲区后备数组中的偏移量。这意味着如果这个缓冲区由一个数组支持，那么缓冲区位置 p 对应于数组索引 p + arrayOffset()。

为了检查这个缓冲区是否有后备数组，可以使用 hasArray()方法。它确保这个缓冲区有一个可访问的后备数组。

**语法:**

```
public final int arrayOffset()
```

**返回值:**该方法返回该缓冲区数组中缓冲区第一个元素的**偏移量**。

**异常:**如果此缓冲区由数组支持但为只读，则此方法将引发**readonlybufferrexception**

下面的程序说明了 arrayOffset()方法。

**实施例 1:**

```
// Java program to demonstrate
// arrayOffset() method

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
            DoubleBuffer fb = DoubleBuffer.allocate(capacity);

            // putting the value in Doublebuffer
            fb.put(8.56F);
            fb.put(2, 9.61F);

            // print the DoubleBuffer
            System.out.println("DoubleBuffer: "
                               + Arrays.toString(fb.array()));

            // print the arrayOffset
            System.out.println("arrayOffset: "
                               + fb.arrayOffset());
        }

        catch (IllegalArgumentException e) {
            System.out.println("IllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {
            System.out.println("Exception throws" + e);
        }
    }
}
```

**Output:**

```
DoubleBuffer: [8.5600004196167, 0.0, 9.609999656677246, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
arrayOffset: 0

```

**示例 2:** 演示 ReadOnlyBufferException

```
// Java program to demonstrate
// arrayOffset() method

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
            DoubleBuffer fb = DoubleBuffer.allocate(capacity);

            // putting the value in Doublebuffer
            fb.put(8.56F);
            fb.put(2, 9.61F);
            fb.rewind();

            // Creating a read-only copy of DoubleBuffer
            // using asReadOnlyBuffer() method
            DoubleBuffer fb1 = fb.asReadOnlyBuffer();

            // print the DoubleBuffer
            System.out.print("Read only buffer : ");
            while (fb1.hasRemaining())
                System.out.print(fb1.get() + ", ");

            // next line
            System.out.println("");

            // print the arrayOffset
            System.out.println("\nTry to print the array offset"
                               + " of read only buffer");
            System.out.println("arrayOffset: " + fb1.arrayOffset());
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception throws: " + e);
        }

        catch (ReadOnlyBufferException e) {
            System.out.println("Exception throws: " + e);
        }
    }
}
```

**Output:**

```
Read only buffer : 8.5600004196167, 0.0, 9.609999656677246, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 

Try to print the array offset of read only buffer
Exception throws: java.nio.ReadOnlyBufferException

```