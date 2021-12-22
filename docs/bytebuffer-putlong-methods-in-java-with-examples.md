# Java 中的 ByteBuffer putLong()方法，带示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-putlong-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-putlong-methods-in-java-with-examples/)

### 整数值

**java.nio.ByteBuffer** 类的 **putLong(int value)** 方法用于按照当前字节顺序将包含给定长值的八个字节写入当前位置的缓冲区，然后将该位置递增八。

**语法:**

```java
public abstract ByteBuffer putLong(long value)
```

**参数:**该方法取要写入的长值。

**返回值:**这个方法返回这个缓冲区。

**异常:**此方法抛出以下异常:

*   **Bufferovflowexception-** If the current position of this buffer is not less than its limit
*   **ReadonlyBufferenexception-** If this buffer is read-only,

下面是举例说明 putLong(长值)方法的例子:

**例 1:**

```java
// Java program to demonstrate
// putLong() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 24;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the value in ByteBuffer
            // using putLong() method
            bb.putLong(23)
                .putLong(24)
                .putLong(30)
                .rewind();

            // print the ByteBuffer
            System.out.print("Original ByteBuffer: [ ");
            for (int i = 1; i <= capacity / 8; i++)
                System.out.print(bb.getLong() + " ");
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
Original ByteBuffer: [ 23 24 30 ]

```

**例 2:** 演示 BufferOverflowException。

```java
// Java program to demonstrate
// putLong() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 24;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the value in ByteBuffer
            // using putLong() method
            bb.putLong(23)
                .putLong(24)
                .putLong(30)
                .rewind();

            // print the ByteBuffer
            System.out.print("Original ByteBuffer: [ ");
            for (int i = 1; i <= capacity / 8; i++)
                System.out.print(bb.getLong() + " ");
            System.out.print("]");

            // putting the value in ByteBuffer
            // using putInt() method
            bb.putLong(234);
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
Original ByteBuffer: [ 23 24 30 ]

buffer's current position is not smaller than its limit
Exception throws : java.nio.BufferOverflowException

```

**示例 3:** 演示 ReadOnlyBufferException。

```java
// Java program to demonstrate
// putLong() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the ByteBuffer
        int capacity = 24;

        // Creating the ByteBuffer
        try {

            // creating object of ByteBuffer
            // and allocating size capacity
            ByteBuffer bb = ByteBuffer.allocate(capacity);

            // putting the value in ByteBuffer
            // using putLong() method
            bb.putLong(23)
                .putLong(24)
                .putLong(30)
                .rewind();

            // print the ByteBuffer
            System.out.print("Original ByteBuffer: [ ");
            for (int i = 1; i <= capacity / 8; i++)
                System.out.print(bb.getLong() + " ");
            System.out.print("]");

            // Creating a read-only copy of ByteBuffer
            // using asReadOnlyBuffer() method
            ByteBuffer bb1 = bb.asReadOnlyBuffer();

            System.out.println("\n\nTrying to put the long value"
                               + " in read-only buffer");

            // putting the value in readonly ByteBuffer
            // using putLong() method
            bb1.putLong(234);
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
Original ByteBuffer: [ 23 24 30 ]

Trying to put the long value in read only buffer
Exception throws : java.nio.ReadOnlyBufferException

```