# Java 中的 FloatBuffer rewind()方法，示例

> 原文:[https://www . geeksforgeeks . org/float buffer-rewind-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/floatbuffer-rewind-methods-in-java-with-examples/)

[java.nio.FloatBuffer 类](https://www.geeksforgeeks.org/tag/java-floatbuffer/)的**倒带()**方法用来倒带这个缓冲区。此方法将位置设置为零，限制保持不变，如果有任何先前标记的位置，将被丢弃。当需要进行通道写或获取操作时，应调用此方法。这意味着，如果缓冲区数据已经写入，则需要将其复制到另一个数组中。例如:

```

out.write(buf);   // Writes the remaining data
buf.rewind();     // Rewind the buffer
buf.get(array);   // Copy data into array

```

**语法:**

```
public final FloatBuffer rewind()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回该缓冲区。

以下是说明 rewind()方法的示例:

**示例 1:**

```
// Java program to demonstrate
// rewind() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating FloatBuffer
        // using allocate() method
        FloatBuffer floatBuffer = FloatBuffer.allocate(4);

        // put char value in FloatBuffer
        // using put() method
        floatBuffer.put(10.5f);
        floatBuffer.put(20.5f);

        // print the float buffer
        System.out.println("Buffer before operation: "
                           + Arrays.toString(
                                 floatBuffer.array())
                           + "\nPosition: "
                           + floatBuffer.position()
                           + "\nLimit: "
                           + floatBuffer.limit());

        // rewind the Buffer
        // using rewind() method
        floatBuffer.rewind();

        // print the floatbuffer
        System.out.println("\nBuffer after operation: "
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

```
Buffer before operation: [10.5, 20.5, 0.0, 0.0]
Position: 2
Limit: 4

Buffer after operation: [10.5, 20.5, 0.0, 0.0]
Position: 0
Limit: 4

```

**示例 2:**

```
// Java program to demonstrate
// rewind() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating FloatBuffer
        // using allocate() method
        FloatBuffer floatBuffer
            = FloatBuffer.allocate(5);

        // put float value in floatBuffer
        // using put() method
        floatBuffer.put(10.5f);
        floatBuffer.put(20.5f);
        floatBuffer.put(30.5f);

        // mark will be going to discarded by rewind()
        floatBuffer.mark();

        // print the buffer
        System.out.println("Buffer before operation: "
                           + Arrays.toString(
                                 floatBuffer.array())
                           + "\nPosition: "
                           + floatBuffer.position()
                           + "\nLimit: "
                           + floatBuffer.limit());

        // Rewind the Buffer
        // using rewind() method
        floatBuffer.rewind();

        // print the buffer
        System.out.println("\nBuffer after operation: "
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

```
Buffer before operation: [10.5, 20.5, 30.5, 0.0, 0.0]
Position: 3
Limit: 5

Buffer after operation: [10.5, 20.5, 30.5, 0.0, 0.0]
Position: 0
Limit: 5

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/float buffer . html # rewind–](https://docs.oracle.com/javase/9/docs/api/java/nio/FloatBuffer.html#rewind--)