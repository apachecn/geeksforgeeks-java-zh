# Java 中的 ByteBuffer order()方法，带示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-order-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-order-method-in-java-with-examples/)

**order()**

**[Java . nio . bytebuffer](https://www.geeksforgeeks.org/tag/java-bytebuffer/)**类的 **order()** 方法用于检索该缓冲区的字节顺序。读取或写入多字节值时，以及创建作为该字节缓冲区视图的缓冲区时，使用字节顺序。新创建的字节缓冲区的顺序始终是 BIG_ENDIAN。

**语法:**

```
public final ByteOrder order()
```

**返回值:**这个方法返回这个缓冲区的字节顺序。

下面是说明 order()方法的示例:

**实施例 1:**

```
// Java program to demonstrate
// order() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // creating object of ByteBuffer
        // and allocating size capacity
        ByteBuffer bb = ByteBuffer.allocate(12);

        // putting the int value in the bytebuffer
        bb.asIntBuffer()
            .put(10)
            .put(20)
            .put(30);

        // rewind the Bytebuffer
        bb.rewind();

        // print the ByteBuffer
        System.out.println("Original ByteBuffer: ");
        for (int i = 1; i <= 3; i++)
            System.out.print(bb.getInt() + " ");

        // rewind the Bytebuffer
        bb.rewind();

        // Reads the Int at this buffer's current position
        // using order() method
        ByteOrder value = bb.order();

        // print the int value
        System.out.println("\n\nByte Value: " + value);
    }
}
```

**Output:**

```
Original ByteBuffer: 
10 20 30 

Byte Value: BIG_ENDIAN

```

**实施例 2:**

```
// Java program to demonstrate
// order() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // creating object of ByteBuffer
        // and allocating size capacity
        ByteBuffer bb = ByteBuffer.allocate(12);

        // Reads the Int at this buffer's current position
        // using order() method
        ByteOrder value = bb.order();

        // print the int value
        System.out.println("Byte Value: " + value);
    }
}
```

**Output:**

```
Byte Value: BIG_ENDIAN

```

**order(ByteOrder bo)**

ByteBuffer 的 order(ByteOrder bo)方法用于修改该缓冲区的字节顺序。

**语法:**

```
public final ByteBuffer order(ByteOrder bo)
```

**参数:**该方法采用新的字节顺序，可以是 BIG_ENDIAN，也可以是 LITTLE_ENDIAN 作为参数。

**返回值:**这个方法返回这个缓冲区。

以下是说明*顺序(ByteOrder bo)* 方法的示例:

**实施例 1:**

```
// Java program to demonstrate
// order() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // creating object of ByteBuffer
        // and allocating size capacity
        ByteBuffer bb = ByteBuffer.allocate(12);

        // Reads the Int at this buffer's current position
        // using order() method
        ByteOrder oldbyteorder = bb.order();

        // print the result
        System.out.println("Old Byte Order: " + oldbyteorder);

        // Modifies this buffer's byte order
        // by using order() method
        ByteBuffer bb1 = bb.order(ByteOrder.nativeOrder());

        // Reads the Int at this buffer's current position
        // using order() method
        ByteOrder newbyteorder = bb1.order();

        // print the result
        System.out.println("New Byte Order: " + newbyteorder);
    }
}
```

**Output:**

```
Old Byte Order: BIG_ENDIAN
New Byte Order: LITTLE_ENDIAN

```

**实施例 2:**

```
// Java program to demonstrate
// order() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // creating object of ByteBuffer
        // and allocating size capacity
        ByteBuffer bb = ByteBuffer.allocate(12);

        // putting the int value in the bytebuffer
        bb.asIntBuffer()
            .put(10)
            .put(20)
            .put(30);

        // rewind the Bytebuffer
        bb.rewind();

        // print the ByteBuffer
        System.out.println("Original ByteBuffer: ");
        for (int i = 1; i <= 3; i++)
            System.out.print(bb.getInt() + " ");

        // rewind the Bytebuffer
        bb.rewind();

        // Reads the Int at this buffer's current position
        // using order() method
        ByteOrder oldbyteorder = bb.order();

        // print the result
        System.out.println("Old Byte Order: " + oldbyteorder);

        // Modifies this buffer's byte order
        // by using order() method
        ByteBuffer bb1 = bb.order(ByteOrder.nativeOrder());

        // Reads the Int at this buffer's current position
        // using order() method
        ByteOrder newbyteorder = bb1.order();

        // print the result
        System.out.println("New Byte Order: " + newbyteorder);
    }
}
```

**Output:**

```
Original ByteBuffer: 
10 20 30 Old Byte Order: BIG_ENDIAN
New Byte Order: LITTLE_ENDIAN

```

**参考:**

*   [https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # order–](https://docs.oracle.com/javase/9/docs/api/java/nio/ByteBuffer.html#order--)
*   [https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # order-Java . nio . byteorder-](https://docs.oracle.com/javase/9/docs/api/java/nio/ByteBuffer.html#order-java.nio.ByteOrder-)