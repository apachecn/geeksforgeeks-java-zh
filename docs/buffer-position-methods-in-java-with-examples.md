# Java 中的缓冲位置()方法，示例

> 原文:[https://www . geesforgeks . org/buffer-position-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/buffer-position-methods-in-java-with-examples/)

**[java.nio.Buffer 类](https://docs.oracle.com/javase/9/docs/api/java/nio/Buffer.html#)** 的**位置(int newPosition)** 方法用于设置该缓冲区的位置。如果标记被定义并且比新位置大，则它被丢弃。

**语法:**

```java
public Buffer position(int newPosition)
```

**参数:**该方法以**新位置**为参数，为新位置值。它必须是非负的，并且不大于电流限制。

**返回值:**这个方法返回这个缓冲区。

以下是说明**位置()**方法的例子:

**示例 1:**

```java
// Java program to demonstrate
// position() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        byte[] barr = { 10, 20, 30, 40 };

        // creating object of ByteBuffer
        // and allocating size capacity
        ByteBuffer bb = ByteBuffer.wrap(barr);

        // Typecasting ByteBuffer into Buffer
        Buffer bb1 = (Buffer)bb;

        // try to set the position at index 2
        // using position() method
        bb1.position(2);

        // Set this buffer mark position
        bb1.mark();

        // try to set the position at index 4
        // using position() method
        bb1.position(4);

        // display position
        System.out.println("position before reset: "
                           + bb.position());

        // try to call reset() to restore
        // to the position we marked
        bb1.reset();

        // display position
        System.out.println("position after reset: "
                           + bb1.position());
    }
}
```

**输出:**

```java
position before reset: 4
position after reset: 2

```

**示例 2:**

```java
// Java program to demonstrate
// position() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // creating object of ByteBuffer
        // and allocating size capacity
        ByteBuffer bb = ByteBuffer.allocate(4);

        // Typecasting ByteBuffer into Buffer
        Buffer bb1 = (Buffer)bb;

        // try to set the position at index 1
        // using position() method
        bb1.position(3);

        // display position
        System.out.println("position before clear: "
                           + bb1.position());

        // try to clear the Buffer
        // using clear() method
        bb1.clear();

        // display position
        System.out.println("position after clear: "
                           + bb1.position());
    }
}
```

**输出:**

```java
position before clear: 3
position after clear: 0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/buffer . html # position-int-](https://docs.oracle.com/javase/9/docs/api/java/nio/Buffer.html#position-int-)