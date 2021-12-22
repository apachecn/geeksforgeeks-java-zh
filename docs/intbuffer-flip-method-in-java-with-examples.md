# Java 中的 IntBuffer flip()方法，示例

> 原文:[https://www . geesforgeks . org/int buffer-flip-method-in-Java-with-examples/](https://www.geeksforgeeks.org/intbuffer-flip-method-in-java-with-examples/)

**[java.nio.IntBuffer 类](https://www.geeksforgeeks.org/tag/java-intbuffer/)** 的 **flip()** 方法用来翻转这个缓冲区。通过翻转该缓冲区，这意味着缓冲区将被修剪到当前位置，然后该位置将被更改为零。在此过程中，如果缓冲区上有任何标记，则该标记将被自动丢弃。

**语法:**

```
public final IntBuffer flip()
```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回翻转后的 IntBuffer 实例。

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
        // the int array
        int[] ib
            = { 10, 20, 30 };

        // wrap the int array
        // into IntBuffer
        // using wrap() method
        IntBuffer intBuffer
            = IntBuffer.wrap(ib);

        // set position at index 1
        intBuffer.position(1);

        // print the buffer
        System.out.println(
            "Buffer before flip: "
            + Arrays.toString(
                  intBuffer.array())
            + "\nPosition: "
            + intBuffer.position()
            + "\nLimit: "
            + intBuffer.limit());

        // Flip the Buffer
        // using flip() method
        intBuffer.flip();

        // print the buffer
        System.out.println(
            "\nBuffer after flip: "
            + Arrays.toString(
                  intBuffer.array())
            + "\nPosition: "
            + intBuffer.position()
            + "\nLimit: "
            + intBuffer.limit());
    }
}
```

**输出:**

```
Buffer before flip: [10, 20, 30]
Position: 1
Limit: 3

Buffer after flip: [10, 20, 30]
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

        // defining and allocating IntBuffer
        // using allocate() method
        IntBuffer intBuffer
            = IntBuffer.allocate(4);

        // put int value in IntBuffer
        // using put() method
        intBuffer.put(20);
        intBuffer.put(34);

        // set position at index 1
        intBuffer.position(1);

        // print the buffer
        System.out.println(
            "Buffer before flip: "
            + Arrays.toString(
                  intBuffer.array())
            + "\nPosition: "
            + intBuffer.position()
            + "\nLimit: "
            + intBuffer.limit());

        // Flip the Buffer
        // using flip() method
        intBuffer.flip();

        // print the buffer
        System.out.println(
            "\nBuffer after flip: "
            + Arrays.toString(
                  intBuffer.array())
            + "\nPosition: "
            + intBuffer.position()
            + "\nLimit: "
            + intBuffer.limit());
    }
}
```

**输出:**

```
Buffer before flip: [20, 34, 0, 0]
Position: 1
Limit: 4

Buffer after flip: [20, 34, 0, 0]
Position: 0
Limit: 1

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/intbuffer . html # flip–](https://docs.oracle.com/javase/9/docs/api/java/nio/IntBuffer.html#flip--)