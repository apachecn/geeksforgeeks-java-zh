# Java 中的字节缓冲片()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-slice-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-slice-method-in-java-with-examples/)

**java.nio.ByteBuffer** 类的 **slice()** 方法用于创建**新的字节缓冲区**，其内容是给定缓冲区内容的共享子序列。

新缓冲区的内容将从该缓冲区的当前位置开始。对此缓冲区内容的更改将在新缓冲区中可见，反之亦然。两个缓冲器的位置、极限和标记值将是独立的。

新缓冲区的位置将为零，其容量和限制将是该缓冲区中剩余的浮点数，其标记将是未定义的。如果且仅当该缓冲区是直接的，则新缓冲区将是直接的；如果且仅当该缓冲区是只读的，则新缓冲区将是只读的。

**语法:**

```
public abstract ByteBuffer slice()
```

**返回值:**该方法返回**新的字节缓冲区。**

下面是说明 slice()方法的示例:

**实施例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// slice() method

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
            ByteBuffer bb1
                = ByteBuffer.allocate(capacity);

            // putting the value in ByteBuffer
            bb1.put((byte)10);
            bb1.put((byte)20);

            // print the ByteBuffer
            System.out.println("Original ByteBuffer: "
                               + Arrays.toString(bb1.array()));

            // print the ByteBuffer position
            System.out.println("\nposition:  "
                               + bb1.position());

            // print the ByteBuffer capacity
            System.out.println("\ncapacity:  "
                               + bb1.capacity());

            // Creating a shared subsequence buffer
            // of given ByteBuffer
            // using slice() method
            ByteBuffer bb2 = bb1.slice();

            // print the shared subsequence buffer
            System.out.println("\nshared subsequence ByteBuffer: "
                               + Arrays.toString(bb2.array()));

            // print the ByteBuffer position
            System.out.println("\nposition:  " + bb2.position());

            // print the ByteBuffer capacity
            System.out.println("\ncapacity:  " + bb2.capacity());
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
Original ByteBuffer: [10, 20, 0, 0, 0]

position:  2

capacity:  5

shared subsequence ByteBuffer: [10, 20, 0, 0, 0]

position:  0

capacity:  3
```

**实施例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// slice() method

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
            ByteBuffer bb1 = ByteBuffer.allocate(capacity);

            // putting the value in ByteBuffer
            bb1.put((byte)10)
                .put((byte)20)
                .put((byte)30)
                .put((byte)40)
                .put((byte)50);

            // print the ByteBuffer
            System.out.println("Original ByteBuffer: "
                               + Arrays.toString(bb1.array()));

            // print the ByteBuffer position
            System.out.println("\nposition:  "
                               + bb1.position());

            // print the ByteBuffer capacity
            System.out.println("\ncapacity:  "
                               + bb1.capacity());

            // Creating a shared subsequence buffer
            // of given ByteBuffer
            // using slice() method
            ByteBuffer bb2 = bb1.slice();

            // print the shared subsequence buffer
            System.out.println("\nshared subsequence ByteBuffer: "
                               + Arrays.toString(bb2.array()));

            // print the ByteBuffer position
            System.out.println("\nposition:  " + bb2.position());

            // print the ByteBuffer capacity
            System.out.println("\ncapacity:  " + bb2.capacity());
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
Original ByteBuffer: [10, 20, 30, 40, 50]

position:  5

capacity:  5

shared subsequence ByteBuffer: [10, 20, 30, 40, 50]

position:  0

capacity:  0
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # slice–T4】