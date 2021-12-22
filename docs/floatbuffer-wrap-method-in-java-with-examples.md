# Java 中的 FloatBuffer wrap()方法，示例

> 原文:[https://www . geeksforgeeks . org/float buffer-wrap-method-in-Java-with-examples/](https://www.geeksforgeeks.org/floatbuffer-wrap-method-in-java-with-examples/)

### 包装(浮点[]数组)

类的 **wrap()** 方法用于将浮点数组包装到缓冲区中。给定的浮点数组将支持新的缓冲区；也就是说，对缓冲区的修改将导致数组被修改，反之亦然。新缓冲区的容量和限制将为 array.length，其位置将为零，其标记将未定义。它的后备数组将是给定的数组，并且它的数组偏移量将为零。

**语法:**

```
public static FloatBuffer wrap(float[] array)
```

**参数:**该方法以**数组**(将备份该缓冲区的数组)为参数。

**返回值:**这个方法返回新的浮点缓冲区。

以下是说明**包裹()**方法的示例:

示例 1:

```
// Java program to demonstrate
// asReadOnlyBuffer() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declare and initialize the float array
        float[] fbb = { 1.23F, 2.34F, 4.56F };

        // print the float array length
        System.out.println("Array length : " + fbb.length);

        // print the float array element
        System.out.println("\nArray element : "
                           + Arrays.toString(fbb));

        // wrap the float array into floatBuffer
        // using wrap() method
        FloatBuffer floatBuffer = FloatBuffer.wrap(fbb);

        // Rewind the floatbuffer
        floatBuffer.rewind();

        // print the float buffer
        System.out.println("\nfloatBuffer : "
                           + Arrays.toString(floatBuffer.array()));

        // print the FloatBuffer capacity
        System.out.println("\nfloatbuffer capacity : "
                           + floatBuffer.capacity());

        // print the FloatBuffer position
        System.out.println("\nfloatbuffer position:  "
                           + floatBuffer.position());
    }
}
```

**Output:**

```
Array length : 3

Array element : [1.23, 2.34, 4.56]

floatBuffer : [1.23, 2.34, 4.56]

floatbuffer capacity : 3

floatbuffer position:  0

```

### 换行(float[]数组，int 偏移量，int 长度)

给定的浮点数组将支持新的缓冲区；也就是说，对缓冲区的修改将导致数组被修改，反之亦然。新缓冲区的容量将是 array.length，它的位置将被偏移，它的限制将是 offset + length，它的标记将是未定义的。它的支持数组将是给定的数组，并且它的数组偏移量将为零。

**语法:**

```
public static FloatBuffer wrap (float[] array, int offset, int length)
```

**参数:**该方法取以下参数:

*   **数组:**将支持新缓冲区的数组。
*   **偏移量:**要使用的子阵列的偏移量；必须为非负且不大于数组长度。新缓冲区的位置将被设置为该值。
*   **长度:**要使用的子阵列的长度；必须为非负且不大于 array . length–offset。新缓冲区的限制将设置为偏移量+长度。

**返回值:**这个方法返回新的浮点缓冲区。

**抛出:**此方法抛出**指数超出边界异常**(如果偏移和长度参数的前提条件不成立)。

下面是说明 wrap()方法的示例:

**实施例 1:**

```
// Java program to demonstrate
// asReadOnlyBuffer() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declare and initialize the float array
        float[] fbb = { 1.23F, 2.34F, 4.56F };

        // print the float array length
        System.out.println("Array length : " + fbb.length);

        // print the float array element
        System.out.println("\nArray element : "
                           + Arrays.toString(fbb));

        // wrap the float array into floatBuffer
        // using wrap() method
        FloatBuffer floatBuffer = FloatBuffer.wrap(fbb, 0,
                                                   fbb.length);

        // Rewind the floatbuffer
        floatBuffer.rewind();

        // print the float buffer
        System.out.println("\nfloatBuffer : "
                           + Arrays.toString(floatBuffer.array()));

        // print the FloatBuffer capacity
        System.out.println("\nfloatbuffer capacity : "
                           + floatBuffer.capacity());

        // print the FloatBuffer position
        System.out.println("\nfloatbuffer position:  "
                           + floatBuffer.position());
    }
}
```

**Output:**

```
Array length : 3

Array element : [1.23, 2.34, 4.56]

floatBuffer : [1.23, 2.34, 4.56]

floatbuffer capacity : 3

floatbuffer position:  0

```

**示例 2:** 演示空指针异常

```
// Java program to demonstrate
// asReadOnlyBuffer() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declare and initialize the float array
        float[] fbb = { 1.23F, 2.34F, 4.56F };

        // print the float array length
        System.out.println("Array length : " + fbb.length);

        // print the float array element
        System.out.println("\nArray element : " + Arrays.toString(fbb));

        try {
            // wrap the float array into floatBuffer
            // using wrap() method
            System.out.println("\nHere "
                               + "offset and length does not hold"
                               + " the required condition ");
            FloatBuffer floatBuffer = FloatBuffer.wrap(fbb,
                                                       1,
                                                       fbb.length);

            // Rewind the floatbuffer
            floatBuffer.rewind();

            // print the float buffer
            System.out.println("\nfloatBuffer : "
                               + Arrays.toString(floatBuffer.array()));

            // print the FloatBuffer capacity
            System.out.println("\nfloatbuffer capacity : "
                               + floatBuffer.capacity());

            // print the FloatBuffer position
            System.out.println("\nfloatbuffer position:  "
                               + floatBuffer.position());
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

Array element : [1.23, 2.34, 4.56]

Here offset and length does not hold the required condition 
Exception throws:  java.lang.IndexOutOfBoundsException

```