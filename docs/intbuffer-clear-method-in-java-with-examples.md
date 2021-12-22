# Java 中的 IntBuffer clear()方法，示例

> 原文:[https://www . geesforgeks . org/int buffer-clear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/intbuffer-clear-method-in-java-with-examples/)

**[Java . nio . int buffer](https://www.geeksforgeeks.org/tag/java-intbuffer/)**类的 **clear()** 方法用来清除这个缓冲区。清除该缓冲区时，进行以下更改:

*   Set position to zero.
*   Set limit to capacity
*   The tag is discarded.

**语法:**

```java
public final IntBuffer clear()
```

**参数:**该方法不取任何参数。

**返回值:**该方法在清除 IntBuffer 实例中的所有数据后返回该实例。

以下是说明 clear()方法的示例:

**示例 1:**

```java
// Java program to demonstrate
// clear() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        try {

            int[] iarr = { 10, 20, 30, 40 };

            // creating object of IntBuffer
            // and allocating size capacity
            IntBuffer ib
                = IntBuffer.wrap(iarr);

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

            // try to call clear() to restore
            // to the position at index 0
            // by discarding the mark
            ib.clear();

            // display position
            System.out.println("position after reset: "
                               + ib.position());
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

```java
position before reset: 4
position after reset: 0

```

**示例 2:**

```java
// Java program to demonstrate
// clear() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        int[] iarr = { 10, 20, 30, 40 };

        // creating object of IntBuffer
        // and allocating size capacity
        IntBuffer ib = IntBuffer.wrap(iarr);

        // try to set the position at index 3
        ib.position(3);

        // display position
        System.out.println("position before clear: "
                           + ib.position());

        // try to call clear() to restore
        // to the position at index 0
        // by discarding the mark
        ib.clear();

        // display position
        System.out.println("position after clear: "
                           + ib.position());
    }
}
```

**输出:**

```java
position before clear: 3
position after clear: 0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/intbuffer . html # rewind–](https://docs.oracle.com/javase/9/docs/api/java/nio/IntBuffer.html#rewind--)