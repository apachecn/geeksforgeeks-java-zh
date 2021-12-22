# ByteBuffer 将()方法放入 Java 中，示例| Set -1

> 原文:[https://www . geeksforgeeks . org/bytebuffer-put-methods-in-Java-with-examples-set-1/](https://www.geeksforgeeks.org/bytebuffer-put-methods-in-java-with-examples-set-1/)

### put(字节 b)

**java.nio.ByteBuffer** 类的 **put(byte b)** 方法用于将给定的字节写入当前位置新创建的字节缓冲区，然后递增该位置。

**语法:**

```
public abstract ByteBuffer put(byte f)
```

**参数:**该方法将字节值 **b** 作为参数写入字节缓冲区。

**返回值:**这个方法返回这个缓冲区，其中插入了字节值。

**异常:**此方法抛出以下异常:

*   **Bufferovflowexception-** If the current position of this buffer is not less than its limit
*   **ReadonlyBufferenexception-** If this buffer is read-only,

下面是举例说明 put(字节 b)方法的例子:

**例 1:**

```
// Java program to demonstrate
// put() method

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

            // putting the value in ByteBuffer using put() method
            bb.put((byte)10)
                .put((byte)20)
                .put((byte)30)
                .rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer:  "
                               + Arrays.toString(bb.array()));
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
Original ByteBuffer:  [10, 20, 30]

```

**例 2:** 演示 BufferOverflowException。

```
// Java program to demonstrate
// put() method

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

            // putting the value in ByteBuffer using put() method
            bb.put((byte)10)
                .put((byte)20)
                .put((byte)30);

            // print the ByteBuffer
            System.out.println("Original ByteBuffer:  "
                               + Arrays.toString(bb.array()));

            // again putting the value in ByteBuffer
            // using put() method
            System.out.println("\nBuffer position : "
                               + bb.position());
            bb.put((byte)40);
        }

        catch (BufferOverflowException e) {

            System.out.println("buffer's current position "
                               + "is not smaller than its limit");
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
Original ByteBuffer:  [10, 20, 30]

Buffer position : 3
buffer's current position is not smaller than its limit
Exception throws : java.nio.BufferOverflowException

```

**示例 3:** 演示 ReadOnlyBufferException。

```
// Java program to demonstrate
// put() method

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

            // putting the value in ByteBuffer using put() method
            bb.put((byte)10)
                .put((byte)20)
                .put((byte)30);

            // print the ByteBuffer
            System.out.println("Original ByteBuffer:  "
                               + Arrays.toString(bb.array()));

            // Creating a read-only copy of ByteBuffer
            // using asReadOnlyBuffer() method
            ByteBuffer bb1 = bb.asReadOnlyBuffer();

            System.out.println("\nTrying to put the byte value"
                               + " in read only buffer");

            // putting the value in readonly ByteBuffer
            // using put() method
            bb1.put((byte)40);
        }

        catch (BufferOverflowException e) {

            System.out.println("buffer's current position "
                               + "is not smaller than its limit");
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
Original ByteBuffer:  [10, 20, 30]

Trying to put the byte value in read only buffer
Exception throws : java.nio.ReadOnlyBufferException

```