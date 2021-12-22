# Java 中的 ByteBuffer asFloatBuffer()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-as float buffer-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-asfloatbuffer-method-in-java-with-examples/)

**java.nio.ByteBuffer** 类的 **asFloatBuffer()** 方法用于创建该字节缓冲区作为浮动缓冲区的视图。
新缓冲区的内容将从该缓冲区的当前位置开始。对此缓冲区内容所做的更改将在新缓冲区中可见，反之亦然；两个缓冲器的位置、极限和标记值将是独立的。
新缓冲区的位置将为零，其容量和限制将是该缓冲区中剩余的字节数除以 4，其标记将是未定义的。如果且仅当该缓冲区是直接的，则新缓冲区将是直接的；如果且仅当该缓冲区是只读的，则新缓冲区将是只读的。

**语法:**

```java
public abstract FloatBuffer asFloatBuffer()
```

**返回值:**这个方法返回一个新的浮点缓冲区

下面是说明 asFloatBuffer()方法的示例:

**实施例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// asFloatBuffer() method
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

            // creating object of  ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // changing  bytebuffer into
            // FloatBuffer
            FloatBuffer cb = bb.asFloatBuffer();

            // putting the value in FloatBuffer
            cb.put(1.23F);
            cb.put(1.33F);
            cb.put(1.56F);
            cb.rewind();

            // Declaring variable c
            Float c;

            // print the ByteBuffer
            System.out.print("FloatBuffer : ");
            while ((c = cb.get()) != 0)
                System.out.print(c + " ");
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
FloatBuffer : 1.23 1.33 1.56
```

**实施例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// asFloatBuffer() method
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
            // FloatBuffer
            FloatBuffer cb = bb.asFloatBuffer();

            // putting the value in FloatBuffer
            cb.put(2.1F);
            cb.put(3.1F);
            cb.put(4.1F);
            cb.rewind();

            // Declaring variable c
            Float c;

            // print the ByteBuffer
            System.out.print("FloatBuffer : ");
            while ((c = cb.get()) != 0)
                System.out.print(c + "  ");

            // Creating a read-only copy of ByteBuffer
            // using asReadOnlyBuffer() method
            ByteBuffer bb1 = bb.asReadOnlyBuffer();

            // changing read-only bytebuffer into
            // read-only FloatBuffer
            FloatBuffer cb1 = bb1.asFloatBuffer();

            // putting the value in read-only FloatBuffer
            System.out.println("\n\nTrying to put the value "
                               + "in read only FloatBuffer");
            cb1.put(2.1F);
            cb1.put(3.1F);
            cb1.put(4.1F);
            cb1.rewind();
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
FloatBuffer : 2.1  3.1  4.1  

Trying to put the value in read only FloatBuffer
Exception thrown : java.nio.ReadOnlyBufferException
```