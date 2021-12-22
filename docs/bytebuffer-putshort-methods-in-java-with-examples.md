# Java 中的 ByteBuffer putShort()方法，带示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-put short-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-putshort-methods-in-java-with-examples/)

### 点短(整数值)

**java.nio.ByteBuffer** 类的 **putShort(int 值)**方法用于将包含给定短值的两个字节按当前字节顺序写入当前位置的缓冲区，然后将该位置增加 2。

**语法:**

```java
public abstract ByteBuffer putShort(short value)
```

**参数:**此方法取要写入的短值。

**返回值:**这个方法返回这个缓冲区。

**异常:**此方法抛出以下异常:

*   **Bufferovflowexception-** If the current position of this buffer is not less than its limit
*   **ReadonlyBufferenexception-** If this buffer is read-only,

下面是举例说明短值法的例子:

**例 1:**

```java
// Java program to demonstrate
// putShort() method

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

            // putting the value in ByteBuffer
            // using putShort() method
            bb.putShort((short)0x041A)
                .putShort((short)0x042A)
                .putShort((short)0x043A)
                .rewind();

            // print the ByteBuffer
            System.out.print("Original ByteBuffer: [ ");
            for (int i = 1; i <= capacity / 2; i++)
                System.out.print(bb.getShort() + " ");
            System.out.print("]");
        }

        catch (BufferOverflowException e) {

            System.out.println("Exception throws : " + e);
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("Exception throws : " + e);
        }
    }
}
```

**输出:**

```java
Original ByteBuffer: [ 1050 1066 1082 ]

```

**例 2:** 演示 BufferOverflowException。

```java
// Java program to demonstrate
// putShort() method

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

            // putting the value in ByteBuffer
            // using putShort() method
            bb.putShort((short)0x041A)
                .putShort((short)0x042A)
                .putShort((short)0x043A)
                .rewind();

            // print the ByteBuffer
            System.out.print("Original ByteBuffer: [ ");
            for (int i = 1; i <= capacity / 2; i++)
                System.out.print(bb.getShort() + " ");
            System.out.print("]");

            // putting the value in ByteBuffer
            // using putInt() method
            bb.putShort((short)234);
        }

        catch (BufferOverflowException e) {
            System.out.println("\n\nbuffer's current position"
                               + " is not smaller than its limit");
            System.out.println("Exception throws : " + e);
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("Exception throws : " + e);
        }
    }
}
```

**输出:**

```java
Original ByteBuffer: [ 1050 1066 1082 ]

buffer's current position is not smaller than its limit
Exception throws : java.nio.BufferOverflowException

```

**示例 3:** 演示 ReadOnlyBufferException。

```java
// Java program to demonstrate
// putShort() method

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

            // putting the value in ByteBuffer
            // using putShort() method
            bb.putShort((short)0x041A)
                .putShort((short)0x042A)
                .putShort((short)0x043A)
                .rewind();

            // print the ByteBuffer
            System.out.print("Original ByteBuffer: [ ");
            for (int i = 1; i <= capacity / 2; i++)
                System.out.print(bb.getShort() + " ");
            System.out.print("]");

            // Creating a read-only copy of ByteBuffer
            // using asReadOnlyBuffer() method
            ByteBuffer bb1 = bb.asReadOnlyBuffer();

            System.out.println("\n\nTrying to put the short value"
                               + " in read-only buffer");

            // putting the value in readonly ByteBuffer
            // using putShort() method
            bb1.putShort((short)234);
        }

        catch (BufferOverflowException e) {
            System.out.println("\n\nbuffer's current position"
                               + " is not smaller than its limit");
            System.out.println("Exception throws : " + e);
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("Exception throws : " + e);
        }
    }
}
```

**输出:**

```java
Original ByteBuffer: [ 1050 1066 1082 ]

Trying to put the short value in read only buffer
Exception throws : java.nio.ReadOnlyBufferException

```