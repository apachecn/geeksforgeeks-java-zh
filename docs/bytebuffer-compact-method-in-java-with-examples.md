# Java 中的 ByteBuffer compact()方法，带示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-compact-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-compact-method-in-java-with-examples/)

**java.nio.ByteBuffer** 类的 **compact()** 方法用于压缩给定的缓冲区。
缓冲区当前位置与其限制之间的字节(如果有)被复制到缓冲区的开头。也就是说，索引 p =位置()的字节被复制到索引 0，索引 p + 1 的字节被复制到索引 1，以此类推，直到索引限制()–1 的字节被复制到索引 n =限制()–1–p。然后，缓冲区的位置被设置为 n+1，其限制被设置为其容量。如果定义了标记，则会将其丢弃。
缓冲区的位置被设置为复制的字节数，而不是零，这样调用该方法后可以立即调用另一个相对 put 方法。
从缓冲区写入数据后调用此方法，以防写入不完整。
**语法:**

```
public abstract ByteBuffer compact()
```

**返回值:**该方法返回与该缓冲区内容相同的新字节缓冲区。
**异常:**如果这个缓冲区是只读的，这个方法抛出 ReadOnlyBufferException。
以下程序说明了紧凑()方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// compact() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 7;

        // Creating the ByteBuffer

        // creating object of ByteBuffer
        // and allocating size capacity
        ByteBuffer bb = ByteBuffer.allocate(capacity);

        // putting the int to byte typecast value in ByteBuffer
        bb.put((byte)20);
        bb.put((byte)30);
        bb.put((byte)40);

        // print the ByteBuffer
        System.out.println("Original ByteBuffer: "
                           + Arrays.toString(bb.array()));

        System.out.println("Position: " + bb.position());

        System.out.println("limit: " + bb.limit());

        // Creating a compacted  ByteBuffer of same ByteBuffer
        // using compact() method
        ByteBuffer cbb = bb.compact();

        // print the ByteBuffer
        System.out.println("\nCompacted ByteBuffer: "
                           + Arrays.toString(cbb.array()));

        System.out.println("Position: " + cbb.position());

        System.out.println("limit: " + cbb.limit());

        // putting the int to byte typecast value in compacted ByteBuffer
        cbb.put((byte)50);

        // print the ByteBuffer
        System.out.println("\nUpdated Compacted ByteBuffer: "
                           + Arrays.toString(cbb.array()));
        System.out.println("Position: " + cbb.position());
        System.out.println("limit: " + cbb.limit());
    }
}
```

**Output:** 

```
Original ByteBuffer: [20, 30, 40, 0, 0, 0, 0]
Position: 3
limit: 7

Compacted ByteBuffer: [0, 0, 0, 0, 0, 0, 0]
Position: 4
limit: 7

Updated Compacted ByteBuffer: [0, 0, 0, 0, 50, 0, 0]
Position: 5
limit: 7
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// compact() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 5;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the int to byte typecast value in ByteBuffer
            bb.put((byte)20);
            bb.put((byte)30);
            bb.put((byte)40);
            bb.rewind();

            // Creating a read-only copy of ByteBuffer
            // using asReadOnlyBuffer() method
            ByteBuffer bb1 = bb.asReadOnlyBuffer();

            // print the ReadOnlyBuffer
            System.out.print("ReadOnlyBuffer ByteBuffer: ");
            while (bb1.hasRemaining())
                System.out.print(bb1.get() + ", ");
            System.out.println("");

            // print the Position of ByteBuffer bb
            System.out.println("\nPosition: " + bb.position());

            // print the Limit of ByteBuffer bb
            System.out.println("\nlimit: " + bb.limit());

            // Creating a compacted  ByteBuffer of same ReadOnlyBuffer
            // using compact() method
            System.out.println("\nTrying to compact the ReadOnlyBuffer bb1");
            ByteBuffer rbb = bb1.compact();
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
ReadOnlyBuffer ByteBuffer: 20, 30, 40, 0, 0, 

Position: 0

limit: 5

Trying to compact the ReadOnlyBuffer bb1
Exception throws java.nio.ReadOnlyBufferException
```