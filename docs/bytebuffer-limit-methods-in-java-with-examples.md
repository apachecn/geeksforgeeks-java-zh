# Java 中的字节缓冲区限制()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-limit-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-limit-methods-in-java-with-examples/)

[java.nio.ByteBuffer 类](https://www.geeksforgeeks.org/tag/java-bytebuffer/)的 **limit()** 方法用于设置该缓冲区的限制。如果该位置大于新限制，则将其设置为新限制。如果标记已定义并且大于新的限制，则丢弃该标记。

**语法:**

```
public ByteBuffer limit(int newLimit)
```

**返回值:**这个方法返回这个缓冲区。

以下是举例说明 limit()方法的示例:

**示例 1:**

```
// Java program to demonstrate
// compact() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating ByteBuffer
        // using allocate() method
        ByteBuffer byteBuffer = ByteBuffer.allocate(4);

        // put byte value in byteBuffer
        // using put() method
        byteBuffer.put((byte)20);
        byteBuffer.put((byte)30);

        // print the byte buffer
        System.out.println("ByteBuffer before compact: "
                           + Arrays.toString(byteBuffer.array())
                           + "\nPosition: " + byteBuffer.position()
                           + "\nLimit: " + byteBuffer.limit());

        // Limit the byteBuffer
        // using limit() method
        byteBuffer.limit(1);

        // print the byte buffer
        System.out.println("\nByteBuffer after compact: "
                           + Arrays.toString(byteBuffer.array())
                           + "\nPosition: " + byteBuffer.position()
                           + "\nLimit: " + byteBuffer.limit());
    }
}
```

**输出:**

```
ByteBuffer before compact: [20, 30, 0, 0]
Position: 2
Limit: 4

ByteBuffer after compact: [20, 30, 0, 0]
Position: 1
Limit: 1

```

**示例 2:**

```
// Java program to demonstrate
// limit() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating ByteBuffer
        // using allocate() method
        ByteBuffer byteBuffer = ByteBuffer.allocate(5);

        // put byte value in byteBuffer
        // using put() method
        byteBuffer.put((byte)20);
        byteBuffer.put((byte)30);
        byteBuffer.put((byte)40);

        // mark will be going to discarded by limit()
        byteBuffer.mark();

        // print the byte buffer
        System.out.println("ByteBuffer before compact: "
                           + Arrays.toString(byteBuffer.array())
                           + "\nPosition: " + byteBuffer.position()
                           + "\nLimit: " + byteBuffer.limit());

        // Limit the byteBuffer
        // using limit() method
        byteBuffer.limit(4);

        // print the byte buffer
        System.out.println("\nByteBuffer after compact: "
                           + Arrays.toString(byteBuffer.array())
                           + "\nPosition: " + byteBuffer.position()
                           + "\nLimit: " + byteBuffer.limit());
    }
}
```

**输出:**

```
ByteBuffer before compact: [20, 30, 40, 0, 0]
Position: 3
Limit: 5

ByteBuffer after compact: [20, 30, 40, 0, 0]
Position: 3
Limit: 4

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # limit-int-](https://docs.oracle.com/javase/9/docs/api/java/nio/ByteBuffer.html#limit-int-)