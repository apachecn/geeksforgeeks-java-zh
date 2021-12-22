# Java 中的 ByteBuffer getFloat()方法，带示例

> 原文:[https://www . geeksforgeeks . org/bytebuffer-getfloat-method-in-Java-with-examples/](https://www.geeksforgeeks.org/bytebuffer-getfloat-method-in-java-with-examples/)

**getFloat()**

**[Java . nio . bytebuffer](https://www.geeksforgeeks.org/tag/java-bytebuffer/)**类的 **getFloat()** 方法用于读取该缓冲区当前位置的下四个字节，按照当前字节顺序组成一个 Float 值，然后将该位置递增四。

**语法:**

```java
public abstract float getFloat()
```

**返回值:**该方法返回缓冲区当前位置的浮点值。

**异常:**如果这个缓冲区中剩余的字节少于 4 个，这个方法抛出**bufferenderflow Exception**。

以下是说明 getFloat()方法的示例:

**示例 1:**

```java
// Java program to demonstrate
// getFloat() method

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

            // putting the double value in the bytebuffer
            bb.asFloatBuffer()
                .put(12.3f)
                .put(28.44f);

            // rewind the Bytebuffer
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer: ");
            for (int i = 1; i <= capacity / 4; i++)
                System.out.print(bb.getFloat() + " ");

            // rewind the Bytebuffer
            bb.rewind();

            // Reads the Float at this buffer's current position
            // using getFloat() method
            float value = bb.getFloat();

            // print the float value
            System.out.println("\n\nByte Value: " + value);

            // Reads the  float at this buffer's next position
            // using getFloat() method
            float value1 = bb.getFloat();

            // print the float value
            System.out.print("\nNext Byte Value: " + value1);
        }

        catch (BufferUnderflowException e) {

            System.out.println("\nException Thrown : " + e);
        }
    }
}
```

**输出:**

```java
Original ByteBuffer: 
12.3 28.44 

Byte Value: 12.3

Next Byte Value: 28.44

```

**示例 2:**

```java
// Java program to demonstrate
// getFloat() method

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

            // putting the double value in the bytebuffer
            bb.asFloatBuffer()
                .put(12.3f)
                .put(28.44f);

            // rewind the Bytebuffer
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer: ");
            for (int i = 1; i <= capacity / 4; i++)
                System.out.print(bb.getFloat() + " ");

            // rewind the Bytebuffer
            bb.rewind();

            // Reads the Float at this buffer's current position
            // using getFloat() method
            float value = bb.getFloat();

            // print the float value
            System.out.println("\n\nByte Value: " + value);

            // Reads the  float at this buffer's next position
            // using getFloat() method
            float value1 = bb.getFloat();

            // print the float value
            System.out.println("\nNext Byte Value: " + value1);

            // Reads the  float at this buffer's next position
            // using getFloat() method
            float value2 = bb.getFloat();
        }

        catch (BufferUnderflowException e) {
            System.out.println("\nthere are fewer "
                               + "than eight bytes remaining"
                               + " in this buffer");
            System.out.println("Exception Thrown : " + e);
        }
    }
}
```

**输出:**

```java
Original ByteBuffer: 
12.3 28.44 

Byte Value: 12.3

Next Byte Value: 28.44

there are fewer than eight bytes remaining in this buffer
Exception Thrown : java.nio.BufferUnderflowException

```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # getFloat–T4**getFloat(int index)**T7】

**[Java . nio . bytebuffer](https://www.geeksforgeeks.org/tag/java-bytebuffer/)**的 **getFloat(int index)** 方法用于读取给定索引处的四个字节，根据当前字节顺序将其组成一个 Float 值。

**语法:**

```java
public abstract float getFloat(int index)
```

**参数:**该方法以**索引**为参数，该参数是读取字节的索引。

**返回值:**该方法返回给定索引处的浮点值。

**异常:**如果索引为负或不小于缓冲区的限制，此方法将抛出**indexout of boundsexception**。

以下是举例说明 *getFloat(int index)* 方法的例子:

**示例 1:**

```java
// Java program to demonstrate
// getFloat() method

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

            // putting the double value in the bytebuffer
            bb.asFloatBuffer()
                .put(12.3f)
                .put(28.44f);

            // rewind the Bytebuffer
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer: ");
            for (int i = 1; i <= capacity / 4; i++)
                System.out.print(bb.getFloat() + " ");

            // rewind the Bytebuffer
            bb.rewind();

            // Reads the Float at this buffer's current position
            // using getFloat() method
            float value = bb.getFloat(0);

            // print the float value
            System.out.println("\n\nByte Value: " + value);

            // Reads the  float at this buffer's next position
            // using getFloat() method
            float value1 = bb.getFloat(4);

            // print the float value
            System.out.println("\nNext Byte Value: " + value1);
        }

        catch (IndexOutOfBoundsException e) {

            System.out.println("\nindex is negative or smaller"
                               + " than the buffer's limit, "
                               + "minus seven");
            System.out.println("Exception Thrown : " + e);
        }
    }
}
```

**输出:**

```java
Original ByteBuffer: 
12.3 28.44 

Byte Value: 12.3

Next Byte Value: 28.44

```

**示例 2:**

```java
// Java program to demonstrate
// getFloat() method

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

            // putting the double value in the bytebuffer
            bb.asFloatBuffer()
                .put(12.3f)
                .put(28.44f);

            // rewind the Bytebuffer
            bb.rewind();

            // print the ByteBuffer
            System.out.println("Original ByteBuffer: ");
            for (int i = 1; i <= capacity / 4; i++)
                System.out.print(bb.getFloat() + " ");

            // rewind the Bytebuffer
            bb.rewind();

            // Reads the Float at this buffer's current position
            // using getFloat() method
            float value = bb.getFloat(0);

            // print the float value
            System.out.println("\n\nByte Value: " + value);

            // Reads the  float at this buffer's next position
            // using getFloat() method
            float value1 = bb.getFloat(6);

            // print the float value
            System.out.println("\nNext Byte Value: " + value1);
        }

        catch (IndexOutOfBoundsException e) {

            System.out.println("\nindex is negative or"
                               + " smaller than the buffer's "
                               + "limit, minus seven");
            System.out.println("Exception Thrown : " + e);
        }
    }
}
```

**输出:**

```java
Original ByteBuffer: 
12.3 28.44 

Byte Value: 12.3

index is negative or smaller than the buffer's limit, minus seven
Exception Thrown : java.lang.IndexOutOfBoundsException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/bytebuffer . html # getFloat-int-](https://docs.oracle.com/javase/9/docs/api/java/nio/ByteBuffer.html#getFloat-int-)