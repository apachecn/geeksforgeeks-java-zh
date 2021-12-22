# Java 中的 CharBuffer slice()方法

> 原文:[https://www . geesforgeks . org/charbuffer-slice-method-in-Java/](https://www.geeksforgeeks.org/charbuffer-slice-method-in-java/)

**slice()** 方法的 **java.nio.charBuffer** 类用于创建一个**新的 char buffer** ，其内容是给定缓冲区内容的共享子序列。

新缓冲区的内容将从该缓冲区的当前位置开始。新的缓冲区将显示缓冲区内容的变化，反之亦然。两个缓冲器的位置、极限和标记值将是独立的。

新缓冲区的位置将为零，其容量和限制将是该缓冲区中剩余的整数数量，其标记将是未定义的。如果且仅当，此缓冲区是直接的，那么新缓冲区将是直接的，并且当且仅当，此缓冲区是只读的时，它将是只读的。

**语法:**

```
public abstract CharBuffer slice()
```

**返回值:**该方法返回**新的字符缓冲区。**

下面是说明 slice()方法的示例:

**例 1:**

```
// Java program to demonstrate
// slice() method
import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the CharBuffer
        int capacity = 10;

        // Creating the CharBuffer
        try {

            // creating object of Charbuffer
            // and allocating size capacity
            CharBuffer cb1 = CharBuffer.allocate(capacity);

            // putting the value in intbuffer
            cb1.put('a');
            cb1.put('b');

            // print the CharBuffer
            System.out.println("Original CharBuffer: "
                               + Arrays.toString(cb1.array()));

            // print the CharBuffer position
            System.out.println("position: " + cb1.position());

            // print the CharBuffer capacity
            System.out.println("capacity: " + cb1.capacity());

            // Creating a shared subsequance buffer of given CharBuffer
            // using slice() method
            CharBuffer cb2 = cb1.slice();

            // print the shared subsequance buffer
            System.out.println("shared subsequance CharBuffer: "
                               + Arrays.toString(cb2.array()));

            // print the CharBuffer position
            System.out.println("position: " + cb2.position());

            // print the CharBuffer capacity
            System.out.println("capacity: " + cb2.capacity());
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
Original CharBuffer: [a, b, , , , , , , , ]
position: 2
capacity: 10
shared subsequance CharBuffer: [a, b, , , , , , , , ]
position: 0
capacity: 8

```

**例 2:**

```
// Java program to demonstrate
// slice() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the CharBuffer
        int capacity = 10;

        // Creating the CharBuffer
        try {

            // creating object of charbuffer
            // and allocating size capacity
            CharBuffer cb1 = CharBuffer.allocate(capacity);

            // putting the value in floatbuffer
            cb1.put('a');
            cb1.put('b');
            cb1.put('c');
            cb1.put('d');

            // print the CharBuffer
            System.out.println("Original CharBuffer: "
                               + Arrays.toString(cb1.array()));

            // print the CharBuffer position
            System.out.println("position: " + cb1.position());

            // print the CharBuffer capacity
            System.out.println("capacity: " + cb1.capacity());

            // Creating a shared subsequance buffer of given CharBuffer
            // using slice() method
            CharBuffer cb2 = cb1.slice();
            cb2.put('k');
            cb2.put('l');

            // print the shared subsequance buffer
            System.out.println("shared subsequance CharBuffer: "
                               + Arrays.toString(cb2.array()));

            // print the CharBuffer position
            System.out.println("position: " + cb2.position());

            // print the CharBuffer capacity
            System.out.println("capacity: " + cb2.capacity());
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
Original CharBuffer: [a, b, c, d, , , , , , ]
position: 4
capacity: 10
shared subsequance CharBuffer: [a, b, c, d, k, l, , , , ]
position: 2
capacity: 6

```