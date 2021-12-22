# Java 中的 ByteBuffer asCharBuffer()方法，带示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-ascharbuffer-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-ascharbuffer-method-in-java-with-examples/)

**java.nio.ByteBuffer** 类的 **asCharBuffer()** 方法用于创建该字节缓冲区作为字符缓冲区的视图。
新缓冲区的内容将从该缓冲区的当前位置开始。对此缓冲区内容的更改将在新缓冲区中可见，反之亦然；两个缓冲器的位置、极限和标记值将是独立的。
新缓冲区的位置将为零，其容量和限制将是该缓冲区中剩余的字节数除以 2，其标记将是未定义的。如果且仅当该缓冲区是直接的，则新缓冲区将是直接的；如果且仅当该缓冲区是只读的，则新缓冲区将是只读的。
**语法:**

```java
public abstract CharBuffer asCharBuffer()
```

**返回值:**这个方法返回一个新的字符缓冲区。
以下是说明 asCharBuffer()方法的示例:
**示例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// asCharBuffer() method
// for ByteBuffer

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity  of the ByteBuffer
        int capacity = 50;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // changing bytebuffer view as char buffer
            // and putting a string value
            bb.asCharBuffer().put("TajMahal");

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

**Output:** 

```java
Char buffer : T a j M a h a l
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// asCharBuffer() method
// for Read only ByteBuffer

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity  of the ByteBuffer
        int capacity = 50;

        // Creating the ByteBuffer
        try {

            // creating object of  ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // changing  bytebuffer into
            // char buffer
            CharBuffer cb = bb.asCharBuffer();

            // putting the value in charbuffer
            cb.put("Tajmahal");
            cb.rewind();

            // Declaring variable c
            char c;

            // print the ByteBuffer
            System.out.print("Char buffer : ");
            while ((c = cb.get()) != 0)
                System.out.print(c + " ");

            // Creating a read-only copy of ByteBuffer
            // using asReadOnlyBuffer() method
            ByteBuffer bb1 = bb.asReadOnlyBuffer();

            // changing read only bytebuffer into
            // read only char buffer
            CharBuffer cb1 = bb1.asCharBuffer();

            // putting the value in charbuffer
            System.out.println("\n\nTrying to put the string"
                               + " into read only charbuffer");
            cb1.put("Tajmahal");
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

**Output:** 

```java
Char buffer : T a j m a h a l 

Trying to put the string into read only charbuffer
Exception thrown : java.nio.ReadOnlyBufferException
```