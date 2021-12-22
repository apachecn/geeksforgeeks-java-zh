# Java 中的 FloatBuffer flip()方法，示例

> 原文:[https://www . geeksforgeeks . org/float buffer-flip-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/floatbuffer-flip-methods-in-java-with-examples/)

**[java.nio.FloatBuffer 类](https://www.geeksforgeeks.org/tag/java-floatbuffer/)** 的 **flip()** 方法用来翻转这个缓冲区。通过翻转该缓冲区，这意味着缓冲区将被修剪到当前位置，然后该位置将被更改为零。在此过程中，如果缓冲区上有任何标记，则该标记将被自动丢弃。

**语法:**

```java
public final FloatBuffer flip()
```

**返回值:**该方法返回翻转的**浮动缓冲器**实例。

下面是一些示例来说明 flip()方法:

**示例 1:**

```java
// Java program to demonstrate
// flip() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declare and initialize
        // the double array
        float[] db
            = { 10.56f, 20.34f, 30.78f };

        // wrap the float array
        // into FloatBuffer
        // using wrap() method
        FloatBuffer floatBuffer
            = FloatBuffer.wrap(db);

        // set position at index 1
        floatBuffer.position(1);

        // print the buffer
        System.out.println(
            "Buffer before flip: "
            + Arrays.toString(
                  floatBuffer.array())
            + "\nPosition: "
            + floatBuffer.position()
            + "\nLimit: "
            + floatBuffer.limit());

        // Flip the Buffer
        // using flip() method
        floatBuffer.flip();

        // print the buffer
        System.out.println(
            "\nBuffer after flip: "
            + Arrays.toString(
                  floatBuffer.array())
            + "\nPosition: "
            + floatBuffer.position()
            + "\nLimit: "
            + floatBuffer.limit());
    }
}
```

**输出:**

```java
Buffer before flip: [10.56, 20.34, 30.78]
Position: 1
Limit: 3

Buffer after flip: [10.56, 20.34, 30.78]
Position: 0
Limit: 1

```

**示例 2:**

```java
// Java program to demonstrate
// flip() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // defining and allocating FloatBuffer
        // using allocate() method
        FloatBuffer floatBuffer
            = FloatBuffer.allocate(4);

        // put float value in FloatBuffer
        // using put() method
        floatBuffer.put(20.4f);
        floatBuffer.put(34.5f);

        // set position at index 1
        floatBuffer.position(1);

        // print the buffer
        System.out.println(
            "Buffer before flip: "
            + Arrays.toString(
                  floatBuffer.array())
            + "\nPosition: "
            + floatBuffer.position()
            + "\nLimit: "
            + floatBuffer.limit());

        // Flip the Buffer
        // using flip() method
        floatBuffer.flip();

        // print the buffer
        System.out.println(
            "\nBuffer after flip: "
            + Arrays.toString(
                  floatBuffer.array())
            + "\nPosition: "
            + floatBuffer.position()
            + "\nLimit: "
            + floatBuffer.limit());
    }
}
```

**输出:**

```java
Buffer before flip: [20.4, 34.5, 0.0, 0.0]
Position: 1
Limit: 4

Buffer after flip: [20.4, 34.5, 0.0, 0.0]
Position: 0
Limit: 1

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/float buffer . html # flip–](https://docs.oracle.com/javase/9/docs/api/java/nio/FloatBuffer.html#flip--)