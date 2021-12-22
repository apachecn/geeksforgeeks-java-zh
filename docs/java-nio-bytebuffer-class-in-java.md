# java 中的 java.nio.ByteBuffer 类

> 原文:[https://www . geesforgeks . org/Java-nio-bytebuffer-class-in-Java/](https://www.geeksforgeeks.org/java-nio-bytebuffer-class-in-java/)

**字节缓冲区**保存一系列用于输入/输出操作的整数值。**字节缓冲区**类在长缓冲区上提供以下四类操作:

*   读取单个字节的绝对和相对 get 方法。
*   写单字节的绝对和相对 put 方法。
*   相对批量放入和获取方法，用于将连续的字节序列从 int 数组或其他字节缓冲区传输到该缓冲区，并从该缓冲区传输到数组。

短缓冲区可以通过以下方式创建:

*   allocate():这为缓冲区的内容分配空间。
*   wrap():这将现有的长数组包装到缓冲区中。

字节缓冲类的大多数方法都直接类似于字节缓冲定义的方法。

**类别申报:**

> 公共抽象类 ByteBuffer
> 
> 缓冲区扩展
> 
> 可比工具

**CharBuffer 类的方法:**

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| [分配(int 容量)](https://www.geeksforgeeks.org/bytebuffer-allocate-method-in-java-with-examples/) | 这个方法分配一个新的字节缓冲区。 |
| [分配直接(整数容量)](https://www.geeksforgeeks.org/bytebuffer-allocatedirect-method-in-java-with-examples/) | 这个方法分配一个新的直接字节缓冲区。 |
| [数组()](https://www.geeksforgeeks.org/bytebuffer-array-method-in-java-with-examples/) | 此方法返回支持此缓冲区的字节数组 |
| [arrayOffset()](https://www.geeksforgeeks.org/bytebuffer-arrayoffset-method-in-java-with-examples/) | 此方法返回缓冲区第一个元素在该缓冲区后备数组中的偏移量。 |
| [灰分缓冲器()](https://www.geeksforgeeks.org/bytebuffer-ascharbuffer-method-in-java-with-examples/) | 此方法将此字节缓冲区创建为字符缓冲区。 |
| [asDoubleBuffer()](https://www.geeksforgeeks.org/bytebuffer-asdoublebuffer-method-in-java-with-examples/) | 此方法将此字节缓冲区创建为双缓冲区。 |
| [asFloatBuffer()](https://www.geeksforgeeks.org/bytebuffer-asfloatbuffer-method-in-java-with-examples/) | 此方法将此字节缓冲区创建为浮点缓冲区。 |
| asintbuffer() | 此方法将此字节缓冲区创建为 int 缓冲区。 |
| [asongbuffer()](https://www.geeksforgeeks.org/bytebuffer-aslongbuffer-method-in-java-with-examples/) | 此方法将此字节缓冲区创建为长缓冲区。 |
| [ASR onlybbuffer()](https://www.geeksforgeeks.org/bytebuffer-asreadonlybuffer-method-in-java-with-examples/) | 此方法创建一个新的只读字节缓冲区，共享该缓冲区的内容。 |
| [作为短速缓冲器（）](https://www.geeksforgeeks.org/bytebuffer-asshortbuffer-method-in-java-with-examples/) | 此方法将此字节缓冲区创建为短缓冲区。 |
| [紧凑型()](https://www.geeksforgeeks.org/bytebuffer-compact-method-in-java-with-examples/) | 这个方法压缩这个缓冲区。 |
| [比较](https://www.geeksforgeeks.org/bytebuffer-compareto-method-in-java-with-examples/) | 此方法将此缓冲区与另一个缓冲区进行比较。 |
| [重复()](https://www.geeksforgeeks.org/bytebuffer-duplicate-method-in-java-with-examples/) | 此方法创建一个共享缓冲区内容的新字节缓冲区。 |
| [等于(对象 ob)](https://www.geeksforgeeks.org/bytebuffer-equals-method-in-java-with-examples/) | 这个方法告诉这个缓冲区是否等于另一个对象。 |
| [get()](https://www.geeksforgeeks.org/bytebuffer-get-method-in-java-with-examples/) | 此方法是一个相对 get 方法，返回缓冲区当前位置的字节。 |
| [get(byte[] dst)](https://www.geeksforgeeks.org/bytebuffer-get-method-in-java-with-examples/) | 这个方法是一个相对的批量获取方法，并返回这个缓冲区。 |
| [获取(字节[] dst，int 偏移量，int 长度)](https://www.geeksforgeeks.org/bytebuffer-get-method-in-java-with-examples/) | 这个方法是一个相对批量获取方法，并返回这个缓冲区。 |
| [get(int index)](https://www.geeksforgeeks.org/bytebuffer-get-method-in-java-with-examples/) | 该方法是一个绝对获取方法，返回给定索引处的字节。 |
| [getChar()](https://www.geeksforgeeks.org/bytebuffer-getchar-method-in-java-with-examples/) | 此方法是读取字符值的相对获取方法，并返回缓冲区当前位置的字符值。 |
| [getChar(int index)](https://www.geeksforgeeks.org/bytebuffer-getchar-method-in-java-with-examples/) | 此方法是读取字符值的绝对 get 方法，并返回给定索引处的字符值。 |
| [get ul()](https://www.geeksforgeeks.org/bytebuffer-getdouble-method-in-java-with-examples/) | 此方法是读取双精度值的相对 get 方法，并返回缓冲区当前位置的双精度值。 |
| [get ul(int index)](https://www.geeksforgeeks.org/bytebuffer-getdouble-method-in-java-with-examples/) | 此方法是读取双精度值的绝对 get 方法，并返回给定索引处的双精度值。 |
| [getFloat()](https://www.geeksforgeeks.org/bytebuffer-getfloat-method-in-java-with-examples/) | 此方法是读取浮点值的相对获取方法，并返回缓冲区当前位置的浮点值。 |
| [getFloat(int index)](https://www.geeksforgeeks.org/bytebuffer-getfloat-method-in-java-with-examples/) | 此方法是读取浮点值的绝对 get 方法，并返回给定索引处的浮点值。 |
| [getInt()](https://www.geeksforgeeks.org/bytebuffer-getint-method-in-java-with-examples/) | 此方法是读取 int 值的相对 get 方法，并返回缓冲区当前位置的 int 值。 |
| getint(int 指数) | 此方法是读取整数值的绝对 get 方法，并返回给定索引处的整数值。 |
| [getLong()](https://www.geeksforgeeks.org/bytebuffer-getlong-method-in-java-with-examples/) | 此方法是读取长值的相对 get 方法，并返回缓冲区当前位置的长值。 |
| [getLong(int index)](https://www.geeksforgeeks.org/bytebuffer-getlong-method-in-java-with-examples/) | 此方法是读取长值的绝对 get 方法，并返回给定索引处的 int 值。 |
| get hort() | 此方法是读取短值的相对 get 方法，并返回缓冲区当前位置的长值。 |
| [get hort(int index)](https://www.geeksforgeeks.org/bytebuffer-getshort-method-in-java-with-examples/) | 此方法是读取短值的绝对 get 方法，并返回给定索引处的 int 值。 |
| [随机阵列()](https://www.geeksforgeeks.org/bytebuffer-hasarray-method-in-java-with-examples/) | 此方法告知此缓冲区是否由可访问的字节数组支持。 |
| [hashCode()](https://www.geeksforgeeks.org/bytebuffer-hashcode-method-in-java-with-examples/) | 此方法返回此缓冲区的当前哈希代码。 |
| 【t0 isdirect():t1】 | 这个方法告诉这个字节缓冲区是否是直接的。 |
| [订单()](https://www.geeksforgeeks.org/bytebuffer-order-method-in-java-with-examples/) | 此方法检索此缓冲区的字节顺序。 |
| [命令(字节顺序波)](https://www.geeksforgeeks.org/bytebuffer-order-method-in-java-with-examples/) | 这个方法修改这个缓冲区的字节顺序。 |
| [放(字节 b)](https://www.geeksforgeeks.org/bytebuffer-put-methods-in-java-with-examples-set-1/) | 这个方法是一个相对放置方法，返回这个缓冲区。 |
| [put(byte[] src)](https://www.geeksforgeeks.org/bytebuffer-put-methods-in-java-with-examples-set-1/) | 这个方法是一个相对大容量放入方法，并返回这个缓冲区。 |
| [put(ByteBuffer src)](https://www.geeksforgeeks.org/bytebuffer-put-methods-in-java-with-examples-set-1/) | 这个方法是一个相对大容量放入方法，并返回这个缓冲区。 |
| [put(int 索引，字节 b)](https://www.geeksforgeeks.org/bytebuffer-put-methods-in-java-with-examples-set-1/) | 此方法是绝对放入方法，并返回此缓冲区。 |
| [putChar(char value)](https://www.geeksforgeeks.org/bytebuffer-putchar-methods-in-java-with-examples/) | 这个方法是写一个字符值的相对放方法。 |
| [putChar(int 索引，Char 值)](https://www.geeksforgeeks.org/bytebuffer-putchar-methods-in-java-with-examples/) | 此方法是写入字符值的绝对 put 方法。 |
| [放双(双值)](https://www.geeksforgeeks.org/bytebuffer-putdouble-methods-in-java-with-examples/) | 这个方法是写双精度值的相对 put 方法。 |
| [putDouble(int index，double value)](https://www.geeksforgeeks.org/bytebuffer-putdouble-methods-in-java-with-examples/) | 这个方法是写双精度值的绝对 put 方法。 |
| [putFloat(浮点值)](https://www.geeksforgeeks.org/bytebuffer-putfloat-methods-in-java-with-examples/) | 这个方法是写浮点值的相对 put 方法。 |
| [putFloat(int 索引，Float 值)](https://www.geeksforgeeks.org/bytebuffer-putfloat-methods-in-java-with-examples/) | 这个方法是写浮点值的绝对 put 方法。 |
| [putInt(int 值)](https://www.geeksforgeeks.org/bytebuffer-putint-methods-in-java-with-examples/) | 这个方法是写 int 值的相对 put 方法。 |
| [putInt(Int 索引，int 值)](https://www.geeksforgeeks.org/bytebuffer-putint-methods-in-java-with-examples/) | 这个方法是写一个 int 值的绝对 put 方法。 |
| [putLong(int 索引，Long 值)](https://www.geeksforgeeks.org/bytebuffer-putlong-methods-in-java-with-examples/) | 这个方法是写长值的绝对 put 方法。 |
| [putLong(长值)](https://www.geeksforgeeks.org/bytebuffer-putlong-methods-in-java-with-examples/) | 这个方法是写长值的相对 put 方法。 |
| [putShort(int 索引，短值)](https://www.geeksforgeeks.org/bytebuffer-putshort-methods-in-java-with-examples/) | 这个方法是写短值的绝对 put 方法。 |
| [短接(短接值)](https://www.geeksforgeeks.org/bytebuffer-putshort-methods-in-java-with-examples/) | 这个方法是写短值的相对 put 方法。 |
| [切片()](https://www.geeksforgeeks.org/bytebuffer-slice-method-in-java-with-examples/) | 此方法创建一个新的字节缓冲区，其内容是该缓冲区内容的共享子序列。 |
| [toString()](https://www.geeksforgeeks.org/bytebuffer-tostring-method-in-java-with-examples/) | 这个方法返回一个总结这个缓冲区状态的字符串。 |
| [包装(字节[]数组)](https://www.geeksforgeeks.org/bytebuffer-wrap-methods-in-java-with-examples/) | 此方法将字节数组包装到缓冲区中。 |
| [换行(字节[]数组，int 偏移量，int 长度)](https://www.geeksforgeeks.org/bytebuffer-wrap-methods-in-java-with-examples/) | 此方法将字节数组包装到缓冲区中。 |

</figure>

**下面是一些演示 CharBuffer 类及其方法的程序:**

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// ByteBuffer class

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 4;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the int to byte typecast value
            // in ByteBuffer using putInt() method
            bb.put((byte)10);
            bb.put((byte)20);
            bb.put((byte)30);
            bb.put((byte)40);
            bb.rewind();

            // print the ByteBuffer
            System.out.println(
                "Original ByteBuffer: "
                + Arrays.toString(bb.array()));
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

```
Original ByteBuffer: [10, 20, 30, 40]

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// ByteBuffer class

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 50;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // changeing bytebuffer view as char buffer
            // and putting a string value
            bb.asCharBuffer().put("GeeksForGeeks");

            // Declaring char variable c
            char c;

            // print the ByteBuffer
            System.out.print("Char buffer : ");
            while ((c = bb.getChar()) != 0)
                System.out.print(c + " ");
            System.out.println();
        }

        catch (IllegalArgumentException e) {

            System.out.println("Exception thrown : " + e);
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output**

```
Char buffer : G e e k s F o r G e e k s 

```