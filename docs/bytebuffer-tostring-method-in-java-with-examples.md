# Java 中的 ByteBuffer toString()方法，带示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-tostring-method-in-java-with-examples/)

**字节缓冲类**的 **toString()** 方法是用于返回表示字节缓冲对象包含的数据的字符串的内置方法。创建并初始化一个新的字符串对象，从这个字节缓冲对象中获取字符序列，然后由 toString()返回字符串。对象包含的对该序列的后续更改不会影响字符串的内容。
**语法:**

```
public abstract String toString()
```

**返回值:**这个方法返回**字符串**，代表 ByteBuffer 对象包含的数据。
下面的程序说明了 ByteBuffer.toString()方法:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// toString() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 5;

        // creating object of ByteBuffer
        // and allocating size capacity
        ByteBuffer bb1 = ByteBuffer.allocate(capacity);

        // putting the value in ByteBuffer
        bb1.put((byte)10);
        bb1.put((byte)20);

        // print the ByteBuffer
        System.out.println("Original ByteBuffer: "
                           + Arrays.toString(bb1.array()));

        // Creating a shared subsequence buffer of given ByteBuffer
        // using toString() method
        String value = bb1.toString();

        // print the ByteBuffer
        System.out.println("\nstring representation of ByteBuffer:  "
                           + value);
    }
}
```

**Output:** 

```
Original ByteBuffer: [10, 20, 0, 0, 0]

string representation of ByteBuffer:  java.nio.HeapByteBuffer[pos=2 lim=5 cap=5]
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// toString() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 4;

        // creating object of ByteBuffer
        // and allocating size capacity
        ByteBuffer bb1 = ByteBuffer.allocate(capacity);

        // putting the value in ByteBuffer
        bb1.put((byte)10)
            .put((byte)20)
            .put((byte)30)
            .put((byte)40);

        // print the ByteBuffer
        System.out.println("Original ByteBuffer: "
                           + Arrays.toString(bb1.array()));

        // Creating a shared subsequence buffer of given ByteBuffer
        // using toString() method
        String value = bb1.toString();

        // print the ByteBuffer
        System.out.println("\nstring representation of ByteBuffer:  "
                           + value);
    }
}
```

**Output:** 

```
Original ByteBuffer: [10, 20, 30, 40]

string representation of ByteBuffer:  java.nio.HeapByteBuffer[pos=4 lim=4 cap=4]
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # toString–T4】