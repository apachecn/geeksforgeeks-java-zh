# Java 中 ByteBuffer hashCode()方法示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-hashcode-method-in-java-with-examples/)

**[Java . nio . bytebuffer](https://www.geeksforgeeks.org/tag/java-bytebuffer/)**类的 **hashCode()** 方法用于返回该缓冲区的当前哈希代码。
一个字节缓冲区的哈希码只取决于它的剩余元素；也就是说，从位置()到极限()1 的元素。
由于缓冲区哈希代码依赖于内容，因此不建议将缓冲区用作哈希映射或类似数据结构中的键，除非知道它们的内容不会改变。

**语法:**

```
public int hashCode()
```

**返回值:**该方法返回该缓冲区的当前哈希码。

下面是一些示例来说明 hashCode()方法:

**实施例 1:**

```
// Java program to demonstrate
// getInt() method

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
        // using getInt() method
        int value = bb.hashCode();

        // print the int value
        System.out.println("\n\nByte Value: " + value);
    }
}
```

**Output:**

```
Original ByteBuffer: 
10 20 30 

Byte Value: -219122491

```

**实施例 2:**

```
// Java program to demonstrate
// getInt() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // creating object of ByteBuffer
        // and allocating size capacity
        ByteBuffer bb = ByteBuffer.allocate(12);

        // Reads the Int at this buffer's current position
        // using getInt() method
        int value = bb.hashCode();

        // print the int value
        System.out.println("Byte Value: " + value);
    }
}
```

**Output:**

```
Byte Value: -293403007

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # hashCode–](https://docs.oracle.com/javase/9/docs/api/java/nio/ByteBuffer.html#hashCode--)