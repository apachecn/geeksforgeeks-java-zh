# Java 中的 IntBuffer wrap()方法

> 原文:[https://www . geesforgeks . org/int buffer-wrap-method-in-Java/](https://www.geeksforgeeks.org/intbuffer-wrap-method-in-java/)

### 换行(int[]数组)

**java.nio.IntBuffer** 类的 **wrap()** 方法用于将 int 数组包装到缓冲区中。给定的 int 数组将支持新的缓冲区；也就是说，对缓冲区的修改将导致数组被修改，反之亦然。新缓冲区的容量和限制将为 array.length，其位置将为零，其标记将未定义。它的支持数组将是给定的数组，并且它的数组偏移量将为零。

**语法:**

```
public static IntBuffer wrap(int[] array)
```

**参数:**该方法以**数组**作为参数，该数组是将备份该缓冲区的数组。

**返回值:**该方法返回创建的**新 int 缓冲区**。

以下是说明**包裹()**方法的示例:

示例 1:

```
// Java program to demonstrate
// wrap() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declare and initialize the int array
        int[] ibb = { 1, 2, 3 };

        // print the int array length
        System.out.println("Array length : "
                           + ibb.length);

        // print the int array element
        System.out.println("\nArray element : "
                           + Arrays.toString(ibb));

        // wrap the int array into intBuffer
        // using wrap() method
        IntBuffer intBuffer = IntBuffer.wrap(ibb);

        // Rewind the intbuffer
        intBuffer.rewind();

        // print the int buffer
        System.out.println("\nintBuffer : "
                           + Arrays.toString(intBuffer.array()));

        // print the IntBuffer capacity
        System.out.println("\nintbuffer capacity : "
                           + intBuffer.capacity());

        // print the IntBuffer position
        System.out.println("\nintbuffer position:  "
                           + intBuffer.position());
    }
}
```

**Output:**

```
Array length : 3

Array element : [1, 2, 3]

intBuffer : [1, 2, 3]

intbuffer capacity : 3

intbuffer position:  0

```

### 换行(int[]数组，int 偏移量，int 长度)

wrap()方法将 int 数组包装到缓冲区中。给定的 int 数组将支持新的缓冲区；也就是说，对缓冲区的修改将导致数组被修改，反之亦然。新缓冲区的容量将是 array.length，它的位置将被偏移，它的限制将是 offset + length，它的标记将是未定义的。它的支持数组将是给定的数组，并且它的数组偏移量将为零。

**语法:**

```
public static IntBuffer 
    wrap (int[] array, int offset, int length)
```

**参数:**该方法取以下参数:

*   **数组:**将支持新缓冲区的数组。
*   **偏移量:**要使用的子阵列的偏移量；必须为非负且不大于数组长度。新缓冲区的位置将被设置为该值。
*   **长度:**要使用的子阵列的长度；必须为非负且不大于 array . length–offset。新缓冲区的限制将设置为偏移量+长度。

**返回值:**这个方法返回新的浮点缓冲区。

**抛出:**如果偏移和长度参数的前提条件不成立，该方法抛出**指数。**

下面是说明 wrap()方法的示例:

**实施例 1:**

```
// Java program to demonstrate
// wrap() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declare and initialize the int array
        int[] ibb = { 1, 2, 3 };

        // print the int array length
        System.out.println("Array length : " + ibb.length);

        // print the int array element
        System.out.println("\nArray element : "
                           + Arrays.toString(ibb));

        // wrap the int array into intBuffer
        // using wrap() method
        IntBuffer intBuffer = IntBuffer.wrap(ibb, 0,
                                             ibb.length);

        // Rewind the intbuffer
        intBuffer.rewind();

        // print the int buffer
        System.out.println("\nintBuffer : "
                           + Arrays.toString(intBuffer.array()));

        // print the IntBuffer capacity
        System.out.println("\nintbuffer capacity : "
                           + intBuffer.capacity());

        // print the IntBuffer position
        System.out.println("\nintbuffer position: "
                           + intBuffer.position());
    }
}
```

**Output:**

```
Array length : 3

Array element : [1, 2, 3]

intBuffer : [1, 2, 3]

intbuffer capacity : 3

intbuffer position: 0

```

**示例 2:** 演示空指针异常

```
// Java program to demonstrate
// wrap() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declare and initialize the float array
        int[] ibb = { 1, 2, 3 };

        // print the int array length
        System.out.println("Array length : "
                           + ibb.length);

        // print the int array element
        System.out.println("\nArray element : "
                           + Arrays.toString(ibb));

        try {
            // wrap the int array into intBuffer
            // using wrap() method
            System.out.println("\nHere "
                               + "offset and length does not hold"
                               + " the required condition ");

            IntBuffer intBuffer = IntBuffer.wrap(ibb,
                                                 1,
                                                 ibb.length);

            // Rewind the intbuffer
            intBuffer.rewind();

            // print the int buffer
            System.out.println("\nintBuffer : "
                               + Arrays.toString(intBuffer.array()));

            // print the IntBuffer capacity
            System.out.println("\nintbuffer capacity : "
                               + intBuffer.capacity());

            // print the IntBuffer position
            System.out.println("\nintbuffer position:  "
                               + intBuffer.position());
        }
        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception throws:  " + e);
        }
    }
}
```

**Output:**

```
Array length : 3

Array element : [1, 2, 3]

Here offset and length does not hold the required condition 
Exception throws:  java.lang.IndexOutOfBoundsException

```