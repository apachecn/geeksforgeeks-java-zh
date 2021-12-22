# Java 中的 IntBuffer put()方法| Set 1

> 原文:[https://www . geesforgeks . org/int buffer-put-methods-in-Java-set-1/](https://www.geeksforgeeks.org/intbuffer-put-methods-in-java-set-1/)

### put(int i)

**java.nio.IntBuffer** 类的 **put(int i)** 方法用于将给定的 int 写入当前位置新创建的 int 缓冲区，然后递增该位置。

**语法:**

```java
public abstract IntBuffer put(int i)
```

**参数:**该方法将 int 值 **i** 作为参数写入 int 缓冲区。

**返回值:**这个方法返回这个缓冲区，其中插入了 int 值。

**异常:**此方法抛出以下异常:

*   **Bufferovflowexception-** If the current position of this buffer is not less than its limit
*   **ReadonlyBufferenexception-** If this buffer is read-only,

下面是举例说明 put(int i)方法的例子:

**例 1:**

```java
// Java program to demonstrate
// put() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the IntBuffer
        int capacity = 3;

        // Creating the IntBuffer
        try {

            // creating object of Intbuffer
            // and allocating size capacity
            IntBuffer ib = IntBuffer.allocate(capacity);

            // putting the value in Intbuffer using put() method
            ib.put(8);
            ib.put(9);
            ib.put(7);
            ib.rewind();

            // print the IntBuffer
            System.out.println("Original IntBuffer: "
                               + Arrays.toString(ib.array()));
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
Original IntBuffer: [8, 9, 7]

```

**例 2:** 演示 BufferOverflowException。

```java
// Java program to demonstrate
// put() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the IntBuffer
        int capacity = 3;

        // Creating the IntBuffer
        try {

            // creating object of Intbuffer
            // and allocating size capacity
            IntBuffer ib = IntBuffer.allocate(capacity);

            // putting the value in Intbuffer using put() method
            ib.put(8);
            ib.put(9);
            ib.put(7);

            System.out.println("Trying to put the Int at the "
                               + "position more than its limit");
            ib.put(7);

            // rewind the Intbuffer
            ib.rewind();

            // print the IntBuffer
            System.out.println("Original IntBuffer:  "
                               + Arrays.toString(ib.array()));
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
Trying to put the Int at the position more than its limit
Exception throws : java.nio.BufferOverflowException

```

**示例 3:** 演示 ReadOnlyBufferException。

```java
// Java program to demonstrate
// put() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the IntBuffer
        int capacity = 3;

        // Creating the IntBuffer
        try {

            // creating object of Intbuffer
            // and allocating size capacity using allocate() method
            IntBuffer ib = IntBuffer.allocate(capacity);

            // Creating a read-only copy of IntBuffer
            // using asReadOnlyBuffer() method
            IntBuffer ib1 = ib.asReadOnlyBuffer();

            System.out.println("Trying to put the Int value"
                               + " in read only buffer");

            // putting the value in readonly Intbuffer
            // using put() method
            ib1.put(8);
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
Trying to put the Int value in read only buffer
Exception throws : java.nio.ReadOnlyBufferException

```