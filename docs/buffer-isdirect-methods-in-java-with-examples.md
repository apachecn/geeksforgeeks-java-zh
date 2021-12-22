# Java 中的缓冲区是直接()方法，示例

> 原文:[https://www . geesforgeks . org/buffer-is direct-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/buffer-isdirect-methods-in-java-with-examples/)

**[java.nio.Buffer 类](https://www.geeksforgeeks.org/tag/java-bytebuffer/)** 的 **isDirect()** 方法用来判断这个缓冲区是否是直接的。

**语法:**

```
public abstract boolean isDirect()
```

**返回值:**当且仅当该缓冲区是直接的时，该方法返回真。

以下是说明**是直接()**方法的例子:

**示例 1:**

```
// Java program to demonstrate
// isDirect() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating ByteBuffer
        // using allocate() method
        ByteBuffer byteBuffer
            = ByteBuffer.allocateDirect(4);

        // Typecast byteBuffer to buffer
        Buffer buffer = (Buffer)byteBuffer;

        // check the Buffer
        // using isDirect() method
        boolean val = buffer.isDirect();

        // checking the condition
        if (val)
            System.out.println("buffer is direct");
        else
            System.out.println("buffer is not direct");
    }
}
```

**输出:**

```
buffer is direct

```

**示例 2:**

```
// Java program to demonstrate
// isDirect() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {
        // defining and allocating ByteBuffer
        // using allocate() method
        ByteBuffer byteBuffer = ByteBuffer.allocate(4);

        // Typecast byteBuffer to buffer
        Buffer buffer = (Buffer)byteBuffer;

        // check the byteBuffer
        // using isDirect() method
        boolean val = buffer.isDirect();

        // checking the condition
        if (val)
            System.out.println("buffer is direct");
        else
            System.out.println("buffer is not direct");
    }
}
```

**输出:**

```
buffer is not direct

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/buffer . html # isDirect–](https://docs.oracle.com/javase/9/docs/api/java/nio/Buffer.html#isDirect--)