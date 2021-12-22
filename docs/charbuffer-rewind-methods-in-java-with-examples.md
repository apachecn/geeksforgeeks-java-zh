# Java 中的 CharBuffer rewind()方法，示例

> 原文:[https://www . geesforgeks . org/char buffer-rewind-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/charbuffer-rewind-methods-in-java-with-examples/)

[java.nio.CharBuffer 类](https://www.geeksforgeeks.org/tag/java-charbuffer/)的**倒带()**方法用来倒带这个缓冲区。位置设置为零，标记被丢弃。假设已经适当地设置了限制，则在一系列通道写入或获取操作之前调用此方法。调用此方法既不会改变也不会丢弃标记的值。

**语法:**

```java
public ByteBuffer rewind()
```

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
        // defining and allocating CharBuffer
        // using allocate() method
        CharBuffer charBuffer = CharBuffer.allocate(4);

        // put char value in charBuffer
        // using put() method
        charBuffer.put('a');
        charBuffer.put((char)105);

        // print the char buffer
        System.out.println("Buffer before operation: "
                           + Arrays.toString(
                                 charBuffer.array())
                           + "\nPosition: "
                           + charBuffer.position()
                           + "\nLimit: "
                           + charBuffer.limit());

        // rewind the Buffer
        // using rewind() method
        charBuffer.rewind();

        // print the charbuffer
        System.out.println("\nBuffer after operation: "
                           + Arrays.toString(
                                 charBuffer.array())
                           + "\nPosition: "
                           + charBuffer.position()
                           + "\nLimit: "
                           + charBuffer.limit());
    }
}
```

**输出:**

```java
Buffer before operation: [a, i,,  ]
Position: 2
Limit: 4

Buffer after operation: [a, i,,  ]
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
        // defining and allocating CharBuffer
        // using allocate() method
        CharBuffer charBuffer
            = CharBuffer.allocate(5);

        // put byte value in charBuffer
        // using put() method
        charBuffer.put('a');
        charBuffer.put('b');
        charBuffer.put('c');

        // mark will be going to discarded by rewind()
        charBuffer.mark();

        // print the buffer
        System.out.println("Buffer before operation: "
                           + Arrays.toString(
                                 charBuffer.array())
                           + "\nPosition: "
                           + charBuffer.position()
                           + "\nLimit: "
                           + charBuffer.limit());

        // Rewind the Buffer
        // using rewind() method
        charBuffer.rewind();

        // print the buffer
        System.out.println("\nBuffer after operation: "
                           + Arrays.toString(
                                 charBuffer.array())
                           + "\nPosition: "
                           + charBuffer.position()
                           + "\nLimit: "
                           + charBuffer.limit());
    }
}
```

**输出:**

```java
Buffer before operation: [a, b, c,,  ]
Position: 3
Limit: 5

Buffer after operation: [a, b, c,,  ]
Position: 0
Limit: 5

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charbuffer . html # rewind–](https://docs.oracle.com/javase/9/docs/api/java/nio/CharBuffer.html#rewind--)