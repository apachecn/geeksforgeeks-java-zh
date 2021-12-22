# java 中的 java.nio.LongBuffer 类

> 原文:[https://www . geesforgeks . org/Java-nio-longbuffer-class-in-Java/](https://www.geeksforgeeks.org/java-nio-longbuffer-class-in-java/)

**长缓冲区**保存一系列长值，用于输入/输出操作。LongBuffer 类在长缓冲区上提供了以下四类操作:

*   绝对和相对读写单长的 get 和 put 方法。
*   相对大容量 get 方法将连续的长序列从这个缓冲区传输到数组中。
*   相对大容量 put 方法，用于将长数组或其他长缓冲区中的连续长序列传输到该缓冲区中。
*   一种压缩长缓冲区的方法。

长缓冲区可以通过以下方式创建:

*   allocate()方法，它为缓冲区的内容分配空间，
*   wrap()方法，它将现有的长数组包装到缓冲区中，或者
*   通过创建现有字节缓冲区的视图。

LongBuffer 类的大多数方法都直接类似于 ByteBuffer 定义的方法。

**语法:**类声明

```
public abstract class LongBuffer
extends Buffer
implements Comparable<LongBuffer>
```

下面列出了 LongBuffer 类的所有方法:

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| 分配(整数容量) | 这个方法分配一个新的长缓冲区。 |
| 数组() | 此方法返回支持此缓冲区的长数组。 |
| arrayOffset() | 此方法返回缓冲区第一个元素在该缓冲区后备数组中的偏移量。 |
| asReadOnlyBuffer() | 此方法创建一个新的只读长缓冲区，共享该缓冲区的内容。 |
| 清除() | 这个方法会清除这个缓冲区。 |
| 紧凑() | 这个方法压缩这个缓冲区。 |
| 比较 | 此方法将此缓冲区与另一个缓冲区进行比较。 |
| 重复() | 此方法创建一个新的长缓冲区，共享该缓冲区的内容。 |
| 等于(对象对象) | 这个方法告诉这个缓冲区是否等于另一个对象。 |
| 翻转() | 这个方法翻转这个缓冲区。 |
| get() | 此方法是一个相对 get 方法，返回缓冲区当前位置的 long。 |
| get (int 索引) | 此方法是绝对 get 方法，并返回给定索引处的 long。 |
| get (long[] dst) | 这个方法是一个相对的批量获取方法，并返回这个缓冲区。 |
| get (long[] dst，int 偏移量，int 长度) | 这个方法是一个相对的批量获取方法，并返回这个缓冲区。 |
| hasArray() | 此方法告诉此缓冲区是否由可访问的长数组支持。 |
| hashCode() | 此方法返回此缓冲区的当前哈希代码。 |
| 间接的 | 这个方法告诉这个长缓冲区是否是直接的。 |
| 极限(整数新极限) | 此方法设置此缓冲区的限制。 |
| 标记() | 此方法将此缓冲区的标记设置在其位置。 |
| 订单() | 此方法检索此缓冲区的字节顺序。 |
| 位置(内部新位置) | 此方法设置该缓冲区的位置。 |
| put(整数索引，长 l) | 此方法是绝对 put 方法，并返回此缓冲区。 |
| 放(长 l) | 这个方法是一个相对 put 方法，返回这个缓冲区。 |
| 看跌期权 | 这个方法是一个相对大容量的 put 方法，并返回这个缓冲区。 |
| put (long[] src，int 偏移量，int 长度) | 这个方法是一个相对大容量的 put 方法，并返回这个缓冲区。 |
| put (LongBuffer src) | 这个方法是一个相对大容量的 put 方法，并返回这个缓冲区。 |
| 重置() | 此方法将此缓冲区的位置重置为先前标记的位置。 |
| 倒带() | 这个方法会倒回这个缓冲区。 |
| 切片() | 此方法创建一个新的长缓冲区，其内容是该缓冲区内容的共享子序列。 |
| toString() | 这个方法返回一个总结这个缓冲区状态的字符串。 |
| 换行(长[]数组) | 此方法将长数组包装到缓冲区中。 |
| 换行(长[]数组，int 偏移量，int 长度) | 此方法将长数组包装到缓冲区中。 |

</figure>

下面是一些演示 LongBuffer 类及其方法的程序:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate LongBuffer class

// Importing input output classes
import java.nio.*;
// Importing all utility classes
import java.util.*;

// Main Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Declaring and initializing variable to
        // the capacity of the LongBuffer
        int capacity = 5;

        // try block to check for exceptions
        try {

            // creating object of Longbuffer
            // and allocating size capacity
            LongBuffer ib = LongBuffer.allocate(capacity);

            // Adding elements to the objects of Longbuffer
            // class
            // using the pur() method
            ib.put(9);
            ib.put(8);
            ib.put(5);
            ib.rewind();

            // print the original LongBuffer
            // using standard toString() method
            System.out.println(
                "Original LongBuffer: "
                + Arrays.toString(ib.array()));

            // Reads the Long at this buffer's current
            // position using get() method
            Long value = ib.get();

            // Print the Long value
            System.out.println("Long Value: " + value);

            // Reads the Long at this buffer's next position
            // using get() method
            Long value1 = ib.get();

            // Agan, now print the Long value
            System.out.print("Next Long Value: " + value1);
        }

        // Catch blocks to handle the exceptions

        // Catch block 1
        catch (IllegalArgumentException e) {

            // Print the message when there is illegal
            // arguments
            System.out.println(
                "IllegalArgumentException catched");
        }

        // Catch block 2
        catch (ReadOnlyBufferException e) {

            // Print statement when an exception is encountered
            System.out.println(
                "ReadOnlyBufferException catched");
        }

        // Catch block 3
        catch (BufferUnderflowException e) {

            // Print statement when an exception is encountered
            System.out.println("Exception throws: " + e);
        }
    }
}
```

**Output**

```
Original LongBuffer: [9, 8, 5, 0, 0]
Long Value: 9
Next Long Value: 8
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate LongBuffer class

// Importing required libraries
import java.nio.*;
import java.util.*;

// Main Class
public class GFG {
    public static void main(String[] args)
    {

        // Declaring and initializing variable to
        // capacity of the LongBuffer
        int Capacity = 10;

        // Creating the LongBuffer

        // creating object of Longbuffer
        // and allocating size capacity
        LongBuffer ib = LongBuffer.allocate(Capacity);

        // Inserting the value in Longbuffer
        // Custom entries
        ib.put(11);
        ib.put(5, 22);

        // Print all the elements inside Longbuffer by
        // use of Arrays.toString() method
        System.out.println("LongBuffer: "
                           + Arrays.toString(ib.array()));
    }
}
```

**Output**

```
LongBuffer: [11, 0, 0, 0, 0, 22, 0, 0, 0, 0]
```