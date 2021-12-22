# Java 中的缓冲区限制()方法，示例

> 原文:[https://www . geesforgeks . org/buffer-limit-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/buffer-limit-methods-in-java-with-examples/)

[java.nio.Buffer 类](https://www.geeksforgeeks.org/tag/java-bytebuffer/)的 **limit()** 方法用于设置该缓冲区的限制。如果该位置大于新限制，则将其设置为新限制。如果标记已定义并且大于新的限制，则丢弃该标记。

**语法:**

```java
public Buffer limit(int newLimit)
```

**返回值:**这个方法返回这个缓冲区。

以下是举例说明 limit()方法的示例:

**示例 1:**

```java
// Java program to demonstrate
// limit() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating ByteBuffer
        // using allocate() method
        ByteBuffer byteBuffer
            = ByteBuffer.allocate(4);

        // put byte value in byteBuffer
        // using put() method
        byteBuffer.put((byte)20);
        byteBuffer.put((byte)30);

        // Typecast byteBuffer to buffer
        Buffer buffer = (Buffer)byteBuffer;

        // print the byte buffer
        System.out.println("Buffer before operation: "
                           + Arrays.toString(
                                 (byte[])buffer.array())
                           + "\nPosition: "
                           + buffer.position()
                           + "\nLimit: "
                           + buffer.limit());

        // Limit the Buffer
        // using limit() method
        buffer.limit(1);

        // print the buffer
        System.out.println("\nBuffer after operation: "
                           + Arrays.toString(
                                 (byte[])buffer.array())
                           + "\nPosition: "
                           + buffer.position()
                           + "\nLimit: "
                           + buffer.limit());
    }
}
```

**输出:**

```java
Buffer before operation: [20, 30, 0, 0]
Position: 2
Limit: 4

Buffer after operation: [20, 30, 0, 0]
Position: 1
Limit: 1

```

**示例 2:**

```java
// Java program to demonstrate
// limit() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating ByteBuffer
        // using allocate() method
        ByteBuffer byteBuffer
            = ByteBuffer.allocate(5);

        // put byte value in byteBuffer
        // using put() method
        byteBuffer.put((byte)20);
        byteBuffer.put((byte)30);
        byteBuffer.put((byte)40);

        // Typecast byteBuffer to buffer
        Buffer buffer = (Buffer)byteBuffer;

        // mark will be going to discarded by limit()
        buffer.mark();

        // print the buffer
        System.out.println("Buffer before operation: "
                           + Arrays.toString(
                                 (byte[])buffer.array())
                           + "\nPosition: "
                           + buffer.position()
                           + "\nLimit: "
                           + buffer.limit());

        // Limit the Buffer
        // using limit() method
        buffer.limit(4);

        // print the buffer
        System.out.println("\nBuffer after operation: "
                           + Arrays.toString(
                                 (byte[])buffer.array())
                           + "\nPosition: "
                           + buffer.position()
                           + "\nLimit: "
                           + buffer.limit());
    }
}
```

**输出:**

```java
Buffer before operation: [20, 30, 40, 0, 0]
Position: 3
Limit: 5

Buffer after operation: [20, 30, 40, 0, 0]
Position: 3
Limit: 4

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/buffer . html # limit-int-](https://docs.oracle.com/javase/9/docs/api/java/nio/Buffer.html#limit-int-)