# Java 中的缓冲区标记()方法，示例

> 原文:[https://www . geesforgeks . org/buffer-mark-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/buffer-mark-methods-in-java-with-examples/)

[java.nio.Buffer 类](https://www.geeksforgeeks.org/tag/java-bytebuffer/)的**标记()**方法用于将该缓冲区的标记设置在其位置。

**语法:**

```
public Buffer mark()
```

**返回值:**这个方法返回这个缓冲区。

下面是说明 mark()方法的示例:

**示例 1:**

```
// Java program to demonstrate
// mark() method

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

            // try to call reset() to restore
            // to the position we marked
            bb1.reset();

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
position after reset: 2

```

**示例 2:** 演示无效标记异常

```
// Java program to demonstrate
// mark() method

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
            bb1.position(1);

            // display position
            System.out.println("position before reset: "
                               + bb1.position());

            // try to call reset() to restore
            // to the position we marked
            bb1.reset();

            // display position
            System.out.println("position after reset: "
                               + bb1.position());
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

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/buffer . html # mark–](https://docs.oracle.com/javase/9/docs/api/java/nio/Buffer.html#mark--)