# Java 中的字节缓冲包装()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-wrap-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-wrap-method-in-java-with-examples/)

### 换行(字节[]数组)

类的 **wrap()** 方法用于将字节数组包装到缓冲区中。给定的字节数组将支持新的缓冲区；也就是说，对缓冲区的修改将导致数组被修改，反之亦然。新缓冲区的容量和限制将为 array.length，其位置将为零，其标记将未定义。它的后备数组将是给定的数组，并且它的数组偏移量将为零。

**语法:**

```java
public static ByteBuffer wrap(float[] array)
```

**参数:**该方法以一个浮点**数组**作为参数，该数组将支持该缓冲区。

**返回值:**这个方法返回新的字节缓冲区。

以下是说明**包裹()**方法的示例:

**示例 1:**

```java
// Java program to demonstrate
// wrap() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declare and initialize the byte array
        byte[] bbb = { 10, 20, 30 };

        // print the byte array length
        System.out.println("Array length : "
                           + bbb.length);

        // print the byte array element
        System.out.println("\nArray element : "
                           + Arrays.toString(bbb));

        // wrap the byte array into byteBuffer
        // using wrap() method
        ByteBuffer byteBuffer = ByteBuffer.wrap(bbb);

        // Rewind the ByteBuffer
        byteBuffer.rewind();

        // print the byte buffer
        System.out.println("\nbyteBuffer : "
                           + Arrays.toString(byteBuffer.array()));

        // print the ByteBuffer capacity
        System.out.println("\nbyteBuffer capacity : "
                           + byteBuffer.capacity());

        // print the ByteBuffer position
        System.out.println("\nbyteBuffer position:  "
                           + byteBuffer.position());
    }
}
```

**输出:**

```java
Array length : 3

Array element : [10, 20, 30]

byteBuffer : [10, 20, 30]

byteBuffer capacity : 3

byteBuffer position:  0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # wrap-byte:A-](https://docs.oracle.com/javase/9/docs/api/java/nio/ByteBuffer.html#wrap-byte:A-)

### 换行(字节[]数组，int 偏移量，int 长度)

给定的字节数组将支持新的缓冲区；也就是说，对缓冲区的修改将导致数组被修改，反之亦然。新缓冲区的容量将是 array.length，它的位置将被偏移，它的限制将是 offset + length，它的标记将是未定义的。它的后备数组将是给定的数组，并且它的数组偏移量将为零。

**语法:**

```java
public static ByteBuffer wrap(byte[] array, 
                          int offset, int length)
```

**参数:**此方法取以下参数:

*   **Array:** The array of the new buffer will be backed up.
*   **Offset:** Offset of the subarray to be used; Must be non-negative and not greater than the array length. The location of the new buffer will be set to this value.
*   **Length:** The length of the subarray to be used; Must be non-negative and not greater than array.length–offset. The limit of the new buffer will be set to offset+length.

**返回值:**这个方法返回新的字节缓冲区。

**抛出:**此方法抛出**指数超出边界异常**(如果偏移和长度参数的前提条件不成立)。

下面是说明 wrap()方法的示例:

**示例 1:**

```java
// Java program to demonstrate
// wrap() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declare and initialize the byte array
        byte[] bbb = { 10, 20, 30 };

        // print the byte array length
        System.out.println("Array length : "
                           + bbb.length);

        // print the byte array element
        System.out.println("\nArray element : "
                           + Arrays.toString(bbb));

        // wrap the byte array into ByteBuffer
        // using wrap() method
        ByteBuffer byteBuffer = ByteBuffer.wrap(bbb, 0,
                                                bbb.length);

        // Rewind the bytebuffer
        byteBuffer.rewind();

        // print the byte buffer
        System.out.println("\nbyteBuffer : "
                           + Arrays.toString(byteBuffer.array()));

        // print the ByteBuffer capacity
        System.out.println("\nbyteBuffer capacity : "
                           + byteBuffer.capacity());

        // print the ByteBuffer position
        System.out.println("\nbyteBuffer position:  "
                           + byteBuffer.position());
    }
}
```

**输出:**

```java
Array length : 3

Array element : [10, 20, 30]

byteBuffer : [10, 20, 30]

byteBuffer capacity : 3

byteBuffer position:  0

```

**示例 2:** 演示 NullPointerException

```java
// Java program to demonstrate
// asReadOnlyBuffer() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declare and initialize the byte array
        byte[] bbb = { 10, 20, 30 };

        // print the byte array length
        System.out.println("Array length : " + bbb.length);

        // print the byte array element
        System.out.println("\nArray element : " + Arrays.toString(bbb));

        try {
            // wrap the byte array into byteBuffer
            // using wrap() method
            System.out.println("\nHere "
                               + "offset and length does not hold"
                               + " the required condition ");
            ByteBuffer byteBuffer = ByteBuffer.wrap(bbb,
                                                    1,
                                                    bbb.length);

            // Rewind the bytebuffer
            byteBuffer.rewind();

            // print the byte buffer
            System.out.println("\nbyteBuffer : "
                               + Arrays.toString(byteBuffer.array()));

            // print the byteBuffer capacity
            System.out.println("\nbytebuffer capacity : "
                               + byteBuffer.capacity());

            // print the byteBuffer position
            System.out.println("\nbytebuffer position:  "
                               + byteBuffer.position());
        }
        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception throws:  " + e);
        }
    }
}
```

**输出:**

```java
Array length : 3

Array element : [10, 20, 30]

Here offset and length does not hold the required condition 
Exception throws:  java.lang.IndexOutOfBoundsException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # wrap-byte:A-int-int-](https://docs.oracle.com/javase/9/docs/api/java/nio/ByteBuffer.html#wrap-byte:A-int-int-)