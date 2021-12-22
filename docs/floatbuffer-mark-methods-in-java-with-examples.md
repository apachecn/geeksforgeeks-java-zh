# Java 中的 FloatBuffer mark()方法，示例

> 原文:[https://www . geeksforgeeks . org/float buffer-mark-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/floatbuffer-mark-methods-in-java-with-examples/)

[java.nio.FloatBuffer 类](https://www.geeksforgeeks.org/tag/java-floatbuffer/)的**标记()**方法用于将该 FloatBuffer 的当前位置标记为该缓冲区的标记。

**语法:**

```
public final FloatBuffer mark()
```

**参数:**该方法不取任何参数。

**返回值:**在当前位置设置缓冲区标记后，该方法返回该浮动缓冲区。

以下示例说明了 mark()方法:

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

            float[] farr = { 10.5f, 20.5f, 30.5f, 40.5f };

            // creating object of FloatBuffer
            // and allocating size capacity
            FloatBuffer fb = FloatBuffer.wrap(farr);

            // try to set the position at index 2
            fb.position(2);

            // Set this buffer mark position
            // using mark() method
            fb.mark();

            // try to set the position at index 4
            fb.position(4);

            // display position
            System.out.println("position before reset: "
                               + fb.position());

            // try to call reset() to restore
            // to the position we marked
            fb.reset();

            // display position
            System.out.println("position after reset: "
                               + fb.position());
        }

        catch (InvalidMarkException e) {
            System.out.println("New position "
                               + "is less than "
                               + "the position "
                               + "marked before ");
            System.out.println("Exception throws: "
                               + e);
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

            float[] farr = { 10.5f, 20.5f, 30.5f, 40.5f };

            // creating object of FloatBuffer
            // and allocating size capacity
            FloatBuffer fb = FloatBuffer.wrap(farr);

            // try to set the position at index 2
            fb.position(2);

            // Set this buffer mark position
            // using mark() method
            fb.mark();

            // try to set the position at index 1
            fb.position(1);

            // display position
            System.out.println("position before reset: "
                               + fb.position());

            // try to call reset() to restore
            // to the position we marked
            fb.reset();

            // display position
            System.out.println("position after reset: "
                               + fb.position());
        }

        catch (InvalidMarkException e) {
            System.out.println("\nNew position "
                               + "is less than "
                               + "the position "
                               + "marked before ");
            System.out.println("Exception throws: "
                               + e);
        }
    }
}
```

**输出:**

```
position before reset: 1

New position is less than the position marked before 
Exception throws: java.nio.InvalidMarkException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/float buffer . html # mark–](https://docs.oracle.com/javase/9/docs/api/java/nio/FloatBuffer.html#mark--)