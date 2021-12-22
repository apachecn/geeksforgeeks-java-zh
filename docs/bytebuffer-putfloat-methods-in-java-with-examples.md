# Java 中的 ByteBuffer putFloat()方法，带示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-put float-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-putfloat-methods-in-java-with-examples/)

### 浮点值

**java.nio.ByteBuffer** 类的 **putFloat(float value)** 方法用于按照当前字节顺序将包含给定浮点值的四个字节写入当前位置的缓冲区，然后将该位置递增四。

**语法:**

```
public abstract ByteBuffer putFloat(float value)
```

**参数:**该方法取一个参数**浮点值**，即需要写入的浮点值。

**返回值:**这个方法返回这个 ByteBuffer，将写入的浮点值作为参数传递。

**异常:**此方法抛出以下异常:

*   **Bufferovflowexception-** If the current position of this buffer is not less than its limit
*   **ReadonlyBufferenexception-** If this buffer is read-only,

下面是举例说明 putFloat(浮点值)方法的例子:

**例 1:**

```
// Java program to demonstrate
// putFloat() method

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

            // putting the value in ByteBuffer
            // using putFloat() method
            bb.putFloat(23.4f)
                .putFloat(234.5f)
                .putFloat(34.56f)
                .rewind();

            // print the ByteBuffer
            System.out.print("Original ByteBuffer: [ ");
            for (int i = 1; i <= capacity / 4; i++)
                System.out.print(bb.getFloat() + " ");
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
// putFloat() method

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

            // putting the value in ByteBuffer
            // using putFloat() method
            bb.putFloat(23.4f)
                .putFloat(234.5f)
                .putFloat(34.56f)
                .rewind();

            // print the ByteBuffer
            System.out.print("Original ByteBuffer: [ ");
            for (int i = 1; i <= capacity / 4; i++)
                System.out.print(bb.getFloat() + " ");
            System.out.print("]");

            // putting the value in ByteBuffer
            // using putFloat() method
            bb.putFloat(234.55f);
        }

        catch (BufferOverflowException e) {
            System.out.println("\n\nbuffer's current "
                               + "position is not smaller"
                               + " than its limit");
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
// putFloat() method

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

            // putting the value in ByteBuffer
            // using putFloat() method
            bb.putFloat(23.4f)
                .putFloat(234.5f)
                .putFloat(34.56f)
                .rewind();

            // print the ByteBuffer
            System.out.print("Original ByteBuffer: [ ");
            for (int i = 1; i <= capacity / 4; i++)
                System.out.print(bb.getFloat() + " ");
            System.out.print("]");

            // Creating a read-only copy of ByteBuffer
            // using asReadOnlyBuffer() method
            ByteBuffer bb1 = bb.asReadOnlyBuffer();

            System.out.println("\n\nTrying to put the float value"
                               + " in read-only buffer");

            // putting the value in readonly ByteBuffer
            // using putFloat() method
            bb1.putFloat(234.5f);
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

Trying to put the float value in read-only buffer
Exception throws : java.nio.ReadOnlyBufferException

```