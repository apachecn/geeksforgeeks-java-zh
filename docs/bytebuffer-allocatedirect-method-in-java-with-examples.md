# Java 中的字节缓冲区分配直接()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-allocatedirect-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-allocatedirect-method-in-java-with-examples/)

使用 **java.nio.ByteBuffer** 类的 **allocateDirect()** 方法分配一个新的直接字节缓冲区。

新缓冲区的位置将为零，其限制将是其容量，其标记将是未定义的，并且其每个元素将被初始化为零。它是否有一个后备数组是未知的。

该方法比 allocate()方法快 25%-75%。

**语法:**

```java
public static ByteBuffer allocateDirect(int capacity)
```

**参数:**该方法以**容量**字节为参数。

**返回值:**该方法返回**新的字节缓冲区。**

**异常:**此方法抛出 **IllegalArgumentException** ，如果容量为负整数。

以下是说明 allocateDirect()方法的示例:

**实施例 1:**

```java
// Java program to demonstrate
// allocateDirect() method

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
            ByteBuffer bb = ByteBuffer.allocateDirect(capacity);

            // creating byte array of size capacity
            byte[] value = { 20, 30, 40, 50 };

            // wrap the byte array into ByteBuffer
            bb = ByteBuffer.wrap(value);

            // print the ByteBuffer
            System.out.println("Direct ByteBuffer:  "
                               + Arrays.toString(bb.array()));

            // print the state of the buffer
            System.out.print("\nState of the ByteBuffer : ");
            System.out.println(bb.toString());
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
Direct ByteBuffer:  [20, 30, 40, 50]

State of the ByteBuffer : java.nio.HeapByteBuffer[pos=0 lim=4 cap=4]

```

**示例 2:** 显示 IllegalArgumentException

```java
// Java program to demonstrate
// allocateDirect() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity
        // with negative value
        int capacity = -4;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity

            System.out.println("Trying to allocate"
                               + " negative value in ByteBuffer");
            ByteBuffer bb = ByteBuffer.allocateDirect(capacity);

            // creating byte array of size capacity
            byte[] value = { 20, 30, 40, 50 };

            // wrap the byte array into ByteBuffer
            bb = ByteBuffer.wrap(value);

            // print the ByteBuffer
            System.out.println("Direct ByteBuffer:  "
                               + Arrays.toString(bb.array()));

            // print the state of the buffer
            System.out.print("\nState of the ByteBuffer : ");
            System.out.println(bb.toString());
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
Exception thrown : java.lang.IllegalArgumentException: Negative capacity: -4

```