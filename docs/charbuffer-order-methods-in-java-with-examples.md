# Java 中的 CharBuffer order()方法，示例

> 原文:[https://www . geesforgeks . org/char buffer-order-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/charbuffer-order-methods-in-java-with-examples/)

[**Java . nio . charbuffer**](https://www.geeksforgeeks.org/tag/java-charbuffer/)类的 **order()** 方法用于检索该缓冲区的字节顺序。通过分配或包装现有字符数组创建的字符缓冲区的字节顺序是底层硬件的本机顺序。作为字节缓冲区视图创建的字符缓冲区的字节顺序是创建视图时字节缓冲区的字节顺序。
**语法:**

```
public abstract ByteOrder order()
```

**返回值:**这个方法返回这个缓冲区的字节顺序。
以下是举例说明 order()方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// order() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // creating object of CharBuffer
        // and allocating size capacity
        CharBuffer cb
            = CharBuffer.allocate(4);

        // append the int value in the charbuffer
        cb.append('a')
            .append('b')
            .append('c')
            .append('d');

        // rewind the Bytebuffer
        cb.rewind();

        // Retrieve the ByteOrder
        // using order() method
        ByteOrder order = cb.order();

        // print the char buffer and order
        System.out.println("CharBuffer is : "
                           + Arrays.toString(cb.array())
                           + "\nOrder: " + order);
    }
}
```

**Output:** 

```
CharBuffer is : [a, b, c, d]
Order: LITTLE_ENDIAN
```

**实施例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// order() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // creating object of CharBuffer
        // and allocating size capacity
        CharBuffer cb = CharBuffer.allocate(4);

        // Retrieve the ByteOrder
        // using order() method
        ByteOrder order = cb.order();

        // print the char buffer and order
        System.out.println("CharBuffer is : "
                           + Arrays.toString(cb.array())
                           + "\nOrder: " + order);
    }
}
```

**Output:** 

```
CharBuffer is : [,,,  ]
Order: LITTLE_ENDIAN
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charbuffer . html # order–](https://docs.oracle.com/javase/9/docs/api/java/nio/CharBuffer.html#order--)