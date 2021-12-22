# Java 中的 ByteBuffer getDouble()方法，带示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-get double-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-getdouble-method-in-java-with-examples/)

**getDouble()**

**[Java . nio . bytebuffer](https://www.geeksforgeeks.org/tag/java-bytebuffer/)**类的 **getDouble()** 方法用于读取该缓冲区当前位置的下八个字节，按照当前字节顺序组成一个 Double 值，然后将该位置递增八。

**语法:**

```java
public abstract double getDouble()
```

**返回值:**该方法返回缓冲区当前位置的双精度值

**抛出:**此方法抛出**bufferenderflow exception**如果缓冲区当前位置不小于其限制，则抛出此异常。

下面是说明 getDouble()方法的示例:

**示例 1:**

```java
// Java program to demonstrate
// getDouble() method

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

            // putting the double value in the bytebuffer
            bb.asDoubleBuffer()
                .put(1234.3456)
                .put(2884.4444);

            // rewind the Bytebuffer
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer: ");
            for (int i = 1; i <= capacity / 8; i++)
                System.out.print(bb.getDouble() + " ");

            // rewind the Bytebuffer
            bb.rewind();

            // Reads the double at this buffer's current position
            // using getDouble() method
            double value = bb.getDouble();

            // print the char value
            System.out.println("\n\nByte Value: " + value);

            // Reads the  char at this buffer's next position
            // using getDouble() method
            double value1 = bb.getDouble();

            // print the char value
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
1234.3456 2884.4444 

Byte Value: 1234.3456

Next Byte Value: 2884.4444

```

**示例 2:**

```java
// Java program to demonstrate
// getDouble() method

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

            // putting the double value in the bytebuffer
            bb.asDoubleBuffer()
                .put(1234.3456)
                .put(2884.4444);

            // rewind the Bytebuffer
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer: ");
            for (int i = 1; i <= capacity / 8; i++)
                System.out.print(bb.getDouble() + " ");

            // rewind the Bytebuffer
            bb.rewind();

            // Reads the double at this buffer's current position
            // using getDouble() method
            double value = bb.getDouble();

            // print the char value
            System.out.println("\n\nByte Value: " + value);

            // Reads the  char at this buffer's next position
            // using getDouble() method
            double value1 = bb.getDouble();

            // print the char value
            System.out.println("\nNext Byte Value: " + value1);

            // Reads the  char at this buffer's next position
            // using getDouble() method
            double value2 = bb.getDouble();
        }

        catch (BufferUnderflowException e) {
            System.out.println("\nthere are fewer than "
                               + "eight bytes remaining in"
                               + " this buffer");
            System.out.println("Exception Thrown : " + e);
        }
    }
}
```

**输出:**

```java
Original ByteBuffer: 
1234.3456 2884.4444 

Byte Value: 1234.3456

Next Byte Value: 2884.4444

there are fewer than eight bytes remaining in this buffer
Exception Thrown : java.nio.BufferUnderflowException

```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # getDouble–T4**getDouble(int index)**T7】

**字节缓冲**的 **getDouble(int index)** 方法用于读取给定索引处的八个字节，根据当前字节顺序将它们组成一个双数值。

**语法:**

```java
public abstract double getDouble(int index)
```

**参数:**该方法以**索引**为参数，该参数是读取字节的索引。

**返回值:**该方法返回给定索引处的双精度值

**异常:**此方法抛出**indexout of boundsexception**。如果索引为负或不小于缓冲区的限制，则会引发此异常。

下面是举例说明 *getDouble(int index)* 方法的例子:

**示例 1:**

```java
// Java program to demonstrate
// getDouble() method

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

            // putting the double value in the bytebuffer
            bb.asDoubleBuffer()
                .put(1234.3456)
                .put(2884.4444);

            // rewind the Bytebuffer
            bb.rewind();

            // Declaring the variable
            double c;

            // print the ByteBuffer
            System.out.println("Original ByteBuffer: ");
            for (int i = 1; i <= capacity / 8; i++)
                System.out.print(bb.getDouble() + " ");

            // rewind the Bytebuffer
            bb.rewind();

            // Reads the double at this buffer's current position
            // using getDouble() method
            double value = bb.getDouble(0);

            // print the char value
            System.out.println("\n\nByte Value: " + value);

            // Reads the  char at this buffer's next position
            // using getDouble() method
            double value1 = bb.getDouble(8);

            // print the char value
            System.out.print("\nNext Byte Value: " + value1);
        }

        catch (IndexOutOfBoundsException e) {

            System.out.println("\nindex is negative or "
                               + "smaller than the buffer's "
                               + "limit, minus seven");
            System.out.println("Exception Thrown : " + e);
        }
    }
}
```

**输出:**

```java
Original ByteBuffer: 
1234.3456 2884.4444 

Byte Value: 1234.3456

Next Byte Value: 2884.4444

```

**示例 2:**

```java
// Java program to demonstrate
// getDouble() method

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

            // putting the double value in the bytebuffer
            bb.asDoubleBuffer()
                .put(1234.3456)
                .put(2884.4444);

            // rewind the Bytebuffer
            bb.rewind();

            // Declaring the variable
            double c;

            // print the ByteBuffer
            System.out.println("Original ByteBuffer: ");
            for (int i = 1; i <= capacity / 8; i++)
                System.out.print(bb.getDouble() + " ");

            // rewind the Bytebuffer
            bb.rewind();

            // Reads the double at this buffer's current position
            // using getDouble() method
            double value = bb.getDouble(0);

            // print the char value
            System.out.println("\n\nByte Value: " + value);

            // Reads the  char at this buffer's next position
            // using getDouble() method
            double value1 = bb.getDouble(9);

            // print the char value
            System.out.print("\nNext Byte Value: " + value1);
        }

        catch (IndexOutOfBoundsException e) {

            System.out.println("\nindex is negative or"
                               + " smaller than the buffer's"
                               + " limit, minus seven");
            System.out.println("Exception Thrown : " + e);
        }
    }
}
```

**输出:**

```java
Original ByteBuffer: 
1234.3456 2884.4444 

Byte Value: 1234.3456

index is negative or smaller than the buffer's limit, minus seven
Exception Thrown : java.lang.IndexOutOfBoundsException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # getDouble-int-](https://docs.oracle.com/javase/9/docs/api/java/nio/ByteBuffer.html#getDouble-int-)