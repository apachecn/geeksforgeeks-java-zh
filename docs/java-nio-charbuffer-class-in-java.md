# java 中的 java.nio.CharBuffer 类

> 原文:[https://www . geesforgeks . org/Java-nio-charbuffer-class-in-Java/](https://www.geeksforgeeks.org/java-nio-charbuffer-class-in-java/)

**字符缓冲区**保存输入/输出操作中使用的整数值序列。 **CharBuffer** 类在长缓冲区上提供以下四类操作:

*   读取单个字符的绝对和相对获取方法。
*   写单个字符的绝对和相对 put 方法。
*   相对大容量放入和获取方法，用于将连续的字符序列从 int 数组或其他字符缓冲区传输到该缓冲区，并从该缓冲区传输到数组。

短缓冲区可以通过以下方式创建:

*   allocate():这为缓冲区的内容分配空间。
*   wrap():这将现有的长数组包装到缓冲区中。

CharBuffer 类的大多数方法直接类似于 ByteBuffer 定义的方法。

**类别申报:**

> 公共抽象类 CharBuffer
> 
> 缓冲区扩展
> 
> 实现可比较的<charbuffer>，可追加，字符序列，可读</charbuffer>

**CharBuffer 类的方法:**

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| 分配(整数容量) | 此方法分配一个新的字符缓冲区。 |
| [追加(char c)](https://www.geeksforgeeks.org/charbuffer-append-methods-in-java-with-examples/) | 此方法将指定的字符追加到此缓冲区。 |
| 附录(CharSequence csq) | 此方法将指定的字符序列追加到此缓冲区。 |
| [附录(CharSequence csq，int start，int end)](https://www.geeksforgeeks.org/charbuffer-append-methods-in-java-with-examples/) | 此方法将指定字符序列的子序列追加到此缓冲区 |
| [数组()](https://www.geeksforgeeks.org/charbuffer-array-method-in-java/) | 此方法返回支持此缓冲区的 char 数组 |
| [arrayOffset()](https://www.geeksforgeeks.org/charbuffer-arrayoffset-method-in-java/) | 此方法返回缓冲区第一个元素在该缓冲区后备数组中的偏移量 |
| [ASR onlybbuffer()](https://www.geeksforgeeks.org/charbuffer-asreadonlybuffer-method-in-java/) | 此方法创建一个新的只读字符缓冲区，共享该缓冲区的内容。 |
| [charAt(int index)](https://www.geeksforgeeks.org/charbuffer-charat-methods-in-java-with-examples/) | 此方法读取相对于当前位置的给定索引处的字符。 |
| [紧凑型()](https://www.geeksforgeeks.org/charbuffer-compact-method-in-java/) | 这个方法压缩这个缓冲区 |
| [比较(字符缓冲区)](https://www.geeksforgeeks.org/charbuffer-compareto-method-in-java/) | 此方法将此缓冲区与另一个缓冲区进行比较。 |
| 重复() | 此方法创建一个新的字符缓冲区，共享该缓冲区的内容。 |
| [等于(对象 ob)](https://www.geeksforgeeks.org/charbuffer-equals-method-in-java/) | 这个方法告诉这个缓冲区是否等于另一个对象。 |
| [get()](https://www.geeksforgeeks.org/charbuffer-get-methods-in-java/) | 此方法是一个相对 get 方法，返回 |
| 获取(char[] dst) | 此方法是相对批量获取方法，并返回 |
| [get(char[] dst，int offset，int length)](https://www.geeksforgeeks.org/charbuffer-get-methods-in-java/) | 此方法是相对批量获取方法，并返回 |
| [get(int index)](https://www.geeksforgeeks.org/charbuffer-get-methods-in-java/) | 此方法是绝对 get 方法，并返回 |
| [随机阵列()](https://www.geeksforgeeks.org/charbuffer-hasarray-method-in-java/) | 此方法告知此缓冲区是否由可访问的字符数组支持。 |
| hashCode() | 此方法返回此缓冲区的当前哈希代码。 |
| isDirect() | 这个方法告诉这个字符缓冲区是否是直接的。 |
| [长度()](https://www.geeksforgeeks.org/charbuffer-length-methods-in-java-with-examples/) | 这个方法返回这个字符缓冲区的长度。 |
| [订单()](https://www.geeksforgeeks.org/charbuffer-order-methods-in-java-with-examples/) | 此方法检索此缓冲区的字节顺序。 |
| [放(炭 c)](https://www.geeksforgeeks.org/charbuffer-put-methods-in-java/) | 此方法是一个相对的 put 方法，返回 |
| [放(char[] src)](https://www.geeksforgeeks.org/charbuffer-put-methods-in-java/) | 此方法是相对大容量的 put 方法，并返回 |
| [put(char[] src，int 偏移量，int 长度)](https://www.geeksforgeeks.org/charbuffer-put-methods-in-java/) | 此方法是相对大容量的 put 方法，并返回 |
| [放(CharBuffer src)](https://www.geeksforgeeks.org/charbuffer-put-methods-in-java/) | 此方法是相对大容量的 put 方法，并返回 |
| [put(int index，char c)](https://www.geeksforgeeks.org/charbuffer-put-methods-in-java/) | 此方法是绝对看跌方法，并返回 |
| [放(串 src)](https://www.geeksforgeeks.org/charbuffer-put-methods-in-java/) | 此方法是相对大容量的 put 方法，并返回 |
| [放(字符串 src，int 开始，int 结束)](https://www.geeksforgeeks.org/charbuffer-put-methods-in-java/) | 此方法是相对大容量的 put 方法，并返回 |
| [读取(CharBuffer 目标)](https://www.geeksforgeeks.org/charbuffer-read-methods-in-java-with-examples/) | 此方法尝试将字符读入指定的字符缓冲区。 |
| [切片()](https://www.geeksforgeeks.org/charbuffer-slice-method-in-java/) | 此方法创建一个新的字符缓冲区，其内容是该缓冲区内容的共享子序列。 |
| [子序列(int 开始，int 结束)](https://www.geeksforgeeks.org/charbuffer-subsequence-methods-in-java-with-examples/) | 此方法创建一个新的字符缓冲区，表示相对于当前位置的该缓冲区的指定子序列。 |
| toString() | 此方法返回包含此缓冲区中字符的字符串。 |
| [包装(char[]数组)](https://www.geeksforgeeks.org/charbuffer-wrap-method-in-java/) | 此方法将字符数组包装到缓冲区中。 |
| [换行(char[]数组，int 偏移量，int 长度)](https://www.geeksforgeeks.org/charbuffer-wrap-method-in-java/) | 此方法将字符数组包装到缓冲区中。 |
| [环绕(CharSequence csq)](https://www.geeksforgeeks.org/charbuffer-wrap-method-in-java/) | 此方法将字符序列包装到缓冲区中。 |
| [换行(CharSequence csq，int start，int end)](https://www.geeksforgeeks.org/charbuffer-wrap-method-in-java/) | 此方法将字符序列包装到缓冲区中。 |

</figure>

**下面是一些演示 CharBuffer 类及其方法的程序:**

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// CharBuffer class

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the CharBuffer
        char capacity = 10;

        // Creating the CharBuffer

        // creating object of Charbuffer
        // and allocating size capacity
        CharBuffer fb = CharBuffer.allocate(capacity);

        // putting the value in charbuffer
        fb.put('a');
        fb.put(5, 'b');
          fb.put(7, 'c');

        // Printing the CharBuffer
        System.out.println("ChartBuffer: "
                        + Arrays.toString(fb.array()));
    }
}
```

**输出:**

```
ChartBuffer: [a, , , , , b, , c, , ]
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// CharBuffer class

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the CharBuffer
        int capacity = 4;

        // Creating the CharBuffer
        try {

            // creating object of CharBuffer
            // and allocating size capacity
            CharBuffer charbuffer
                = CharBuffer.allocate(capacity);

            // append the value in CharBuffer
            // using append() method
            charbuffer.append('a')
                .append('b')
                .append('c')
                  .append('d')
                .rewind();

            // print the CharBuffer
            System.out.println("Original CharBuffer: "
                            + Arrays.toString(
                                    charbuffer.array()));
        }

        catch (BufferOverflowException e) {

            System.out.println("Exception throws : " + e);
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("Exception throws : " + e);
        }
    }
}
```

**输出:**

```
Original CharBuffer: [a, b, c, d]
```