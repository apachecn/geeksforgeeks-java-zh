# Java 中的 FloatBuffer compact()方法示例

> 原文:[https://www . geesforgeks . org/float buffer-compact-in-Java-method-with-examples/](https://www.geeksforgeeks.org/floatbuffer-compact-method-in-java-with-examples/)

**java.nio.FloatBuffer** 类的 **compact()** 方法用于压缩给定的缓冲区。

缓冲区的当前位置与其限制之间的值被复制到缓冲区的开头。然后，缓冲器的位置被设置为 n+1，其极限被设置为其容量。缓冲区的位置被设置为复制的浮点数。

**语法:**

```
public abstract FloatBuffer compact()
```

**返回值:**该方法返回与该缓冲区内容相同的**新浮动缓冲区**。

**异常:**如果这个缓冲区是只读的，这个方法抛出**readonlybufferrexception**。

下面的程序说明了**紧凑()**的方法:

**实施例 1:**

```
// Java program to demonstrate
// compact() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the FloatBuffer
        int capacity = 10;

        // Creating the FloatBuffer

        // creating object of floatbuffer
        // and allocating size capacity
        FloatBuffer fb = FloatBuffer.allocate(capacity);

        // putting the value in floatbuffer
        fb.put(8.56F);
        fb.put(9.61F);
        fb.put(9.61F);

        // print the FloatBuffer
        System.out.println("Original FloatBuffer: "
                           + Arrays.toString(fb.array()));

        System.out.println("Position: " + fb.position());

        System.out.println("limit: " + fb.limit());

        // Creating a compacted  FloatBuffer of same FloatBuffer
        // using compact() method
        FloatBuffer floatBuffer = fb.compact();

        // print the FloatBuffer
        System.out.println("\nCompacted FloatBuffer: "
                           + Arrays.toString(floatBuffer.array()));

        System.out.println("Position: " + floatBuffer.position());

        System.out.println("limit: " + floatBuffer.limit());

        // putting the value in compacted floatbuffer
        floatBuffer.put(9.61F);

        // print the FloatBuffer
        System.out.println("\nUpdated Compacted FloatBuffer: "
                           + Arrays.toString(floatBuffer.array()));
        System.out.println("Position: " + floatBuffer.position());
        System.out.println("limit: " + floatBuffer.limit());
    }
}
```

**Output:**

```
Original FloatBuffer: [8.56, 9.61, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
Position: 3
limit: 10

Compacted FloatBuffer: [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
Position: 7
limit: 10

Updated Compacted FloatBuffer: [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 9.61, 0.0, 0.0]
Position: 8
limit: 10

```

**实施例 2:**

```
// Java program to demonstrate
// compact() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the FloatBuffer
        int capacity = 10;

        // Creating the FloatBuffer
        try {

            // creating object of FloatBuffer
            // and allocating size capacity
            FloatBuffer fb = FloatBuffer.allocate(capacity);

            // putting the value in floatbuffer
            fb.put(8.56F);
            fb.put(9.61F);
            fb.put(9.61F);
            fb.rewind();

            // Creating a read-only copy of FloatBuffer
            // using asReadOnlyBuffer() method
            FloatBuffer fb1 = fb.asReadOnlyBuffer();

            // print the ReadOnlyBuffer
            System.out.print("ReadOnlyBuffer FloatBuffer: ");
            while (fb1.hasRemaining())
                System.out.print(fb1.get() + ", ");
            System.out.println("");

            // print the Position of FloatBuffer fb
            System.out.println("\nPosition: " + fb.position());

            // print the Limit of FloatBuffer fb
            System.out.println("\nlimit: " + fb.limit());

            // Creating a compacted  FloatBuffer of same ReadOnlyBuffer
            // using compact() method
            System.out.println("\nTrying to compact the ReadOnlyBuffer fb1");
            FloatBuffer floatBuffer = fb1.compact();
        }

        catch (IllegalArgumentException e) {

            System.out.println("Exception throws " + e);
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("Exception throws " + e);
        }
    }
}
```

**Output:**

```
ReadOnlyBuffer FloatBuffer: 8.56, 9.61, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 

Position: 0

limit: 10

Trying to compact the ReadOnlyBuffer fb1
Exception throws java.nio.ReadOnlyBufferException

```