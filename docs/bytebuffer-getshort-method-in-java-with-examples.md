# Java 中的 ByteBuffer getShort()方法，带示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-get short-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-getshort-method-in-java-with-examples/)

**getShort()**

**[Java . nio . bytebuffer](https://www.geeksforgeeks.org/tag/java-bytebuffer/)**类的 **getShort()** 方法用于读取该缓冲区当前位置的下两个字节，根据当前字节顺序将其组成一个短值，然后将该位置递增 2。

**语法:**

```java
public abstract short getShort()
```

**返回值:**该方法返回缓冲区当前位置的短值。

**抛出:**如果这个缓冲区剩余的字节少于 4 个，这个方法抛出**bufferenderflow exception**。

下面是说明 getShort()方法的示例:

**示例 1:**

```java
// Java program to demonstrate
// getShort() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 6;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the short value in the bytebuffer
            bb.asShortBuffer()
                .put((short)1034)
                .put((short)1035)
                .put((short)1036);

            // rewind the Bytebuffer
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer: ");
            for (int i = 1; i <= capacity / 2; i++)
                System.out.print(bb.getShort() + " ");

            // rewind the Bytebuffer
            bb.rewind();

            // Reads the long at this buffer's current position
            // using getShort() method
            long value = bb.getShort();

            // print the long value
            System.out.println("\n\nByte Value: " + value);

            // Reads the short at this buffer's next position
            // using getShort() method
            long value1 = bb.getShort();

            // print the short value
            System.out.print("\nNext Byte Value: " + value1);
        }

        catch (BufferUnderflowException e) {

            System.out.println("\nException Thrown : " + e);
        }
    }
}
```

**输出:**

```java
Original ByteBuffer: 
1034 1035 1036 

Byte Value: 1034

Next Byte Value: 1035

```

**示例 2:**

```java
// Java program to demonstrate
// getShort() method

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

            // putting the short value in the bytebuffer
            bb.asShortBuffer()
                .put((short)1034)
                .put((short)1036);

            // rewind the Bytebuffer
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer: ");
            for (int i = 1; i <= capacity / 2; i++)
                System.out.print(bb.getShort() + " ");

            // rewind the Bytebuffer
            bb.rewind();

            // Reads the long at this buffer's current position
            // using getShort() method
            long value = bb.getShort();

            // print the long value
            System.out.println("\n\nByte Value: " + value);

            // Reads the short at this buffer's next position
            // using getShort() method
            long value1 = bb.getShort();

            // print the short value
            System.out.print("\nNext Byte Value: " + value1);

            // Reads the short at this buffer's next position
            // using getShort() method
            long value2 = bb.getShort();
        }

        catch (BufferUnderflowException e) {
            System.out.println("\nthere are fewer than"
                               + " two bytes remaining in this buffer");
            System.out.println("Exception Thrown : " + e);
        }
    }
}
```

**输出:**

```java
Original ByteBuffer: 
1034 1036 

Byte Value: 1034

Next Byte Value: 1036
there are fewer than two bytes remaining in this buffer
Exception Thrown : java.nio.BufferUnderflowException

```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # getShort–T4**getLong(int index)**T7】

**字节缓冲**的 **getLong(int index)** 方法用于读取给定索引处的四个字节，根据当前字节顺序将它们组成一个浮点值。

**语法:**

```java
public abstract long getLong(int index)
```

**参数:**该方法以索引(将从中读取字节的索引)为参数。

**返回值:**该方法返回给定索引处的长值。

**异常:**此方法抛出**indexout of boundsexception**。如果索引为负或不小于缓冲区的限制，则会引发此异常。

以下是举例说明 *getLong(int index)* 方法的例子:

**示例 1:**

```java
// Java program to demonstrate
// getShort() method

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

            // putting the short value in the bytebuffer
            bb.asShortBuffer()
                .put((short)1034)
                .put((short)1036);

            // rewind the Bytebuffer
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer: ");
            for (int i = 1; i <= capacity / 2; i++)
                System.out.print(bb.getShort() + " ");

            // rewind the Bytebuffer
            bb.rewind();

            // Reads the long at this buffer's current position
            // using getShort() method
            long value = bb.getShort(0);

            // print the long value
            System.out.println("\n\nByte Value: " + value);

            // Reads the short at this buffer's next position
            // using getShort() method
            long value1 = bb.getShort(2);

            // print the short value
            System.out.print("\nNext Byte Value: " + value1);
        }

        catch (IndexOutOfBoundsException e) {

            System.out.println("\nindex is negative or "
                               + "smaller than the buffer's limit, "
                               + " minus seven");
            System.out.println("Exception Thrown : " + e);
        }
    }
}
```

**输出:**

```java
Original ByteBuffer: 
1034 1036 

Byte Value: 1034

Next Byte Value: 1036

```

**示例 2:**

```java
// Java program to demonstrate
// getShort() method

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

            // putting the short value in the bytebuffer
            bb.asShortBuffer()
                .put((short)1034)
                .put((short)1036);

            // rewind the Bytebuffer
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer: ");
            for (int i = 1; i <= capacity / 2; i++)
                System.out.print(bb.getShort() + " ");

            // rewind the Bytebuffer
            bb.rewind();

            // Reads the long at this buffer's current position
            // using getShort() method
            long value = bb.getShort(0);

            // print the long value
            System.out.println("\n\nByte Value: " + value);

            // Reads the short at this buffer's next position
            // using getShort() method
            long value1 = bb.getShort(3);

            // print the short value
            System.out.print("\nNext Byte Value: " + value1);
        }

        catch (IndexOutOfBoundsException e) {

            System.out.println("\nindex is negative or smaller "
                               + "than the buffer's limit, "
                               + "minus one");
            System.out.println("Exception Thrown : " + e);
        }
    }
}
```

**输出:**

```java
Original ByteBuffer: 
1034 1036 

Byte Value: 1034

index is negative or smaller than the buffer's limit, minus one
Exception Thrown : java.lang.IndexOutOfBoundsException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # getShort-int-](https://docs.oracle.com/javase/9/docs/api/java/nio/ByteBuffer.html#getShort-int-)