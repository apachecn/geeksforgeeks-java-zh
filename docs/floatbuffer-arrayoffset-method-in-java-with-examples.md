# Java 中的 FloatBuffer arrayOffset()方法示例

> 原文:[https://www . geeksforgeeks . org/float buffer-arrayoffset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/floatbuffer-arrayoffset-method-in-java-with-examples/)

**java.nio.FloatBuffer** 类的 **arrayOffset()** 方法用于返回缓冲区第一个元素在缓冲区后备数组中的偏移量。这意味着如果这个缓冲区由一个数组支持，那么缓冲区位置 p 对应于数组索引 p + arrayOffset()。

为了检查这个缓冲区是否有后备数组，可以使用 **hasArray()** 方法。它确保这个缓冲区有一个可访问的后备数组。

**语法:**

```java
public final int arrayOffset()
```

**返回值:**该方法返回该缓冲区数组中缓冲区第一个元素的**偏移量**。

**异常:**如果此缓冲区由数组支持但为只读，则此方法将引发**readonlybufferrexception**

下面的程序说明了 **arrayOffset()** 方法。

**实施例 1:**

```java
// Java program to demonstrate
// arrayOffset() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the FloatBuffer
        int capacity = 10;

        // Creating the FloatBuffer
        try {

            // creating object of floatbuffer
            // and allocating size capacity
            FloatBuffer fb = FloatBuffer.allocate(capacity);

            // putting the value in floatbuffer
            fb.put(8.56F);
            fb.put(2, 9.61F);

            // print the FloatBuffer
            System.out.println("FloatBuffer: "
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

```java
FloatBuffer: [8.56, 0.0, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
arrayOffset: 0

```

**示例 2:** 演示 ReadOnlyBufferException

```java
// Java program to demonstrate
// arrayOffset() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the FloatBuffer
        int capacity = 10;

        // Creating the FloatBuffer
        try {

            // creating object of floatbuffer
            // and allocating size capacity
            FloatBuffer fb = FloatBuffer.allocate(capacity);

            // putting the value in floatbuffer
            fb.put(8.56F);
            fb.put(2, 9.61F);
            fb.rewind();

            // Creating a read-only copy of FloatBuffer
            // using asReadOnlyBuffer() method
            FloatBuffer fb1 = fb.asReadOnlyBuffer();

            // print the FloatBuffer
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

```java
Read only buffer : 8.56, 0.0, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 

Try to print the array offset of read only buffer
Exception throws: java.nio.ReadOnlyBufferException

```