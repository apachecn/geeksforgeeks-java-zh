# Java 中的字节缓冲位置()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-position-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-position-methods-in-java-with-examples/)

**[java.nio.ByteBuffer 类](https://www.geeksforgeeks.org/tag/java-bytebuffer/)** 的**位置(int newPosition)** 方法用于设置该缓冲区的位置。如果标记被定义并且比新位置大，则它被丢弃。

**语法:**

```
public ByteBuffer position(int newPosition)
```

**参数:**该方法以**新位置**为参数，为新位置值。它必须是非负的，并且不大于电流限制。

**返回值:**这个方法返回这个缓冲区。

以下是说明**位置()**方法的例子:

**示例 1:**

```
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

        // try to set the position at index 2
        // using position() method
        bb.position(2);

        // Set this buffer mark position
        bb.mark();

        // try to set the position at index 4
        // using position() method
        bb.position(4);

        // display position
        System.out.println("position before reset: "
                           + bb.position());

        // try to call reset() to restore
        // to the position we marked
        bb.reset();

        // display position
        System.out.println("position after reset: "
                           + bb.position());
    }
}
```

**输出:**

```
position before reset: 4
position after reset: 2

```

**示例 2:**

```
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

        // try to set the position at index 1
        // using position() method
        bb.position(1);

        // putting the value of ByteBuffer
        // using put() method
        bb.put((byte)10);

        // try to set the position at index 3
        // using position() method
        bb.position(3);

        // putting the value of ByteBuffer
        // using put() method
        bb.put((byte)30);

        // display position
        System.out.println("ByteBuffer: "
                           + Arrays.toString(bb.array()));
    }
}
```

**输出:**

```
ByteBuffer: [0, 10, 0, 30]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # position-int-](https://docs.oracle.com/javase/9/docs/api/java/nio/ByteBuffer.html#position-int-)