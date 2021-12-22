# Java 中的 DoubleBuffer flip()方法，示例

> 原文:[https://www . geesforgeks . org/double buffer-flip-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/doublebuffer-flip-methods-in-java-with-examples/)

**[java.nio.DoubleBuffer 类](https://www.geeksforgeeks.org/tag/java-doublebuffer/)** 的 **flip()** 方法用于翻转该缓冲区。通过翻转该缓冲区，这意味着缓冲区将被修剪到当前位置，然后该位置将被更改为零。在此过程中，如果缓冲区上有任何标记，则该标记将被自动丢弃。

**语法:**

```
public final DoubleBuffer flip()
```

**返回值:**这个方法返回翻转的 DoubleBuffer 实例。

下面是一些示例来说明 flip()方法:

**示例 1:**

```
// Java program to demonstrate
// flip() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declare and initialize
        // the double array
        double[] db
            = { 10.56, 20.34, 30.78 };

        // wrap the double array
        // into DoubleBuffer
        // using wrap() method
        DoubleBuffer doubleBuffer
            = DoubleBuffer.wrap(db);

        // set position at index 1
        doubleBuffer.position(1);

        // print the buffer
        System.out.println(
            "Buffer before flip: "
            + Arrays.toString(
                  doubleBuffer.array())
            + "\nPosition: "
            + doubleBuffer.position()
            + "\nLimit: "
            + doubleBuffer.limit());

        // Flip the Buffer
        // using flip() method
        doubleBuffer.flip();

        // print the buffer
        System.out.println(
            "\nBuffer after flip: "
            + Arrays.toString(
                  doubleBuffer.array())
            + "\nPosition: "
            + doubleBuffer.position()
            + "\nLimit: "
            + doubleBuffer.limit());
    }
}
```

**输出:**

```
Buffer before flip: [10.56, 20.34, 30.78]
Position: 1
Limit: 3

Buffer after flip: [10.56, 20.34, 30.78]
Position: 0
Limit: 1

```

**示例 2:**

```
// Java program to demonstrate
// flip() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // defining and allocating DoubleBuffer
        // using allocate() method
        DoubleBuffer doubleBuffer
            = DoubleBuffer.allocate(4);

        // put double value in DoubleBuffer
        // using put() method
        doubleBuffer.put(20.4);
        doubleBuffer.put(34.5);

        // set position at index 1
        doubleBuffer.position(1);

        // print the buffer
        System.out.println(
            "Buffer before flip: "
            + Arrays.toString(
                  doubleBuffer.array())
            + "\nPosition: "
            + doubleBuffer.position()
            + "\nLimit: "
            + doubleBuffer.limit());

        // Flip the Buffer
        // using flip() method
        doubleBuffer.flip();

        // print the buffer
        System.out.println(
            "\nBuffer after flip: "
            + Arrays.toString(
                  doubleBuffer.array())
            + "\nPosition: "
            + doubleBuffer.position()
            + "\nLimit: "
            + doubleBuffer.limit());
    }
}
```

**输出:**

```
Buffer before flip: [20.4, 34.5, 0.0, 0.0]
Position: 1
Limit: 4

Buffer after flip: [20.4, 34.5, 0.0, 0.0]
Position: 0
Limit: 1

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/double buffer . html # flip–](https://docs.oracle.com/javase/9/docs/api/java/nio/DoubleBuffer.html#flip--)