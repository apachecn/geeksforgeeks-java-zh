# Java 中的 IntBuffer rewind()方法，示例

> 原文:[https://www . geesforgeks . org/int buffer-rewind-method-in-Java-with-examples/](https://www.geeksforgeeks.org/intbuffer-rewind-method-in-java-with-examples/)

[java.nio.IntBuffer 类](https://www.geeksforgeeks.org/tag/java-intBuffer/)的**倒带()**方法用来倒带这个缓冲区。位置设置为零，标记被丢弃。假设已经适当地设置了限制，则在一系列通道写入或获取操作之前调用此方法。调用此方法既不会改变也不会丢弃标记的值。

**语法:**

```java
public final IntBuffer rewind()
```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回这个缓冲区。

以下是说明 rewind()方法的示例:

**示例 1:**

```java
// Java program to demonstrate
// rewind() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating IntBuffer
        // using allocate() method
        IntBuffer intBuffer
            = IntBuffer.allocate(4);

        // put char value in intBuffer
        // using put() method
        intBuffer.put(10);
        intBuffer.put(20);

        // print the int buffer
        System.out.println(
            "Buffer before operation: "
            + Arrays.toString(
                  intBuffer.array())
            + "\nPosition: "
            + intBuffer.position()
            + "\nLimit: "
            + intBuffer.limit());

        // rewind the Buffer
        // using rewind() method
        intBuffer.rewind();

        // print the intbuffer
        System.out.println(
            "\nBuffer after operation: "
            + Arrays.toString(
                  intBuffer.array())
            + "\nPosition: "
            + intBuffer.position()
            + "\nLimit: "
            + intBuffer.limit());
    }
}
```

**输出:**

```java
Buffer before operation: [10, 20, 0, 0]
Position: 2
Limit: 4

Buffer after operation: [10, 20, 0, 0]
Position: 0
Limit: 4

```

**示例 2:**

```java
// Java program to demonstrate
// rewind() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating IntBuffer
        // using allocate() method
        IntBuffer intBuffer
            = IntBuffer.allocate(5);

        // put int value in IntBuffer
        // using put() method
        intBuffer.put(10);
        intBuffer.put(20);
        intBuffer.put(30);

        // mark will be going to
        // discarded by rewind()
        intBuffer.mark();

        // print the buffer
        System.out.println(
            "Buffer before operation: "
            + Arrays.toString(
                  intBuffer.array())
            + "\nPosition: "
            + intBuffer.position()
            + "\nLimit: "
            + intBuffer.limit());

        // Rewind the Buffer
        // using rewind() method
        intBuffer.rewind();

        // print the buffer
        System.out.println(
            "\nBuffer after operation: "
            + Arrays.toString(
                  intBuffer.array())
            + "\nPosition: "
            + intBuffer.position()
            + "\nLimit: "
            + intBuffer.limit());
    }
}
```

**输出:**

```java
Buffer before operation: [10, 20, 30, 0, 0]
Position: 3
Limit: 5

Buffer after operation: [10, 20, 30, 0, 0]
Position: 0
Limit: 5

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/intbuffer . html # rewind–](https://docs.oracle.com/javase/9/docs/api/java/nio/IntBuffer.html#rewind--)