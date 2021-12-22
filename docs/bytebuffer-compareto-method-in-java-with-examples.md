# Java 中的字节缓冲比较()方法，带示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-compareto-method-in-java-with-examples/)

**java.nio.ByteBuffer** 类的 **compareTo()** 方法用于比较一个缓冲区和另一个缓冲区。
两个字节缓冲区的比较是通过按字典顺序比较剩余元素的序列来进行的，而不考虑每个序列在其相应缓冲区内的起始位置。像调用 Byte.compare(byte，byte)一样对字节元素对进行比较。
字节缓冲区无法与任何其他类型的对象相比。
**语法:**

```java
public int compareTo(ByteBuffer that)
```

**参数:**该方法将一个 ByteBuffer 对象作为参数，与该缓冲区进行比较。
**返回值:**该方法返回负整数、零或正整数，因为该缓冲区小于、等于或大于给定的缓冲区。
以下是说明 *compareTo()* 方法的示例:
**示例 1:** 当两个字节缓冲区相等时。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// compareTo() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the bb
        int capacity1 = 3;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer bb
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity1);

            // putting the byte to int typecast value in bb
            bb.put((byte)20);
            bb.put((byte)30);
            bb.put((byte)40);

            // rewind the  ByteBuffer
            bb.rewind();

            // print the  ByteBuffer
            System.out.println("ByteBuffer bb: "
                               + Arrays.toString(bb.array()));

            // creating object of  ByteBuffer bb1
            // and allocating size capacity
            ByteBuffer bb1 = ByteBuffer.allocate(capacity1);

            // putting the value in fb1
            bb1.put((byte)20);
            bb1.put((byte)30);
            bb1.put((byte)40);

            // rewind the ByteBuffer
            bb1.rewind();

            // print the ByteBuffer
            System.out.println("ByteBuffer bb1: "
                               + Arrays.toString(bb1.array()));

            // compare both buffer and store the value into integer
            int i = bb.compareTo(bb1);

            // if else condition
            if (i == 0)
                System.out.println("\nboth buffer are lexicographically equal");
            else if (i >= 0)
                System.out.println("\nbb is lexicographically greater than bb1");
            else
                System.out.println("\nbb is lexicographically less than bb1");
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception throws : " + e);
        }

        catch (ReadOnlyBufferException e) {
            System.out.println("Exception throws : " + e);
        }
    }
}
```

**Output:** 

```java
ByteBuffer bb: [20, 30, 40]
ByteBuffer bb1: [20, 30, 40]

both buffer are lexicographically equal
```

**示例 2:** 当该字节缓冲区大于传递的字节缓冲区时

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// compareTo() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the bb
        int capacity1 = 3;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer bb
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity1);

            // putting the byte to int typecast value in bb
            bb.put((byte)30);
            bb.put((byte)30);
            bb.put((byte)40);

            // rewind the  ByteBuffer
            bb.rewind();

            // print the  ByteBuffer
            System.out.println("ByteBuffer bb: "
                               + Arrays.toString(bb.array()));

            // creating object of  ByteBuffer bb1
            // and allocating size capacity
            ByteBuffer bb1 = ByteBuffer.allocate(capacity1);

            // putting the value in bb1
            bb1.put((byte)20);
            bb1.put((byte)30);
            bb1.put((byte)40);

            // rewind the ByteBuffer
            bb1.rewind();

            // print the ByteBuffer
            System.out.println("ByteBuffer bb1: "
                               + Arrays.toString(bb1.array()));

            // compare both buffer and store the value into integer
            int i = bb.compareTo(bb1);

            // if else condition
            if (i == 0)
                System.out.println("\nboth buffer are lexicographically equal");
            else if (i >= 0)
                System.out.println("\nbb is lexicographically greater than bb1");
            else
                System.out.println("\nbb is lexicographically less than bb1");
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception throws : " + e);
        }

        catch (ReadOnlyBufferException e) {
            System.out.println("Exception throws : " + e);
        }
    }
}
```

**Output:** 

```java
ByteBuffer bb: [30, 30, 40]
ByteBuffer bb1: [20, 30, 40]

bb is lexicographically greater than bb1
```

**示例 3:** 当该字节缓冲区小于传递的字节缓冲区时

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// compareTo() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the bb
        int capacity1 = 3;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer bb
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity1);

            // putting the byte to int typecast value in bb
            bb.put((byte)20);
            bb.put((byte)30);
            bb.put((byte)40);

            // rewind the  ByteBuffer
            bb.rewind();

            // print the  ByteBuffer
            System.out.println("ByteBuffer bb: "
                               + Arrays.toString(bb.array()));

            // creating object of  ByteBuffer bb1
            // and allocating size capacity
            ByteBuffer bb1 = ByteBuffer.allocate(capacity1);

            // putting the value in fb1
            bb1.put((byte)40);
            bb1.put((byte)30);
            bb1.put((byte)40);

            // rewind the ByteBuffer
            bb1.rewind();

            // print the ByteBuffer
            System.out.println("ByteBuffer bb1: "
                               + Arrays.toString(bb1.array()));

            // compare both buffer and store the value into integer
            int i = bb.compareTo(bb1);

            // if else condition
            if (i == 0)
                System.out.println("\nboth buffer are lexicographically equal");
            else if (i >= 0)
                System.out.println("\nbb is lexicographically greater than bb1");
            else
                System.out.println("\nbb is lexicographically less than bb1");
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception throws : " + e);
        }

        catch (ReadOnlyBufferException e) {
            System.out.println("Exception throws : " + e);
        }
    }
}
```

**Output:** 

```java
ByteBuffer bb: [20, 30, 40]
ByteBuffer bb1: [40, 30, 40]

bb is lexicographically less than bb1
```