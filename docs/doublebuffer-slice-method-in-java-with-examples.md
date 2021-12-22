# Java 中的 DoubleBuffer slice()方法，示例

> 原文:[https://www . geesforgeks . org/double buffer-slice-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doublebuffer-slice-method-in-java-with-examples/)

类的 **slice()** 方法用于创建一个新的双缓冲区，其内容是给定缓冲区内容的共享子序列。

新缓冲区的内容将从该缓冲区的当前位置开始。对此缓冲区内容的更改将在新缓冲区中可见，反之亦然。两个缓冲器的位置、极限和标记值将是独立的。

新缓冲区的位置将为零，其容量和限制将是该缓冲区中剩余的双精度数，其标记将是未定义的。如果且仅当该缓冲区是直接的，则新缓冲区将是直接的；如果且仅当该缓冲区是只读的，则新缓冲区将是只读的。

**语法:**

```
public abstract DoubleBuffer slice()
```

**返回值:**该方法返回**新的双缓冲区。**

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

        // Declaring the capacity of the DoubleBuffer
        int capacity = 10;

        // Creating the DoubleBuffer
        try {

            // creating object of Doublebuffer
            // and allocating size capacity
            DoubleBuffer fb1 = DoubleBuffer.allocate(capacity);

            // putting the value in Doublebuffer
            fb1.put(8.56F);
            fb1.put(9.61F);

            // print the DoubleBuffer
            System.out.println("Original DoubleBuffer: "
                               + Arrays.toString(fb1.array()));

            // print the DoubleBuffer position
            System.out.println("\nposition:  " + fb1.position());

            // print the DoubleBuffer capacity
            System.out.println("\ncapacity:  " + fb1.capacity());

            // Creating a shared subsequence buffer of given DoubleBuffer
            // using slice() method
            DoubleBuffer fb2 = fb1.slice();

            // print the shared subsequence buffer
            System.out.println("\nshared subsequence DoubleBuffer: "
                               + Arrays.toString(fb2.array()));

            // print the DoubleBuffer position
            System.out.println("\nposition:  " + fb2.position());

            // print the DoubleBuffer capacity
            System.out.println("\ncapacity:  " + fb2.capacity());
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
Original DoubleBuffer: [8.5600004196167, 9.609999656677246, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]

position:  2

capacity:  10

shared subsequence DoubleBuffer: [8.5600004196167, 9.609999656677246, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]

position:  0

capacity:  8
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

        // Declaring the capacity of the DoubleBuffer
        int capacity = 10;

        // Creating the DoubleBuffer
        try {

            // creating object of Doublebuffer
            // and allocating size capacity
            DoubleBuffer fb1 = DoubleBuffer.allocate(capacity);

            // putting the value in Doublebuffer
            fb1.put(8.56F);
            fb1.put(9.61F);
            fb1.put(0.56F);
            fb1.put(3.61F);

            // print the DoubleBuffer
            System.out.println("Original DoubleBuffer: "
                               + Arrays.toString(fb1.array()));

            // print the DoubleBuffer position
            System.out.println("\nposition:  " + fb1.position());

            // print the DoubleBuffer capacity
            System.out.println("\ncapacity:  " + fb1.capacity());

            // Creating a shared subsequence buffer of given DoubleBuffer
            // using slice() method
            DoubleBuffer fb2 = fb1.slice();
            fb2.put(2.34F);
            fb2.put(6.34F);

            // print the shared subsequence buffer
            System.out.println("\nshared subsequence DoubleBuffer: "
                               + Arrays.toString(fb2.array()));

            // print the DoubleBuffer position
            System.out.println("\nposition:  " + fb2.position());

            // print the DoubleBuffer capacity
            System.out.println("\ncapacity:  " + fb2.capacity());
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
Original DoubleBuffer: [8.5600004196167, 9.609999656677246, 0.5600000023841858, 3.609999895095825, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]

position:  4

capacity:  10

shared subsequence DoubleBuffer: [8.5600004196167, 9.609999656677246, 0.5600000023841858, 3.609999895095825, 2.3399999141693115, 6.340000152587891, 0.0, 0.0, 0.0, 0.0]

position:  2

capacity:  6
```