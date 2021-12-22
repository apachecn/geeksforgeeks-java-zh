# Java 中的缓冲区剩余()方法，示例

> 原文:[https://www . geesforgeks . org/buffer-has resisting-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/buffer-hasremaining-methods-in-java-with-examples/)

**[java.nio.Buffer](https://www.geeksforgeeks.org/tag/java-bytebuffer/)** 类的**has resisting()**方法用来判断当前位置和极限之间是否有元素。

**语法:**

```
public final boolean hasRemaining()
```

**返回:**当且仅当该缓冲区中至少还有一个元素剩余时，该方法将返回 **true** 。

以下是说明**has resisting()**方法的示例:

**示例 1:**

```
// Java program to demonstrate
// hasRemaining() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 10;

        // creating object of bytebuffer
        // and allocating size capacity
        ByteBuffer bb = ByteBuffer.allocate(capacity);

        // putting the value in bytebuffer
        bb.put((byte)10);
        bb.put((byte)20);
        bb.rewind();

        // Typecast bytebuffer to Buffer
        Buffer buffer = (Buffer)bb;

        // checking buffer is backed by array or not
        boolean isRemain = buffer.hasRemaining();

        // checking if else condition
        if (isRemain)
            System.out.println("there is at least one "
                               + "element remaining "
                               + "in this buffer");
        else
            System.out.println("there is no "
                               + "element remaining "
                               + "in this buffer");
    }
}
```

**输出:**

```
there is at least one element remaining in this buffer

```

**示例 2:**

```
// Java program to demonstrate
// hasRemaining() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 0;

        // creating object of bytebuffer
        // and allocating size capacity
        ByteBuffer bb = ByteBuffer.allocate(capacity);

        // Typecast bytebuffer to Buffer
        Buffer buffer = (Buffer)bb;

        // checking buffer is backed by array or not
        boolean isRemain = buffer.hasRemaining();

        // checking if else condition
        if (isRemain)
            System.out.println("there is at least one "
                               + "element remaining"
                               + " in this buffer");
        else
            System.out.println("there is no "
                               + "element remaining"
                               + " in this buffer");
    }
}
```

**输出:**

```
there is no element remaining in this buffer

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/buffer . html # has resisting–](https://docs.oracle.com/javase/9/docs/api/java/nio/Buffer.html#hasRemaining--)