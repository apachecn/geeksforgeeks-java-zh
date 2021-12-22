# java 中的 java.nio.ShortBuffer 类

> 原文:[https://www . geesforgeks . org/Java-nio-short buffer-class-in-Java/](https://www.geeksforgeeks.org/java-nio-shortbuffer-class-in-java/)

**短缓冲区**保存输入/输出操作中使用的整数值序列。**短缓冲区**类对长缓冲区提供以下四类操作:

*   读取单个短裤的绝对和相对获取方法。
*   写单个短裤的绝对和相对看跌方法。
*   相对批量放入和获取方法，用于将连续的短序列从 int 数组或其他短缓冲区传输到该缓冲区，并从该缓冲区传输到数组。

短缓冲区可以通过以下方式创建:

*   allocate():这为缓冲区的内容分配空间。
*   wrap():这将现有的长数组包装到缓冲区中。

ShortBuffer 类的大多数方法都直接类似于 ByteBuffer 定义的方法。

**类别申报:**

> 公共抽象类 ShortBuffer
> 
> 缓冲区扩展
> 
> 可比工具

**短缓冲类的方法:**

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| [分配(int 容量)](https://www.geeksforgeeks.org/shortbuffer-allocate-method-in-java-with-examples/) | 这个方法分配一个新的短缓冲区。 |
| [数组()](https://www.geeksforgeeks.org/shortbuffer-array-method-in-java-with-examples/) | 此方法返回支持此缓冲区的短数组。 |
| [arrayOffset()](https://www.geeksforgeeks.org/shortbuffer-arrayoffset-method-in-java-with-examples/) | 此方法返回缓冲区第一个元素在该缓冲区后备数组中的偏移量。 |
| [ASR onlybbuffer()](https://www.geeksforgeeks.org/shortbuffer-asreadonlybuffer-method-in-java-with-examples/) | 此方法创建一个新的只读短缓冲区，共享该缓冲区的内容。 |
| [紧凑型()](https://www.geeksforgeeks.org/shortbuffer-compact-method-in-java-with-examples/) | 这个方法压缩这个缓冲区。 |
| [比较(短缓冲区)](https://www.geeksforgeeks.org/shortbuffer-compareto-method-in-java-with-examples/) | 此方法将此缓冲区与另一个缓冲区进行比较。 |
| [重复()](https://www.geeksforgeeks.org/shortbuffer-duplicate-method-in-java-with-examples/) | 此方法创建一个新的短缓冲区，共享该缓冲区的内容。 |
| [等于(对象 ob)](https://www.geeksforgeeks.org/shortbuffer-equals-method-in-java-with-examples/) | 这个方法告诉这个缓冲区是否等于另一个对象。 |
| get() | 此方法是一个相对 get 方法，返回缓冲区当前位置的 short。 |
| get(int 索引) | 此方法是绝对 get 方法，并返回给定索引处的 short。 |
| get(int[] dst) | 这个方法是一个相对的批量获取方法，并返回这个缓冲区。 |
| get(int[] dst，int 偏移量，int 长度) | 此方法相对于批量获取方法，并返回此缓冲区。 |
| [随机阵列()](https://www.geeksforgeeks.org/shortbuffer-hasarray-method-in-java-with-examples/) | 此方法告知此缓冲区是否由可访问的 int 数组支持。 |
| 【t0 isdirect():t1】 | 这个方法告诉这个 int 缓冲区是否是直接的。 |
| [订单()](https://www.geeksforgeeks.org/shortbuffer-order-method-in-java-with-examples/) | 此方法检索此缓冲区的字节顺序。 |
| [看跌(int index，short s)](https://www.geeksforgeeks.org/shortbuffer-putint-short-method-in-java-with-examples/) | 此方法是绝对 put 方法，并返回此缓冲区。 |
| 做空 | 这个方法是一个相对 put 方法，返回这个缓冲区。 |
| 看跌期权 | 这个方法是一个相对大容量的 put 方法，并返回这个缓冲区。 |
| put(短[] src，int 偏移量，int 长度) | 这个方法是一个相对大容量的 put 方法，并返回这个缓冲区。 |
| put(短缓冲 src) | 这个方法是一个相对大容量的 put 方法，并返回这个缓冲区。 |
| [切片()](https://www.geeksforgeeks.org/shortbuffer-slice-method-in-java-with-examples/) | 此方法创建一个新的短缓冲区，其内容是该缓冲区内容的共享子序列。 |
| [toString()](https://www.geeksforgeeks.org/shortbuffer-tostring-method-in-java-with-examples/) | 这个方法返回一个总结这个缓冲区状态的字符串。 |
| 换行(短[]数组) | 此方法将短数组包装到缓冲区中。 |
| 换行(短[]数组，int 偏移量，int 长度) | 此方法将短数组包装到缓冲区中。 |

</figure>

**下面是一些演示 ShortBuffer 类及其方法的程序:**

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// ShortBuffer class

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the ShortBuffer
        int capacity = 10;

        // Creating the ShortBuffer
        try {

            // creating object of Shortbuffer
            // and allocating size capacity
            ShortBuffer sb = ShortBuffer.allocate(capacity);

            // putting the value in Shortbuffer
            sb.put((short)100);
            sb.put(2, (short)9);
            sb.rewind();

            // getting array from fb ShortBuffer using
            // array() method
            short[] sbb = sb.array();

            // printing the ShortBuffer fb
            System.out.println("ShortBuffer: "
                               + Arrays.toString(sbb));
        }

        catch (IllegalArgumentException e) {

            System.out.println(
                "IllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {

            System.out.println(
                "ReadOnlyBufferException catched");
        }
    }
}
```

**Output**

```java
ShortBuffer: [100, 0, 9, 0, 0, 0, 0, 0, 0, 0]
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// ShortBuffer class

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ShortBuffer 1
        int capacity1 = 10;

        // Declaring the capacity of the ShortBuffer 2
        int capacity2 = 10;

        // Creating the ShortBuffer
        try {

            // creating object of Shortbuffer 1
            // and allocating size capacity
            ShortBuffer sb1
                = ShortBuffer.allocate(capacity1);

            // creating object of Shortbuffer 2
            // and allocating size capacity
            ShortBuffer fb2
                = ShortBuffer.allocate(capacity2);

            // putting the value in Shortbuffer 1
            sb1.put((short)100);
            sb1.put(2, (short)9);
            sb1.rewind();

            // putting the value in Shortbuffer 2
            fb2.put((short)100);
            fb2.put(2, (short)9);
            fb2.rewind();

            // print the ShortBuffer 1
            System.out.println(
                "ShortBuffer 1: "
                + Arrays.toString(sb1.array()));

            // print the ShortBuffer 2
            System.out.println(
                "ShortBuffer 2: "
                + Arrays.toString(fb2.array()));

            // checking the equality of both ShortBuffer
            boolean fbb = sb1.equals(fb2);

            // checking if else condition
            if (fbb)
                System.out.println("both are equal");
            else
                System.out.println("both are not equal");
        }

        catch (IllegalArgumentException e) {
            System.out.println(
                "IllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {
            System.out.println(
                "ReadOnlyBufferException catched");
        }
    }
}
```

**Output**

```java
ShortBuffer 1: [100, 0, 9, 0, 0, 0, 0, 0, 0, 0]
ShortBuffer 2: [100, 0, 9, 0, 0, 0, 0, 0, 0, 0]
both are equal
```