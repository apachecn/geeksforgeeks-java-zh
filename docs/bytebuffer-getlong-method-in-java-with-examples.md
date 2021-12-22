# Java 中的 ByteBuffer getLong()方法，带示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-getlong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-getlong-method-in-java-with-examples/)

**getLong()**

**java.nio.ByteBuffer** 类的 **getLong()** 方法用于读取该缓冲区当前位置的下八个字节，根据当前字节顺序将其组成一个长值，然后将该位置递增八。

**语法:**

```
public abstract long getLong()
```

**返回值:**该方法返回缓冲区当前位置的长值。

**抛出:**这个方法抛出**bufferenderflow exception**–如果这个缓冲区剩余的字节少于 4 个。

下面是说明 getLong()方法的示例:

**示例 1:**

```
// Java program to demonstrate
// getLong() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 16;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the long value in the bytebuffer
            bb.asLongBuffer()
                .put(1233003)
                .put(2292292);

            // rewind the Bytebuffer
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer: ");
            for (int i = 1; i <= capacity / 8; i++)
                System.out.print(bb.getLong() + " ");

            // rewind the Bytebuffer
            bb.rewind();

            // Reads the long at this buffer's current position
            // using getLong() method
            long value = bb.getLong();

            // print the long value
            System.out.println("\n\nByte Value: " + value);

            // Reads the  long at this buffer's next position
            // using getLong() method
            long value1 = bb.getLong();

            // print the long value
            System.out.print("\nNext Byte Value: " + value1);
        }

        catch (BufferUnderflowException e) {

            System.out.println("\nException Thrown : " + e);
        }
    }
}
```

**输出:**

```
Original ByteBuffer: 
1233003 2292292 

Byte Value: 1233003

Next Byte Value: 2292292

```

**示例 2:**

```
// Java program to demonstrate
// getLong() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 16;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the long value in the bytebuffer
            bb.asLongBuffer()
                .put(1233003)
                .put(2292292);

            // rewind the Bytebuffer
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer: ");
            for (int i = 1; i <= capacity / 8; i++)
                System.out.print(bb.getLong() + " ");

            // rewind the Bytebuffer
            bb.rewind();

            // Reads the long at this buffer's current position
            // using getLong() method
            long value = bb.getLong();

            // print the long value
            System.out.println("\n\nByte Value: " + value);

            // Reads the  long at this buffer's next position
            // using getLong() method
            long value1 = bb.getLong();

            // print the long value
            System.out.print("\nNext Byte Value: " + value1);

            // Reads the  long at this buffer's next position
            // using getLong() method
            long value2 = bb.getLong();
        }

        catch (BufferUnderflowException e) {
            System.out.println("\nthere are fewer than "
                               + "eight bytes remaining in this buffer");
            System.out.println("Exception Thrown : " + e);
        }
    }
}
```

**输出:**

```
Original ByteBuffer: 
1233003 2292292 

Byte Value: 1233003

Next Byte Value: 2292292
there are fewer than eight bytes remaining in this buffer
Exception Thrown : java.nio.BufferUnderflowException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # getLong–](https://docs.oracle.com/javase/9/docs/api/java/nio/ByteBuffer.html#getLong--)

T5】getLong(int index)

**字节缓冲**的 **getLong(int index)** 方法用于读取给定索引处的四个字节，根据当前字节顺序将它们组成一个浮点值。

**语法:**

```
public abstract long getLong(int index)
```

**参数:**该方法以索引(将从中读取字节的索引)为参数。

**返回值:**该方法返回给定索引处的长值。

**异常:**此方法抛出**indexout of boundsexception**。如果索引为负或不小于缓冲区的限制，则会引发此异常。

以下是举例说明 *getLong(int index)* 方法的例子:

**示例 1:**

```
// Java program to demonstrate
// getLong() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 16;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the long value in the bytebuffer
            bb.asLongBuffer()
                .put(1233003)
                .put(2292292);

            // rewind the Bytebuffer
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer: ");
            for (int i = 1; i <= capacity / 8; i++)
                System.out.print(bb.getLong() + " ");

            // rewind the Bytebuffer
            bb.rewind();

            // Reads the long at this buffer's current position
            // using getLong() method
            long value = bb.getLong(0);

            // print the long value
            System.out.println("\n\nByte Value: " + value);

            // Reads the  long at this buffer's next position
            // using getLong() method
            long value1 = bb.getLong(8);

            // print the long value
            System.out.print("\nNext Byte Value: " + value1);
        }

        catch (IndexOutOfBoundsException e) {

            System.out.println("\nindex is negative or "
                               + "smaller than the buffer's limit, "
                               + "minus seven");
            System.out.println("Exception Thrown : " + e);
        }
    }
}
```

**输出:**

```
Original ByteBuffer: 
1233003 2292292 

Byte Value: 1233003

Next Byte Value: 2292292

```

**示例 2:**

```
// Java program to demonstrate
// getLong() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 16;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the long value in the bytebuffer
            bb.asLongBuffer()
                .put(1233003)
                .put(2292292);

            // rewind the Bytebuffer
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer: ");
            for (int i = 1; i <= capacity / 8; i++)
                System.out.print(bb.getLong() + " ");

            // rewind the Bytebuffer
            bb.rewind();

            // Reads the long at this buffer's current position
            // using getLong() method
            long value = bb.getLong(0);

            // print the long value
            System.out.println("\n\nByte Value: " + value);

            // Reads the  long at this buffer's next position
            // using getLong() method
            long value1 = bb.getLong(11);

            // print the long value
            System.out.print("\nNext Byte Value: " + value1);
        }

        catch (IndexOutOfBoundsException e) {

            System.out.println("\nindex is negative or"
                               + " smaller than the buffer's limit, "
                               + "minus seven");
            System.out.println("Exception Thrown : " + e);
        }
    }
}
```

**输出:**

```
Original ByteBuffer: 
1233003 2292292 

Byte Value: 1233003

index is negative or smaller than the buffer's limit, minus seven
Exception Thrown : java.lang.IndexOutOfBoundsException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # getLong-int-](https://docs.oracle.com/javase/9/docs/api/java/nio/ByteBuffer.html#getLong-int-)