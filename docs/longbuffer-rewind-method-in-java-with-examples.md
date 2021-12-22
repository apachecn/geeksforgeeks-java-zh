# Java 中的 LongBuffer rewind()方法，带示例

> 原文:[https://www . geesforgeks . org/longbuffer-rewind-method-in-Java-with-examples/](https://www.geeksforgeeks.org/longbuffer-rewind-method-in-java-with-examples/)

[java.nio.LongBuffer 类](https://www.geeksforgeeks.org/tag/java-longbuffer/)的**倒带()**方法用来倒带这个缓冲区。通过倒带此缓冲区，采取以下操作:

*   The current position is set to zero.
*   The tag is discarded (if any), but the tag value remains unchanged.

**语法:**

```
public LongBuffer rewind()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法在倒带后返回该缓冲区。

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
        // defining and allocating LongBuffer
        // using allocate() method
        LongBuffer longBuffer = LongBuffer.allocate(4);

        // put long value in longBuffer
        // using put() method
        longBuffer.put(10);
        longBuffer.put(20);

        // print the long buffer
        System.out.println(
            "Buffer before operation: "
            + Arrays.toString(
                  longBuffer.array())
            + "\nPosition: "
            + longBuffer.position()
            + "\nLimit: "
            + longBuffer.limit());

        // rewind the Buffer
        // using rewind() method
        longBuffer.rewind();

        // print the longbuffer
        System.out.println(
            "\nBuffer after operation: "
            + Arrays.toString(
                  longBuffer.array())
            + "\nPosition: "
            + longBuffer.position()
            + "\nLimit: "
            + longBuffer.limit());
    }
}
```

**输出:**

```
Buffer before operation: [10, 20, 0, 0]
Position: 2
Limit: 4

Buffer after operation: [10, 20, 0, 0]
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
        // defining and allocating LongBuffer
        // using allocate() method
        LongBuffer longBuffer
            = LongBuffer.allocate(5);

        // put long value in longBuffer
        // using put() method
        longBuffer.put(10);
        longBuffer.put(20);
        longBuffer.put(30);

        // mark will be going to
        // discarded by rewind()
        longBuffer.mark();

        // print the buffer
        System.out.println(
            "Buffer before operation: "
            + Arrays.toString(
                  longBuffer.array())
            + "\nPosition: "
            + longBuffer.position()
            + "\nLimit: "
            + longBuffer.limit());

        // Rewind the Buffer
        // using rewind() method
        longBuffer.rewind();

        // print the buffer
        System.out.println(
            "\nBuffer after operation: "
            + Arrays.toString(
                  longBuffer.array())
            + "\nPosition: "
            + longBuffer.position()
            + "\nLimit: "
            + longBuffer.limit());
    }
}
```

**输出:**

```
Buffer before operation: [10, 20, 30, 0, 0]
Position: 3
Limit: 5

Buffer after operation: [10, 20, 30, 0, 0]
Position: 0
Limit: 5

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/longbuffer . html # mark–](https://docs.oracle.com/javase/9/docs/api/java/nio/LongBuffer.html#mark--)