# java 中的 java.nio.DoubleBuffer 类

> 原文:[https://www . geesforgeks . org/Java-nio-double buffer-class-in-Java/](https://www.geeksforgeeks.org/java-nio-doublebuffer-class-in-java/)

**双缓冲区**保存输入/输出操作中使用的一系列双值。DoubleBuffer 类为长缓冲区提供了以下四类操作:

*   读取单倍的绝对和相对 get 方法。
*   写单双精度的绝对和相对 put 方法。
*   相对大容量 put 和 get 方法，用于将连续的 double 序列从 int 数组或其他 double 缓冲区传输到该缓冲区，并从该缓冲区传输到数组。

短缓冲区可以通过以下方式创建:

*   allocate():这为缓冲区的内容分配空间。
*   wrap():这将现有的长数组包装到缓冲区中。

DoubleBuffer 类的大多数方法直接类似于 ByteBuffer 定义的方法。

**类别申报:**

> 公共抽象类 DoubleBuffer
> 
> 缓冲区扩展
> 
> 可比工具

**短缓冲类的方法:**

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| [分配(int 容量)](https://www.geeksforgeeks.org/doublebuffer-allocate-method-in-java-with-examples/) | 这个方法分配一个新的双缓冲区。 |
| [数组()](https://www.geeksforgeeks.org/doublebuffer-array-method-in-java-with-examples/) | 此方法返回支持此缓冲区的双数组。 |
| [arrayOffset()](https://www.geeksforgeeks.org/doublebuffer-arrayoffset-method-in-java-with-examples/) | 此方法返回缓冲区第一个元素在该缓冲区后备数组中的偏移量。 |
| [ASR onlybbuffer()](https://www.geeksforgeeks.org/doublebuffer-asreadonlybuffer-method-in-java-with-examples/) | 此方法创建一个新的只读短缓冲区，共享该缓冲区的内容。 |
| [紧凑型()](https://www.geeksforgeeks.org/doublebuffer-compact-method-in-java-with-examples/) | 这个方法压缩这个缓冲区。 |
| [比较(双缓冲区)](https://www.geeksforgeeks.org/doublebuffer-compareto-method-in-java-with-examples/) | 此方法将此缓冲区与另一个缓冲区进行比较。 |
| [重复()](https://www.geeksforgeeks.org/doublebuffer-duplicate-method-in-java-with-examples/) | 此方法创建一个新的双缓冲区，共享该缓冲区的内容。 |
| [等于(对象 ob)](https://www.geeksforgeeks.org/doublebuffer-equals-method-in-java-with-examples/) | 这个方法告诉这个缓冲区是否等于另一个对象。 |
| [get()](https://www.geeksforgeeks.org/doublebuffer-get-methods-in-java-with-examples/) | 这个方法是一个相对 get 方法，在缓冲区的当前位置返回 double。 |
| [get(double[] dst)](https://www.geeksforgeeks.org/doublebuffer-get-methods-in-java-with-examples/) | 这个方法是一个相对的批量获取方法，并返回这个缓冲区。 |
| [get(double[] dst，int offset，int length)](https://www.geeksforgeeks.org/doublebuffer-get-methods-in-java-with-examples/) | 这个方法是一个相对的批量获取方法和这个缓冲区。 |
| [get(int index)](https://www.geeksforgeeks.org/doublebuffer-get-methods-in-java-with-examples/) | 这个方法是一个绝对的 get 方法和这个缓冲区。 |
| [随机阵列()](https://www.geeksforgeeks.org/doublebuffer-hasarray-method-in-java-with-examples/) | 此方法告知此缓冲区是否由可访问的 int 数组支持。 |
| hashCode() | 此方法返回此缓冲区的当前哈希代码。 |
| isDirect() | 这个方法告诉这个 int 缓冲区是否是直接的。 |
| [订单()](https://www.geeksforgeeks.org/doublebuffer-order-methods-in-java-with-examples/) | 此方法检索此缓冲区的字节顺序。 |
| [放(双 d)](https://www.geeksforgeeks.org/doublebuffer-put-methods-in-java-with-examples-set-1/) | 这个方法是一个相对 put 方法，返回这个缓冲区。 |
| [放(双[] src)](https://www.geeksforgeeks.org/doublebuffer-put-methods-in-java-with-examples-set-1/) | 这个方法是一个相对大容量的 put 方法，并返回这个缓冲区。 |
| [put(double[] src，int offset，int length)](https://www.geeksforgeeks.org/doublebuffer-put-methods-in-java-with-examples-set-1/) | 这个方法是一个相对大容量的 put 方法，并返回这个缓冲区。 |
| [put(DoubleBuffer src)](https://www.geeksforgeeks.org/doublebuffer-put-methods-in-java-with-examples-set-1/) | 这个方法是一个相对大容量的 put 方法，并返回这个缓冲区。 |
| [put(int index，double d)](https://www.geeksforgeeks.org/doublebuffer-put-methods-in-java-with-examples-set-1/) | 此方法是此缓冲区的绝对 put 方法。 |
| [切片()](https://www.geeksforgeeks.org/doublebuffer-slice-method-in-java-with-examples/) | 此方法创建一个新的双缓冲区，其内容是该缓冲区内容的共享子序列。 |
| toString() | 这个方法返回一个总结这个缓冲区状态的字符串。 |
| [包裹(双[]阵列)](https://www.geeksforgeeks.org/doublebuffer-wrap-method-in-java-with-examples/) | 此方法将双数组包装到缓冲区中。 |
| [换行(双[]数组，int 偏移量，int 长度)](https://www.geeksforgeeks.org/doublebuffer-wrap-method-in-java-with-examples/) | 此方法将双数组包装到缓冲区中。 |

</figure>

**下面是一些演示 DoubleBuffer 类及其方法的程序:**

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// DoubleBuffer class

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the DoubleBuffer
        int capacity = 5;

        // Creating the DoubleBuffer

        // creating object of Doublebuffer
        // and allocating size capacity
        DoubleBuffer db = DoubleBuffer.allocate(capacity);

        // putting the value in Doublebuffer
        db.put(9.26F);
        db.put(2, 5.61F);

        System.out.println("DoubleBuffer: "
                           + Arrays.toString(db.array()));
    }
}
```

**Output**

```java
DoubleBuffer: [9.260000228881836, 0.0, 5.610000133514404, 0.0, 0.0]

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// DoubleBuffer class

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaire and initialize the float array
        double[] fbb = { 1.25D, 5.34D, 8.56D };

        // print the float array length
        System.out.println("Array length : " + fbb.length);

        // print the float array element
        System.out.println("\nArray element : "
                           + Arrays.toString(fbb));

        // wrap the float array into floatBuffer
        // using wrap() method
        DoubleBuffer doubleBuffer = DoubleBuffer.wrap(fbb);

        // Rewind the floatbuffer
        doubleBuffer.rewind();

        // print the float buffer
        System.out.println(
            "\ndoubleBuffer : "
            + Arrays.toString(doubleBuffer.array()));

        // print the DoubleBuffer capacity
        System.out.println("\ndoublebuffer capacity : "
                           + doubleBuffer.capacity());

        // print the DoubleBuffer position
        System.out.println("\ndoublebuffer position: "
                           + doubleBuffer.position());
    }
}
```

**Output**

```java
Array length : 3

Array element : [1.25, 5.34, 8.56]

doubleBuffer : [1.25, 5.34, 8.56]

doublebuffer capacity : 3

doublebuffer position: 0

```