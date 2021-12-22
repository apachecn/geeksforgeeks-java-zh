# Java 中的 FloatBuffer reset()方法，示例

> 原文:[https://www . geeksforgeeks . org/float buffer-reset-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/floatbuffer-reset-methods-in-java-with-examples/)

[java.nio.FloatBuffer 类](https://www.geeksforgeeks.org/tag/java-floatbuffer/)的 **reset()** 方法用于将该缓冲区的位置重置到之前标记的位置。在这种情况下，标记的值既不改变也不丢弃。它有助于恢复缓冲区中以前标记的值。

**语法:**

```java
public final FloatBuffer reset()
```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回这个缓冲区。

以下是说明 reset()方法的示例:

**示例 1:**

```java
// Java program to demonstrate
// reset() method

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
            System.out.println("new position is less than "
                               + "the position we"
                               + " marked before ");
            System.out.println("Exception throws: " + e);
        }
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
// reset() method

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
            System.out.println("\nnew position is less than "
                               + "the position we"
                               + " marked before ");
            System.out.println("Exception throws: " + e);
        }
    }
}
```

**输出:**

```java
position before reset: 1

new position is less than the position we marked before 
Exception throws: java.nio.InvalidMarkException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/float buffer . html # reset–](https://docs.oracle.com/javase/9/docs/api/java/nio/FloatBuffer.html#reset--)