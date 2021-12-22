# Java 中的缓冲容量()方法，示例

> 原文:[https://www . geesforgeks . org/buffer-capacity-in-Java-method-with-examples/](https://www.geeksforgeeks.org/buffer-capacity-method-in-java-with-examples/)

**[java.nio.Buffer 类](https://www.geeksforgeeks.org/tag/java-buffer/)** 的**容量()**方法用于返回该缓冲区的容量。

**语法:**

```
public final int capacity()
```

**返回值:**该缓冲区的容量

以下是说明**容量()**方法的示例:

**示例 1:**

```
// Java program to demonstrate
// capacity() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // creating object of ByteBuffer
        // and allocating size capacity
        ByteBuffer bb = ByteBuffer.allocate(7);

        // putting the int to byte typecast
        // value in ByteBuffer
        bb.put((byte)20);
        bb.put((byte)30);
        bb.put((byte)40);
        bb.put((byte)50);

        // Typecasting ByteBuffer into Buffer
        Buffer bb1 = (Buffer)bb;

        // getting capacity of Buffer
        // using capacity() method
        int cap = bb1.capacity();

        // display the result
        System.out.println("capacity is: "
                           + cap);
    }
}
```

**输出:**

```
capacity is: 7

```

**示例 2:**

```
// Java program to demonstrate
// capacity() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // Declaring and initializing byte array
        byte[] byt = { (byte)20, (byte)30,
                       (byte)40, (byte)50,
                       (byte)60 };

        // creating object of ByteBuffer
        // and allocating size capacity
        ByteBuffer bb = ByteBuffer.wrap(byt);

        // Typecasting ByteBuffer into Buffer
        Buffer bb1 = (Buffer)bb;

        // getting capacity of Buffer
        // using capacity() method
        int cap = bb1.capacity();

        // display the result
        System.out.println("capacity is: "
                           + cap);
    }
}
```

**输出:**

```
capacity is: 5

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/buffer . html # capacity–](https://docs.oracle.com/javase/9/docs/api/java/nio/Buffer.html#capacity--)