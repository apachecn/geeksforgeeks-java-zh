# 用示例缓冲 Java 中的 clear()方法

> 原文:[https://www . geesforgeks . org/buffer-clear-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/buffer-clear-methods-in-java-with-examples/)

[java.nio.ByteBuffer 类](https://www.geeksforgeeks.org/tag/java-bytebuffer/)的 **clear()** 方法用于清除该缓冲区。位置设置为零，限制设置为容量，标记被丢弃。在使用一系列通道读取或放置操作来填充此缓冲区之前，请调用此方法。

**例如:**

```

buf.clear();     // Prepare buffer for reading
in.read(buf);    // Read data

```

这种方法实际上并不擦除缓冲区中的数据，但它的命名就好像它擦除了数据一样，因为它最常用于这种情况。

**语法:**

```
public Buffer clear()
```

**返回值:**这个方法返回这个缓冲区。

以下是说明 clear()方法的示例:

**示例 1:**

```
// Java program to demonstrate
// clear() method

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

            // Typecasting ByteBuffer into Buffer
            Buffer bb1 = (Buffer)bb;

            // try to set the position at index 2
            bb1.position(2);

            // Set this buffer mark position
            // using mark() method
            bb1.mark();

            // try to set the position at index 4
            bb1.position(4);

            // display position
            System.out.println("position before reset: "
                               + bb1.position());

            // try to call clear() to restore
            // to the position at index 0
            // by discarding the mark
            bb1.clear();

            // display position
            System.out.println("position after reset: "
                               + bb1.position());
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
position after reset: 0

```

**示例 2:**

```
// Java program to demonstrate
// clear() method

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

            // Typecasting ByteBuffer into Buffer
            Buffer bb1 = (Buffer)bb;

            // try to set the position at index 2
            bb1.position(3);

            // display position
            System.out.println("position before clear: "
                               + bb1.position());

            // try to call clear() to restore
            // to the position at index 0
            // by discarding the mark
            bb1.clear();

            // display position
            System.out.println("position after clear: "
                               + bb1.position());
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
position before clear: 3
position after clear: 0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/buffer . html # clear–](https://docs.oracle.com/javase/9/docs/api/java/nio/Buffer.html#clear--)