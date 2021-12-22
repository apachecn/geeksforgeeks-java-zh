# Java 中的 ByteBuffer putChar()方法，带示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-putchar-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-putchar-methods-in-java-with-examples/)

### char value(char 值)

**java.nio.ByteBuffer** 类的 **putChar(Char 值)**方法用于按照当前字节顺序将包含给定 char 值的两个字节写入当前位置的缓冲区，然后将该位置增加 2。

**语法:**

```
public abstract ByteBuffer putChar(char value)
```

**参数:**该方法取要写入的字符值。

**返回值:**这个方法返回这个缓冲区。

**异常:**此方法抛出以下异常:

*   **Bufferovflowexception-** If the current position of this buffer is not less than its limit
*   **ReadonlyBufferenexception-** If this buffer is read-only,

下面是举例说明 putChar(char 值)方法的例子:

**例 1:**

```
// Java program to demonstrate
// putChar() method

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
            // using putChar() method
            bb.putChar('a')
                .putChar('b')
                .putChar('c')
                .rewind();

            // print the ByteBuffer
            System.out.print("Original ByteBuffer: [ ");
            for (int i = 1; i <= capacity / 2; i++)
                System.out.print(bb.getChar() + " ");
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
Original ByteBuffer: [ a b c ]

```

**例 2:** 演示 BufferOverflowException。

```
// Java program to demonstrate
// putChar() method

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
            // using putChar() method
            bb.putChar('a')
                .putChar('b')
                .putChar('c')
                .rewind();

            // print the ByteBuffer
            System.out.print("Original ByteBuffer: [ ");
            for (int i = 1; i <= capacity / 2; i++)
                System.out.print(bb.getChar() + " ");
            System.out.print("]\n\n");

            // putting the value in ByteBuffer
            // using putChar() method
            bb.putChar('d');
        }

        catch (BufferOverflowException e) {
            System.out.println("buffer's current position"
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
Original ByteBuffer: [ a b c ]

buffer's current position is not smaller than its limit
Exception throws : java.nio.BufferOverflowException

```

**示例 3:** 演示 ReadOnlyBufferException。

```
// Java program to demonstrate
// putChar() method

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
            // using putChar() method
            bb.putChar('a')
                .putChar('b')
                .putChar('c')
                .rewind();

            // print the ByteBuffer
            System.out.print("Original ByteBuffer: [ ");
            for (int i = 1; i <= capacity / 2; i++)
                System.out.print(bb.getChar() + " ");
            System.out.print("]\n");

            // Creating a read-only copy of ByteBuffer
            // using asReadOnlyBuffer() method
            ByteBuffer bb1 = bb.asReadOnlyBuffer();

            System.out.println("\nTrying to put the char value"
                               + " in read-only buffer");

            // putting the value in readonly ByteBuffer
            // using putChart() method
            bb1.putChar('d');
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
Original ByteBuffer: [ a b c ]

Trying to put the char value in read-only buffer
Exception throws : java.nio.ReadOnlyBufferException

```