# Java 中的 IntBuffer 标记()方法，示例

> 原文:[https://www . geesforgeks . org/int buffer-mark-method-in-Java-with-examples/](https://www.geeksforgeeks.org/intbuffer-mark-method-in-java-with-examples/)

[java.nio.IntBuffer 类](https://www.geeksforgeeks.org/tag/java-intbuffer/)的**标记()**方法用于将该 IntBuffer 的当前位置标记为该缓冲区的标记。

**语法:**

```
public final IntBuffer mark()
```

**参数:**该方法不取任何参数。

**返回值:**在当前位置设置缓冲区标记后，该方法返回该 IntBuffer。

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

            int[] farr = { 10, 20, 30, 40 };

            // creating object of IntBuffer
            // and allocating size capacity
            IntBuffer ib = IntBuffer.wrap(farr);

            // try to set the position at index 2
            ib.position(2);

            // Set this buffer mark position
            // using mark() method
            ib.mark();

            // try to set the position at index 4
            ib.position(4);

            // display position
            System.out.println("position before reset: "
                               + ib.position());

            // try to call reset() to restore
            // to the position we marked
            ib.reset();

            // display position
            System.out.println("position after reset: "
                               + ib.position());
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

            int[] farr = { 10, 20, 30, 40 };

            // creating object of IntBuffer
            // and allocating size capacity
            IntBuffer ib = IntBuffer.wrap(farr);

            // try to set the position at index 2
            ib.position(2);

            // Set this buffer mark position
            // using mark() method
            ib.mark();

            // try to set the position at index 1
            ib.position(1);

            // display position
            System.out.println("position before reset: "
                               + ib.position());

            // try to call reset() to restore
            // to the position we marked
            ib.reset();

            // display position
            System.out.println("position after reset: "
                               + ib.position());
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

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/intbuffer . html # mark–](https://docs.oracle.com/javase/9/docs/api/java/nio/IntBuffer.html#mark--)