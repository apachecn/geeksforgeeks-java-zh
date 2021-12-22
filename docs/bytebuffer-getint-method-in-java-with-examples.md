# Java 中的 ByteBuffer getInt()方法，带示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-getint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-getint-method-in-java-with-examples/)

**getInt()**

**java.nio.ByteBuffer** 类的 **getInt()** 方法用于读取该缓冲区当前位置的下四个字节，根据当前字节顺序将其组成一个 Int 值，然后将该位置递增四。

**语法:**

```java
public abstract int getInt()
```

**返回值:**该方法返回缓冲区当前位置的 int 值

**抛出:**这个方法抛出**bufferenderflow exception**–如果这个缓冲区剩余的字节少于 4 个。
下面是说明 getInt()方法的例子:

**实施例 1:**

```java
// Java program to demonstrate
// getInt() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 12;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the int value in the bytebuffer
            bb.asIntBuffer()
                .put(10)
                .put(20)
                .put(30);

            // rewind the Bytebuffer
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer: ");
            for (int i = 1; i <= capacity / 4; i++)
                System.out.print(bb.getInt() + " ");

            // rewind the Bytebuffer
            bb.rewind();

            // Reads the Int at this buffer's current position
            // using getInt() method
            int value = bb.getInt();

            // print the int value
            System.out.println("\n\nByte Value: " + value);

            // Reads the int at this buffer's next position
            // using getInt() method
            int value1 = bb.getInt();

            // print the int value
            System.out.println("Next Byte Value: " + value1);
        }

        catch (BufferUnderflowException e) {

            System.out.println("\nException Thrown : " + e);
        }
    }
}
```

**Output:**

```java
Original ByteBuffer: 
10 20 30 

Byte Value: 10
Next Byte Value: 20

```

**实施例 2:**

```java
// Java program to demonstrate
// getInt() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 8;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the int value in the bytebuffer
            bb.asIntBuffer()
                .put(10)
                .put(20);

            // rewind the Bytebuffer
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer: ");
            for (int i = 1; i <= capacity / 4; i++)
                System.out.print(bb.getInt() + " ");

            // rewind the Bytebuffer
            bb.rewind();

            // Reads the Int at this buffer's current position
            // using getInt() method
            int value = bb.getInt();

            // print the int value
            System.out.println("\n\nByte Value: " + value);

            // Reads the int at this buffer's next position
            // using getInt() method
            int value1 = bb.getInt();

            // print the int value
            System.out.println("Next Byte Value: " + value1);

            // Reads the int at this buffer's next position
            // using getInt() method
            int value2 = bb.getInt();
        }

        catch (BufferUnderflowException e) {
            System.out.println("\nthere are fewer than "
                               + "four bytes remaining in this buffer");
            System.out.println("Exception Thrown : " + e);
        }
    }
}
```

**Output:**

```java
Original ByteBuffer: 
10 20 

Byte Value: 10
Next Byte Value: 20

there are fewer than four bytes remaining in this buffer
Exception Thrown : java.nio.BufferUnderflowException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # getInt–](https://docs.oracle.com/javase/9/docs/api/java/nio/ByteBuffer.html#getInt--)

**getInt(int index)**

**字节缓冲**的 **getInt(Int index)** 方法用于读取给定索引处的四个字节，根据当前字节顺序将它们组成一个 int 值。

**语法:**

```java
public abstract int getInt(int index)
```

**参数:**该方法以索引(将从中读取字节的索引)为参数。

**返回值:**该方法返回给定索引处的 int 值。

**异常:**此方法抛出**indexout of boundsexception**。如果索引为负或不小于缓冲区的限制，则会引发此异常。

以下是说明 *getInt(int index)* 方法的示例:

**实施例 1:**

```java
// Java program to demonstrate
// getInt() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 8;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the int value in the bytebuffer
            bb.asIntBuffer()
                .put(10)
                .put(20);

            // rewind the Bytebuffer
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer: ");
            for (int i = 1; i <= capacity / 4; i++)
                System.out.print(bb.getInt() + " ");

            // rewind the Bytebuffer
            bb.rewind();

            // Reads the Int at this buffer's current position
            // using getInt() method
            int value = bb.getInt(0);

            // print the int value
            System.out.println("\n\nByte Value: " + value);

            // Reads the int at this buffer's next position
            // using getInt() method
            int value1 = bb.getInt(4);

            // print the int value
            System.out.println("Next Byte Value: " + value1);
        }

        catch (IndexOutOfBoundsException e) {

            System.out.println("\nindex is negative or smaller "
                               + "than the buffer's limit, minus seven");
            System.out.println("Exception Thrown : " + e);
        }
    }
}
```

**Output:**

```java
Original ByteBuffer: 
10 20 

Byte Value: 10
Next Byte Value: 20

```

**实施例 2:**

```java
// Java program to demonstrate
// getInt() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 8;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the int value in the bytebuffer
            bb.asIntBuffer()
                .put(10)
                .put(20);

            // rewind the Bytebuffer
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer: ");
            for (int i = 1; i <= capacity / 4; i++)
                System.out.print(bb.getInt() + " ");

            // rewind the Bytebuffer
            bb.rewind();

            // Reads the Int at this buffer's current position
            // using getInt() method
            int value = bb.getInt(0);

            // print the int value
            System.out.println("\n\nByte Value: " + value);

            // Reads the int at this buffer's next position
            // using getInt() method
            int value1 = bb.getInt(7);

            // print the int value
            System.out.println("Next Byte Value: " + value1);
        }

        catch (IndexOutOfBoundsException e) {

            System.out.println("\nindex is negative or smaller"
                               + " than the buffer's limit, minus seven");
            System.out.println("Exception Thrown : " + e);
        }
    }
}
```

**Output:**

```java
Original ByteBuffer: 
10 20 

Byte Value: 10

index is negative or smaller than the buffer's limit, minus seven
Exception Thrown : java.lang.IndexOutOfBoundsException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # getInt-int-](https://docs.oracle.com/javase/9/docs/api/java/nio/ByteBuffer.html#getInt-int-)