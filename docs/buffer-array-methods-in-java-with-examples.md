# Java 中的缓冲数组()方法，示例

> 原文:[https://www . geesforgeks . org/buffer-array-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/buffer-array-methods-in-java-with-examples/)

**java.nio.Buffer** 类的**数组()**方法用于返回支持所取缓冲区的数组。
此方法旨在允许数组支持的缓冲区更有效地传递给本机代码。具体的子类为此方法提供了更强类型的返回值。

对此缓冲区内容的修改将导致返回数组的内容被修改，反之亦然。在调用此方法之前，请调用 hasArray 方法，以确保此缓冲区具有可访问的后备数组。

**语法:**

```
public abstract Object array()
```

**返回值:**这个方法返回支持这个缓冲区的数组。

**异常:**如果此缓冲区由数组支持但为只读，则此方法将引发*readonlybufferrexception*。

下面是说明 array()方法的示例:

**例 1:**

```
// Java program to demonstrate
// array() method

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

            // putting the int to byte typecast
            // value in ByteBuffer
            bb.put((byte)20);
            bb.put((byte)30);
            bb.put((byte)40);
            bb.put((byte)50);

            // Typecasting ByteBuffer into Buffer
            Buffer bb1 = (Buffer)bb;

            // getting array that backs this buffer
            // using array() method
            byte[] arr = (byte[])bb1.array();

            // print the array
            System.out.print("array is : [");
            for (int i = 0; i < arr.length; i++)
                System.out.print(" " + arr[i]);
            System.out.print(" ]");
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("Exception throws: "
                               + e);
        }
    }
}
```

**Output:**

```
array is : [ 20 30 40 50 ]

```

**例 2:**

```
// Java program to demonstrate
// array() method

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

            // putting the int to byte typecast
            // value in ByteBuffer
            bb.put((byte)20);
            bb.put((byte)30);
            bb.put((byte)40);
            bb.put((byte)50);

            // Creating a read-only copy of ByteBuffer
            // using asReadOnlyBuffer() method
            ByteBuffer bb1 = bb.asReadOnlyBuffer();

            // Typecasting Read only ByteBuffer
            // into Read-only Buffer
            Buffer buffer = (Buffer)bb1;

            // getting array that backs this buffer
            // using array() method
            byte[] arr = (byte[])buffer.array();

            // print the array
            System.out.print("array is : [");
            for (int i = 0; i < arr.length; i++)
                System.out.print(" " + arr[i]);
            System.out.print(" ]");
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("buffer is backed by "
                               + "an array but is read-only");
            System.out.println("Exception throws: " + e);
        }
    }
}
```

**Output:**

```
buffer is backed by an array but is read-only
Exception throws: java.nio.ReadOnlyBufferException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/buffer . html # array–](https://docs.oracle.com/javase/9/docs/api/java/nio/Buffer.html#array--)