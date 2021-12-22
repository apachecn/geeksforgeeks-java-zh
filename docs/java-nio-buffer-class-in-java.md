# java 中的 java.nio.Buffer 类

> 原文:[https://www . geesforgeks . org/Java-nio-buffer-class-in-Java/](https://www.geeksforgeeks.org/java-nio-buffer-class-in-java/)

**缓冲区**类为特定原语类型的数据块提供了一个缓冲区或容器。元素的有限序列线性存储在缓冲器中。

方便在数据中执行读写操作的缓冲区的重要属性有:

*   **[Capacity:** This attribute determines the maximum number of elements that can exist in the buffer.
*   **Limit:** This attribute determines the limit of readable and writable data by providing the index of elements.
*   **Position:** This attribute determines the position of the current element in the buffer.

**语法:**类声明

```java
public abstract class Buffer extends Object
```

Buffer 类为以下每个缓冲区数据类型提供了一个子类，如字节缓冲区、映射字节缓冲区、字符缓冲区、双缓冲区、浮动缓冲区、输入缓冲区、长缓冲区、短缓冲区。Buffer 类从类 java.lang.Object 继承了以下方法，如 clone()、finalize()、getClass()、hashCode()、notifyAll()、toString()、wait()。现在，我们继续讨论 Buffer 类的方法，如下所示，按字母顺序排列，如下所示:

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| 数组() | 此方法返回支持此缓冲区的数组 |
| arrayOffset() | 此方法返回缓冲区的第一个元素 |
| capacity() | 此方法返回此缓冲区的容量。 |
| 清除() | 此方法清除此缓冲区。 |
| 翻转() | 这个方法翻转这个缓冲区。 |
| hasArray() | 这个方法告诉这个缓冲区是否由一个可访问的数组支持。 |
| has resisting() | 这个方法告诉当前位置和极限之间是否有元素。 |
| 是直接() | 这个方法告诉这个缓冲区是否是直接的。 |
| isReadOnly() | 这个方法告诉这个缓冲区是否是只读的。 |
| 限制() | 这个方法返回这个缓冲区的限制。 |
| 限制(int newLimit) | 这个方法设置这个缓冲区的限制。 |
| 标记() | 此方法将此缓冲区的标记设置在其位置。 |
| 位置() | 这个方法返回这个缓冲区的位置。 |
| 位置(int newPosition) | 这个方法设置这个缓冲区的位置。 |
| 剩余() | 此方法返回当前位置与极限之间的元素个数。 |
| reset() | 此方法将此缓冲区的位置重置为之前标记的位置。 |
| 倒带() | 此方法倒带此缓冲区。 |

</figure>

**实现:**缓冲类及其方法

**例 1**

## Java

```java
// Java program to demonstrate Buffer Class

// Importing required libraries
import java.nio.*;
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Declaring the capacity of the ByteBuffer
        int capacity = 5;

        // Try block to check for exceptions
        try {

            // Creating the ByteBuffer

            // Creating object of ByteBuffer class and
            // allocating size capacity
            ByteBuffer bufferObj
                = ByteBuffer.allocate(capacity);

            // Putting the int to byte typecast
            // value in ByteBuffer using put() method

            // Custom input entries
            bufferObj.put((byte)10);
            bufferObj.put((byte)20);
            bufferObj.put((byte)30);
            bufferObj.put((byte)40);
            bufferObj.put((byte)50);

            // Typecasting ByteBuffer into Buffer
            Buffer bufferObj1 = (Buffer)bufferObj;

            // Getting array that backs this buffer
            // using array() method
            byte[] arr = (byte[])bufferObj1.array();

            // Display message only
            System.out.print(" The array is : [");

            // Print the array
            for (int i = 0; i < arr.length; i++)
                System.out.print(" " + arr[i]);
            System.out.print(" ]");
        }

        // Catch block to handle the exception
        catch (ReadOnlyBufferException e) {

            // Print message where exception occurred
            // is displayed on console
            System.out.println("Exception throws: " + e);
        }
    }
}
```

**输出**

```java
 The array is : [ 10 20 30 40 50 ]
```

**例 2**

T5】JavaT0T10**输出**T1