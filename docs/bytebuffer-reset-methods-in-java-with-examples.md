# Java 中的字节缓冲复位()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-reset-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-reset-methods-in-java-with-examples/)

[java.nio.ByteBuffer 类](https://www.geeksforgeeks.org/tag/java-bytebuffer/)的 **reset()** 方法用于将该缓冲区的位置重置到之前标记的位置。调用此方法既不会改变也不会丢弃标记的值。

**语法:**

```
public ByteBuffer reset()
```

**返回值:**这个方法返回这个缓冲区。

以下是说明 reset()方法的示例:

**示例 1:**

```
// Java program to demonstrate
// reset() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        try {

            byte[] barr = { 10, 20, 30, 40 };

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.wrap(barr);

            // try to set the position at index 2
            bb.position(2);

            // Set this buffer mark position
            // using mark() method
            bb.mark();

            // try to set the position at index 4
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

        catch (InvalidMarkException e) {
            System.out.println("new position is less than "
                               + "the position we marked before ");
            System.out.println("Exception throws: " + e);
        }
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
// reset() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        try {

            byte[] barr = { 10, 20, 30, 40 };

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.wrap(barr);

            // try to set the position at index 2
            bb.position(2);

            // Set this buffer mark position
            // using mark() method
            bb.mark();

            // try to set the position at index 4
            bb.position(1);

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

        catch (InvalidMarkException e) {
            System.out.println("\nnew position is less than "
                               + "the position we marked before ");
            System.out.println("Exception throws: " + e);
        }
    }
}
```

**输出:**

```
position before reset: 1

new position is less than the position we marked before 
Exception throws: java.nio.InvalidMarkException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # reset–](https://docs.oracle.com/javase/9/docs/api/java/nio/ByteBuffer.html#reset--)