# Java 中的 ByteBuffer putDouble()方法示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-put double-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-putdouble-methods-in-java-with-examples/)

### 双精度值

**java.nio.ByteBuffer** 类的 **putDouble(Double value)** 方法用于按照当前字节顺序将包含给定 double 值的八个字节写入当前位置的缓冲区，然后将该位置增加八。

**语法:**

```
public abstract ByteBuffer putDouble?(double value)
```

**参数:**该方法取要写入的双精度值。

**返回值:**这个方法返回这个缓冲区。

**异常:**此方法抛出以下异常:

*   **Bufferovflowexception-** If the current position of this buffer is not less than its limit
*   **ReadonlyBufferenexception-** If this buffer is read-only,

下面是举例说明 putDouble(双精度值)方法的例子:

**例 1:**

```
// Java program to demonstrate
// putDouble() method

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
            // using putDouble() method
            bb.putDouble(23.4)
                .putDouble(234.5)
                .putDouble(34.56)
                .rewind();

            // print the ByteBuffer
            System.out.print("Original ByteBuffer: [ ");
            for (int i = 1; i <= capacity / 8; i++)
                System.out.print(bb.getDouble() + " ");
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

```
Original ByteBuffer: [ 23.4 234.5 34.56 ]

```

**例 2:** 演示 BufferOverflowException。

```
// Java program to demonstrate
// putDouble() method

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
            // using putDouble() method
            bb.putDouble(23.4)
                .putDouble(234.5)
                .putDouble(34.56)
                .rewind();

            // print the ByteBuffer
            System.out.print("Original ByteBuffer: [ ");
            for (int i = 1; i <= capacity / 8; i++)
                System.out.print(bb.getDouble() + " ");
            System.out.print("]");

            // putting the value in ByteBuffer
            // using putDouble() method
            bb.putDouble(234.55);
        }

        catch (BufferOverflowException e) {
            System.out.println("\n\nbuffer's current position"
                               + " is not smaller than"
                               + " its limit");
            System.out.println("Exception throws : " + e);
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("Exception throws : " + e);
        }
    }
}
```

**输出:**

```
Original ByteBuffer: [ 23.4 234.5 34.56 ]

buffer's current position is not smaller than its limit
Exception throws : java.nio.BufferOverflowException

```

**示例 3:** 演示 ReadOnlyBufferException。

```
// Java program to demonstrate
// putDouble() method

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
            // using putDouble() method
            bb.putDouble(23.4)
                .putDouble(234.5)
                .putDouble(34.56)
                .rewind();

            // print the ByteBuffer
            System.out.print("Original ByteBuffer: [ ");
            for (int i = 1; i <= capacity / 8; i++)
                System.out.print(bb.getDouble() + " ");
            System.out.print("]");

            // Creating a read-only copy of ByteBuffer
            // using asReadOnlyBuffer() method
            ByteBuffer bb1 = bb.asReadOnlyBuffer();

            System.out.println("\n\nTrying to put the char value"
                               + " in read-only buffer");

            // putting the value in readonly ByteBuffer
            // using putDouble() method
            bb1.putDouble(234.5);
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

```
Original ByteBuffer: [ 23.4 234.5 34.56 ]

Trying to put the char value in read-only buffer
Exception throws : java.nio.ReadOnlyBufferException

```