# Java 中的字节缓冲包装()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-wrap-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-wrap-methods-in-java-with-examples/)

### 换行(字节[]数组)

类的 **wrap()** 方法用于将字节数组包装到缓冲区中。新的缓冲区将由给定的字节数组支持，即对缓冲区的修改将导致数组被修改，反之亦然。新缓冲区的容量和限制将是 array.length，它的位置将是零，它的标记将是未定义的，它的字节顺序将是 [BIG_ENDIAN](https://www.geeksforgeeks.org/little-and-big-endian-mystery/) 。它的后备数组将是给定的数组，并且它的数组偏移量将为零。

**语法:**

```java
public static ByteBuffer wrap(byte[] array)
```

**参数:**该方法以**数组**作为参数，该数组将支持该缓冲区。

**返回值:**这个方法返回新的字节缓冲区。

以下是说明**包裹()**方法的示例:

**实施例 1:**

```java
// Java program to demonstrate
// wrap() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declare and initialize the byte array
        byte[] bb = { 10, 20, 30 };

        // print the byte array length
        System.out.println("Array length: "
                           + bb.length);

        // print the byte array element
        System.out.println("\nArray element: "
                           + Arrays.toString(bb));

        // wrap the byte array into floatBuffer
        // using wrap() method
        ByteBuffer byteBuffer = ByteBuffer.wrap(bb);

        // Rewind the bytebuffer
        byteBuffer.rewind();

        // print the byte buffer
        System.out.println("\nbyteBuffer: "
                           + Arrays.toString(
                                 byteBuffer.array()));

        // print the byteBuffer capacity
        System.out.println("\nbytebuffer capacity: "
                           + byteBuffer.capacity());

        // print the byteBuffer position
        System.out.println("\nbytebuffer position:  "
                           + byteBuffer.position());
    }
}
```

**Output:**

```java
Array length: 3

Array element: [10, 20, 30]

byteBuffer: [10, 20, 30]

bytebuffer capacity: 3

bytebuffer position:  0

```

### 换行(字节[]数组，int 偏移量，int 长度)

给定的字节数组将支持新的缓冲区；也就是说，对缓冲区的修改将导致数组被修改，反之亦然。新缓冲区的容量将是 array.length，它的位置将被偏移，它的限制将是 offset + length，它的标记将是未定义的，它的字节顺序将是 BIG_ENDIAN。它的支持数组将是给定的数组，并且它的数组偏移量将为零。

**语法:**

```java
public static ByteBuffer 
    wrap(byte[] array, int offset, int length)
```

**参数:**该方法取以下参数:

*   **数组:**将支持新缓冲区的数组。
*   **偏移量:**要使用的子阵列的偏移量；必须为非负且不大于数组长度。新缓冲区的位置将被设置为该值。
*   **长度:**要使用的子阵列的长度；必须为非负且不大于 array . length–offset。新缓冲区的限制将设置为偏移量+长度。

**返回值:**这个方法返回新的字节缓冲区。

**异常:**该方法抛出**指数超出边界异常**(如果偏移和长度参数的前提条件不成立)。

下面是说明 wrap()方法的示例:

**实施例 1:**

```java
// Java program to demonstrate
// wrap() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        try {

            // Declare and initialize the byte array
            byte[] bb = { 10, 20, 30 };

            // print the byte array length
            System.out.println("Array length: "
                               + bb.length);

            // print the byte array element
            System.out.println("\nArray element: "
                               + Arrays.toString(bb));

            // wrap the byte array into floatBuffer
            // using wrap() method
            ByteBuffer byteBuffer
                = ByteBuffer.wrap(bb, 0,
                                  bb.length);

            // Rewind the bytebuffer
            byteBuffer.rewind();

            // print the byte buffer
            System.out.println("\nbyteBuffer: "
                               + Arrays.toString(
                                     byteBuffer.array()));

            // print the byteBuffer capacity
            System.out.println("\nbytebuffer capacity: "
                               + byteBuffer.capacity());

            // print the byteBuffer position
            System.out.println("\nbytebuffer position:  "
                               + byteBuffer.position());
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("\npreconditions on the"
                               + " offset and length parameters"
                               + " do not hold");
            System.out.println("Exception throws:  " + e);
        }
    }
}
```

**Output:**

```java
Array length: 3

Array element: [10, 20, 30]

byteBuffer: [10, 20, 30]

bytebuffer capacity: 3

bytebuffer position:  0

```

**示例 2:** 演示 IndexOutOfBoundsException

```java
// Java program to demonstrate
// wrap() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        try {

            // Declare and initialize the byte array
            byte[] bb = { 10, 20, 30 };

            // print the byte array length
            System.out.println("Array length: "
                               + bb.length);

            // print the byte array element
            System.out.println("\nArray element: "
                               + Arrays.toString(bb));

            // wrap the byte array into floatBuffer
            // using wrap() method
            ByteBuffer byteBuffer
                = ByteBuffer.wrap(bb, 1,
                                  bb.length);

            // Rewind the bytebuffer
            byteBuffer.rewind();

            // print the byte buffer
            System.out.println("\nbyteBuffer: "
                               + Arrays.toString(
                                     byteBuffer.array()));

            // print the byteBuffer capacity
            System.out.println("\nbytebuffer capacity: "
                               + byteBuffer.capacity());

            // print the byteBuffer position
            System.out.println("\nbytebuffer position:  "
                               + byteBuffer.position());
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("\npreconditions on the"
                               + " offset and length parameters"
                               + " do not hold");
            System.out.println("Exception throws:  " + e);
        }
    }
}
```

**Output:**

```java
Array length: 3

Array element: [10, 20, 30]

preconditions on the offset and length parameters do not hold
Exception throws:  java.lang.IndexOutOfBoundsException

```