# Java 中的 CharBuffer arrayOffset()方法

> 原文:[https://www . geesforgeks . org/char buffer-arrayoffset-method-in-Java/](https://www.geeksforgeeks.org/charbuffer-arrayoffset-method-in-java/)

**java.nio.CharBuffer** 类的 **arrayOffset()** 方法用于返回缓冲区第一个元素在缓冲区后备数组中的偏移量。这意味着如果这个缓冲区由一个数组支持，那么缓冲区位置 p 对应于数组索引 p + arrayOffset()。

为了检查这个缓冲区是否有后备数组，可以使用 **hasArray()** 方法。它确保这个缓冲区有一个可访问的后备数组。

**语法:**

```
public final int arrayOffset()
```

**返回值:**该方法返回该缓冲区数组中缓冲区第一个元素的**偏移量**。

**异常:**如果此缓冲区由数组支持但为只读，则此方法将引发**readonlybufferrexception**

下面的程序说明了 **arrayOffset()** 方法。

**例 1:**

```
// Java program to demonstrate
// arrayOffset() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the CharBuffer
        int capacity = 10;

        // Creating the CharBuffer
        try {

            // creating object of CharBuffer
            // and allocating size capacity
            CharBuffer cb = CharBuffer.allocate(capacity);

            // putting the value in CharBuffer
            cb.put('a');
            cb.put(2, 'b');

            // print the CharBuffer
            System.out.println("CharBuffer: "
                               + Arrays.toString(cb.array()));

            // print the arrayOffset
            System.out.println("arrayOffset: "
                               + cb.arrayOffset());
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

**输出:**

```
CharBuffer: [a, , b, , , , , , , ]
arrayOffset: 0

```

**示例 2:** 演示 readonly buffer exception

```
// Java program to demonstrate
// arrayOffset() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the CharBuffer
        int capacity = 10;

        // Creating the CharBuffer
        try {

            // creating object of CharBuffer
            // and allocating size capacity
            CharBuffer fb = CharBuffer.allocate(capacity);

            // putting the value in CharBuffer
            fb.put('a');
            fb.put(2, 'b');
            fb.rewind();

            // Creating a read-only copy of CharBuffer
            // using asReadOnlyBuffer() method
            CharBuffer cb1 = fb.asReadOnlyBuffer();

            // print the CharBuffer
            System.out.print("Read only buffer : ");
            while (cb1.hasRemaining())
                System.out.print(cb1.get() + ", ");

            // next line
            System.out.println("");

            // print the arrayOffset
            System.out.println("\nTry to print the array offset"
                               + " of read only buffer");
            System.out.println("arrayOffset: " + cb1.arrayOffset());
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

**输出:**

```
Read only buffer : a, , b, , , , , , , , 

Try to print the array offset of read only buffer
Exception throws: java.nio.ReadOnlyBufferException

```