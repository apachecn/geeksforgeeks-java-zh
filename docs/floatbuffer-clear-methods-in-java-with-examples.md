# Java 中的 FloatBuffer clear()方法，示例

> 原文:[https://www . geeksforgeeks . org/float buffer-clear-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/floatbuffer-clear-methods-in-java-with-examples/)

**clear()**[Java . nio . float buffer](https://www.geeksforgeeks.org/tag/java-floatbuffer/)**类的**方法用来清除这个缓冲区。该方法将位置和限制分别设置为零和容量，并丢弃标记。当需要顺序进行通道读取或放入操作时，应调用此方法。这意味着如果需要读取缓冲区，那么 clear()方法会使缓冲区就绪，并将位置设置为零。例如:

```
buf.clear();     // Prepare buffer for reading
in.read(buf);    // Read data

```

该方法实际上并没有擦除缓冲区中的数据，但它的命名就像擦除了一样，因为它最常用于删除的情况。

**语法:**

```
public final FloatBuffer clear()
```

**参数:**该方法不取任何参数。

**返回值:**这个方法在清除了这个 FloatBuffer 实例中的所有数据后，返回这个 float buffer 实例。

以下是说明 clear()方法的示例:

**例 1:**

```
// Java program to demonstrate
// clear() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        try {

            float[] farr = { 2.5f, 3.5f, 4.5f, 6.7f };

            // creating object of FloatBuffer
            // and allocating size capacity
            FloatBuffer fb
                = FloatBuffer.wrap(farr);

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

            // try to call clear() to restore
            // to the position at index 0
            // by discarding the mark
            fb.clear();

            // display position
            System.out.println("position after reset: "
                               + fb.position());
        }

        catch (InvalidMarkException e) {
            System.out.println("new position is less than "
                               + "the position we "
                               + "marked before ");
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

**例 2:**

```
// Java program to demonstrate
// clear() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        float[] farr = { 2.4f, 105.4f, 13.9f, 23.45f };

        // creating object of FloatBuffer
        // and allocating size capacity
        FloatBuffer fb = FloatBuffer.wrap(farr);

        // try to set the position at index 3
        fb.position(3);

        // display position
        System.out.println("position before clear: "
                           + fb.position());

        // try to call clear() to restore
        // to the position at index 0
        // by discarding the mark
        fb.clear();

        // display position
        System.out.println("position after clear: "
                           + fb.position());
    }
}
```

**输出:**

```
position before clear: 3
position after clear: 0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/float buffer . html # clear–](https://docs.oracle.com/javase/9/docs/api/java/nio/FloatBuffer.html#clear--)