# Java 中的 ByteBuffer get()方法，示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-get-method-in-java-with-examples/)

**get()**

**java.nio.ByteBuffer** 类的 **get()** 方法用于读取缓冲区当前位置的字节，然后递增该位置。

**语法:**

```java
public abstract byte get()
```

**返回值:**该方法返回缓冲区当前位置的字节。

**抛出:**此方法抛出**bufferenderflow exception**–如果缓冲区当前位置不小于其限制，则抛出此异常。

以下是举例说明 *get()* 方法的例子:

**实施例 1:**

```java
// Java program to demonstrate
// get() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 5;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the int to byte value in ByteBuffer
            bb.put((byte)20);
            bb.put((byte)30);
            bb.put((byte)40);
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer:  "
                               + Arrays.toString(bb.array()));

            // Reads the byte at this buffer's current position
            // using get() method
            byte value = bb.get();

            // print the byte value
            System.out.println("\nByte Value: " + value);

            // Reads the  Byte at this buffer's next position
            // using get() method
            byte value1 = bb.get();

            // print the Float value
            System.out.print("\nNext Byte Value: " + value1);
        }

        catch (IllegalArgumentException e) {

            System.out.println("\nException Thrown : " + e);
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("\nException Thrown : " + e);
        }

        catch (BufferUnderflowException e) {

            System.out.println("\nException Thrown : " + e);
        }
    }
}
```

**Output:**

```java
Original ByteBuffer:  [20, 30, 40, 0, 0]

Byte Value: 20

Next Byte Value: 30

```

**实施例 2:**

```java
// Java program to demonstrate
// get() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 3;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the int to byte typecast value in ByteBuffer
            bb.put((byte)20);
            bb.put((byte)30);

            // print the ByteBuffer
            System.out.println("Original ByteBuffer:  "
                               + Arrays.toString(bb.array()));

            // Reads the byte at this buffer's current position
            // using get() method
            byte value = bb.get();

            // print the byte value
            System.out.println("\nByte Value: " + value);

            // Reads the Byte at this buffer's next position
            // using get() method
            System.out.print("\nsince the buffer current position is incremented");
            System.out.print(" to greater than its limit ");

            byte value1 = bb.get();

            // print the Byte value
            System.out.print("\nNext Byte Value: " + value1);
        }

        catch (IllegalArgumentException e) {

            System.out.println("\nIllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("\nReadOnlyBufferException catched");
        }

        catch (BufferUnderflowException e) {

            System.out.println("\nException throws : " + e);
        }
    }
}
```

**Output:**

```java
Original ByteBuffer:  [20, 30, 0]

Byte Value: 0

since the buffer current position is incremented to greater than its limit 
Exception throws : java.nio.BufferUnderflowException

```

**get(int index)**

**ByteBuffer 的 get(int index)方法用于读取指定索引处的文章。**

****语法:****

```java
public abstract byte get(int index)
```

****参数:**该方法以索引(将从中读取字节的索引)为参数。**

****返回值:**该方法返回给定索引处的字节值。**

****异常:**此方法抛出**indexout of boundsexception**。如果索引为负或不小于缓冲区的限制，则会引发此异常。**

**以下是举例说明*获取(int index)* 方法的例子:**

****实施例 1:****

```java
// Java program to demonstrate
// get(int index) method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 3;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the int to byte typecast value in ByteBuffer
            bb.put((byte)20);
            bb.put((byte)30);
            bb.put((byte)40);

            // print the ByteBuffer
            System.out.println("Original ByteBuffer:  "
                               + Arrays.toString(bb.array()));

            // Reads the Byte at the index 0 of the Bytebuffer
            // using get() method
            byte value0 = bb.get(0);

            // print the Byte value
            System.out.println("\nByte Value at index 0: " + value0);

            // Reads the Byte at the index 1 of the Bytebuffer
            // using get() method
            byte value1 = bb.get(1);

            // print the Byte value
            System.out.println("\nByte Value at index 1: " + value1);

            // Reads the Byte at the index 2 of the Bytebuffer
            // using get() method
            byte value2 = bb.get(2);

            // print the Byte value
            System.out.println("\nByte Value at index 2: " + value2);
        }

        catch (IllegalArgumentException e) {

            System.out.println("\nIllegalArgumentException catched");
        }

        catch (IndexOutOfBoundsException e) {

            System.out.println("\nReadOnlyBufferException catched");
        }

        catch (BufferUnderflowException e) {

            System.out.println("\nException throws : " + e);
        }
    }
}
```

****Output:**

```java
Original ByteBuffer:  [20, 30, 40]

Byte Value at index 0: 20

Byte Value at index 1: 30

Byte Value at index 2: 40

```** 

****实施例 2:****

```java
// Java program to demonstrate
// get(int index) method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 3;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the int to byte typecast value in ByteBuffer
            bb.put((byte)20);
            bb.put((byte)30);
            bb.put((byte)40);

            // print the ByteBuffer
            System.out.println("Original ByteBuffer:  "
                               + Arrays.toString(bb.array()));

            // Reads the Byte at the index 0 of the Bytebuffer
            // using get() method
            byte value0 = bb.get(0);

            // print the Byte value
            System.out.println("\nByte Value at index 0: " + value0);

            // Reads the Byte at the index 1 of the Bytebuffer
            // using get() method
            byte value1 = bb.get(1);

            // print the Byte value
            System.out.println("\nByte Value at index 1: " + value1);

            // Reads the Byte at the index 4 of the Bytebuffer
            // using get() method
            System.out.println("\nTrying to get the byte"
                               + " of index greater than its limit ");
            byte value2 = bb.get(4);

            // print the Byte value
            System.out.println("\nByte Value at index 4: " + value2);
        }

        catch (IndexOutOfBoundsException e) {

            System.out.println("\nException throws : " + e);
        }

        catch (BufferUnderflowException e) {

            System.out.println("\nException throws : " + e);
        }
    }
}
```

****Output:**

```java
Original ByteBuffer:  [20, 30, 40]

Byte Value at index 0: 20

Byte Value at index 1: 30

Trying to get the byte of index greater than its limit 

Exception throws : java.lang.IndexOutOfBoundsException

```**