# Java 中的 LongBuffer wrap()方法

> 原文:[https://www . geesforgeks . org/longbuffer-wrap-method-in-Java/](https://www.geeksforgeeks.org/longbuffer-wrap-method-in-java/)

### 换行(长[]数组)

类的 **wrap()** 方法用来包装一个 Long 数组，Longo，一个缓冲区。新的缓冲区将由给定的长数组支持；也就是说，对缓冲区的修改将导致数组被修改，反之亦然。新缓冲区的容量和限制将为 array.length，其位置将为零，其标记将未定义。它的后备数组将是给定的数组，并且它的数组偏移量将为零。

**语法:**

```java
public static LongBuffer wrap(Long[] array)
```

**参数:**该方法以*数组*(将备份该缓冲区的数组)为参数。

**返回值:**该方法返回新的 Long 缓冲区。

以下程序说明了*包裹()*的方法:

**程序 1** :

```java
// Java program to demonstrate
// asReadOnlyBuffer() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declare and initialize the Long array
        long[] ibb = { 1L, 2L, 3L };

        // prLong the Long array length
        System.out.println("Array length : " + ibb.length);

        // prLong the Long array element
        System.out.println("\nArray element : "
                           + Arrays.toString(ibb));

        // wrap the Long array Longo LongBuffer
        // using wrap() method
        LongBuffer longBuffer = LongBuffer.wrap(ibb, 0, ibb.length);

        // Rewind the Longbuffer
        longBuffer.rewind();

        // prLong the Long buffer
        System.out.println("\nlongBuffer : "
                           + Arrays.toString(longBuffer.array()));

        // prLong the LongBuffer capacity
        System.out.println("\nlongbuffer capacity : "
                           + longBuffer.capacity());

        // prLong the LongBuffer position
        System.out.println("\nlongbuffer position: "
                           + longBuffer.position());
    }
}
```

**Output:**

```java
Array length : 3

Array element : [1, 2, 3]

LongBuffer : [1, 2, 3]

Longbuffer capacity : 3

Longbuffer position:  0

```

### 换行(长[]数组，长偏移量，长长度)

新的缓冲区将由给定的长数组支持；也就是说，对缓冲区的修改将导致数组被修改，反之亦然。新缓冲区的容量将是 array.length，它的位置将被偏移，它的限制将是 offset + length，它的标记将是未定义的。它的后备数组将是给定的数组，并且它的数组偏移量将为零。

**语法:**

```java
public static LongBuffer wrap (Long[] array, Long offset, Long length)
```

**参数:**该方法取以下参数:

*   **数组:**将支持新缓冲区的数组。
*   **偏移量:**要使用的子阵列的偏移量；必须为非负且不大于数组长度。新缓冲区的位置将被设置为该值。
*   **长度:**要使用的子阵列的长度；必须为非负且不大于 array . length–offset。新缓冲区的限制将设置为偏移量+长度。

**返回值:**这个方法返回新的浮点缓冲区。

**抛出:**此方法抛出**指数超出边界异常**(如果偏移和长度参数的前提条件不成立)。

下面的程序说明了 wrap()方法:

**程序 1:**

```java
// Java program to demonstrate
// asReadOnlyBuffer() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declare and initialize the Long array
        long[] ibb = { 1, 2, 3 };

        // prLong the Long array length
        System.out.println("Array length : " + ibb.length);

        // prLong the Long array element
        System.out.println("\nArray element : "
                           + Arrays.toString(ibb));

        // wrap the Long array Longo LongBuffer
        // using wrap() method
        LongBuffer longBuffer = LongBuffer.wrap(ibb, 0,
                                                ibb.length);

        // Rewind the Longbuffer
        longBuffer.rewind();

        // prLong the Long buffer
        System.out.println("\nLongBuffer : "
                           + Arrays.toString(longBuffer.array()));

        // prLong the LongBuffer capacity
        System.out.println("\nLongbuffer capacity : "
                           + longBuffer.capacity());

        // prLong the LongBuffer position
        System.out.println("\nLongbuffer position: "
                           + longBuffer.position());
    }
}
```

**Output:**

```java
Array length : 3

Array element : [1, 2, 3]

LongBuffer : [1, 2, 3]

Longbuffer capacity : 3

Longbuffer position:  0

```

**程序 2:** 演示空值异常。

```java
// Java program to demonstrate
// asReadOnlyBuffer() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declare and initialize the float array
        long[] ibb = { 1, 2, 3 };

        // prLong the Long array length
        System.out.println("Array length : " + ibb.length);

        // prLong the Long array element
        System.out.println("\nArray element : " + Arrays.toString(ibb));

        try {
            // wrap the Long array Longo LongBuffer
            // using wrap() method
            System.out.println("\nHere "
                               + "offset and length does not hold"
                               + " the required condition ");
            LongBuffer longBuffer = LongBuffer.wrap(ibb,
                                                    1,
                                                    ibb.length);

            // Rewind the Longbuffer
            longBuffer.rewind();

            // prLong the Long buffer
            System.out.println("\nLongBuffer : "
                               + Arrays.toString(longBuffer.array()));

            // prLong the LongBuffer capacity
            System.out.println("\nLongbuffer capacity : "
                               + longBuffer.capacity());

            // prLong the LongBuffer position
            System.out.println("\nLongbuffer position:  "
                               + longBuffer.position());
        }
        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception throws:  " + e);
        }
    }
}
```

**Output:**

```java
Array length : 3

Array element : [1, 2, 3]

Here offset and length does not hold the required condition 
Exception throws:  java.lang.IndexOutOfBoundsException

```