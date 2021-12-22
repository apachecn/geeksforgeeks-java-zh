# Java 中的字节缓冲分配()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-allocate-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-allocate-method-in-java-with-examples/)

**java.nio.ByteBuffer** 类的 **allocate()** 方法用于分配一个新的字节缓冲区。

新缓冲区的位置将为零，其限制将是其容量，其标记将是未定义的，并且其每个元素将被初始化为零。它将有一个后备数组，并且它的数组偏移量为零。

**语法:**

```java
public static ByteBuffer allocate(int capacity)
```

**参数:**该方法以容量为参数，以字节为单位。

**返回值:**这个方法返回新的字节缓冲区。

**抛出:**这个方法抛出 **IllegalArgumentException** ，如果容量是负整数

下面是说明 allocate()方法的示例:

**实施例 1:**

```java
// Java program to demonstrate
// allocate() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 4;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the int to byte typecast value
            // in ByteBuffer using putInt() method
            bb.put((byte)20);
            bb.put((byte)30);
            bb.put((byte)40);
            bb.put((byte)50);
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer:  "
                               + Arrays.toString(bb.array()));
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

```java
Original ByteBuffer:  [20, 30, 40, 50]

```

**实施例 2:**

```java
// Java program to demonstrate
// allocate() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity with negative
        // value of the ByteBuffer
        int capacity = -4;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            System.out.println("Trying to allocate negative"+
                                         " value in ByteBuffer");
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting int to byte typecast value
            // in ByteBuffer using putInt() method
            bb.put((byte)20);
            bb.put((byte)30);
            bb.put((byte)40);
            bb.put((byte)50);
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer:  "
                               + Arrays.toString(bb.array()));
        }

        catch (IllegalArgumentException e) {

            System.out.println("Exception thrown : " + e);
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
Trying to allocate negative value in ByteBuffer
Exception thrown : java.lang.IllegalArgumentException

```