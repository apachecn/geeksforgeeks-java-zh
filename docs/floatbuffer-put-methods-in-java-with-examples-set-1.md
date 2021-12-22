# 用示例将()方法放入 Java 中

> 原文:[https://www . geeksforgeeks . org/float buffer-put-methods-in-Java-with-examples-set-1/](https://www.geeksforgeeks.org/floatbuffer-put-methods-in-java-with-examples-set-1/)

### 放(浮 f)

**java.nio.FloatBuffer** 类的 **put(float f)** 方法用于将给定的 float 写入当前位置新创建的 float 缓冲区，然后递增该位置。

**语法:**

```java
public abstract FloatBuffer put(float f)
```

**参数:**该方法将浮点值 **f** 作为参数写入浮点缓冲区。

**返回值:**这个方法返回这个缓冲区，其中插入了浮点值。

**异常:**此方法抛出以下异常:

*   **Bufferovflowexception-** If the current position of this buffer is not less than its limit
*   **ReadonlyBufferenexception-** If this buffer is read-only,

下面是举例说明 put(float f)方法的例子:

**例 1:**

```java
// Java program to demonstrate
// put() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the FloatBuffer
        int capacity = 3;

        // Creating the FloatBuffer
        try {

            // creating object of floatbuffer
            // and allocating size capacity
            FloatBuffer fb = FloatBuffer.allocate(capacity);

            // putting the value in floatbuffer using put() method
            fb.put(8.56F);
            fb.put(9.61F);
            fb.put(7.86F);
            fb.rewind();

            // print the FloatBuffer
            System.out.println("Original FloatBuffer:  "
                               + Arrays.toString(fb.array()));
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
Original FloatBuffer:  [8.56, 9.61, 7.86]

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

        // Declaring the capacity of the FloatBuffer
        int capacity = 3;

        // Creating the FloatBuffer
        try {

            // creating object of floatbuffer
            // and allocating size capacity
            FloatBuffer fb = FloatBuffer.allocate(capacity);

            // putting the value in floatbuffer using put() method
            fb.put(8.56F);
            fb.put(9.61F);
            fb.put(7.86F);

            System.out.println("Trying to put the float at the "
                             + "position more than its limit");
            fb.put(7.86F);

            // rewind the floatbuffer
            fb.rewind();

            // print the FloatBuffer
            System.out.println("Original FloatBuffer:  "
                               + Arrays.toString(fb.array()));
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
Trying to put the float at the position more than its limit
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

        // Declaring the capacity of the FloatBuffer
        int capacity = 3;

        // Creating the FloatBuffer
        try {

            // creating object of floatbuffer
            // and allocating size capacity using allocate() method
            FloatBuffer fb = FloatBuffer.allocate(capacity);

            // Creating a read-only copy of FloatBuffer
            // using asReadOnlyBuffer() method
            FloatBuffer fb1 = fb.asReadOnlyBuffer();

            System.out.println("Trying to put the float value"
                               + " in read only buffer");

            // putting the value in readonly floatbuffer
            // using put() method
            fb1.put(8.56F);
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
Trying to put the float value in read only buffer
Exception throws : java.nio.ReadOnlyBufferException

```