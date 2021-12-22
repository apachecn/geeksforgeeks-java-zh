# Java 中的 DoubleBuffer wrap()方法，示例

> 原文:[https://www . geesforgeks . org/double buffer-wrap-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doublebuffer-wrap-method-in-java-with-examples/)

### 换行(双[]数组)

**java.nio.DoubleBuff** er 类的 **wrap()** 方法用于将双数组包装到缓冲区中。新的缓冲区将由给定的双数组支持；也就是说，对缓冲区的修改将导致数组被修改，反之亦然。新缓冲区的容量和限制将为 array.length，其位置将为零，其标记将未定义。它的支持数组将是给定的数组，并且它的数组偏移量将为零。

**语法:**

```java
public static DoubleBuffer wrap(double[] array)
```

**参数:**该方法以**数组**作为参数，该数组将支持该缓冲区。

**返回值:**该方法返回**新的双缓冲区。**

下面是说明 wrap()方法的示例:

```java
// Java program to demonstrate
// wrap() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaire and initialize the float array
        double[] fbb = { 1.23D, 2.34D, 4.56D };

        // print the float array length
        System.out.println("Array length : " + fbb.length);

        // print the float array element
        System.out.println("\nArray element : "
                           + Arrays.toString(fbb));

        // wrap the float array into floatBuffer
        // using wrap() method
        DoubleBuffer doubleBuffer = DoubleBuffer.wrap(fbb);

        // Rewind the floatbuffer
        doubleBuffer.rewind();

        // print the float buffer
        System.out.println("\ndoubleBuffer : "
                           + Arrays.toString(doubleBuffer.array()));

        // print the DoubleBuffer capacity
        System.out.println("\ndoublebuffer capacity : "
                           + doubleBuffer.capacity());

        // print the DoubleBuffer position
        System.out.println("\ndoublebuffer position:  "
                           + doubleBuffer.position());
    }
}
```

**Output:**

```java
Array length : 3

Array element : [1.23, 2.34, 4.56]

doubleBuffer : [1.23, 2.34, 4.56]

doublebuffer capacity : 3

doublebuffer position:  0

```

### 换行(双[]数组，int 偏移量，int 长度)

新的缓冲区将由给定的双数组支持；也就是说，对缓冲区的修改将导致数组被修改，反之亦然。新缓冲区的容量将是 array.length，它的位置将被偏移，它的限制将是 offset + length，它的标记将是未定义的。它的支持数组将是给定的数组，并且它的数组偏移量将为零。

**语法:**

```java
public static FloatBuffer wrap (double[] array, int offset, int length)

```

**参数:**该方法取以下参数:

*   **数组:**将支持新缓冲区的数组。
*   **偏移量:**要使用的子阵列的偏移量；必须为非负且不大于数组长度。新缓冲区的位置将被设置为该值。
*   **长度:**要使用的子阵列的长度；必须为非负且不大于 array . length–offset。新缓冲区的限制将设置为偏移量+长度。

**返回值:**该方法返回**新的双缓冲区。**

**异常:**如果偏移和长度参数上的前提条件不成立，此方法将抛出**指数超出边界异常**。

下面是说明 wrap()方法的示例:

**实施例 1:**

```java
// Java program to demonstrate
// wrap() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declare and initialize the float array
        double[] fbb = { 1.23D, 2.34D, 4.56D };

        // print the float array length
        System.out.println("Array length : " + fbb.length);

        // print the float array element
        System.out.println("\nArray element : "
                           + Arrays.toString(fbb));

        // wrap the double array into floatBuffer
        // using wrap() method
        DoubleBuffer doubleBuffer = DoubleBuffer.wrap(fbb, 0,
                                                      fbb.length);

        // Rewind the doublebuffer
        doubleBuffer.rewind();

        // print the float buffer
        System.out.println("\ndoubleBuffer : "
                           + Arrays.toString(doubleBuffer.array()));

        // print the FloatBuffer capacity
        System.out.println("\ndoublebuffer capacity : "
                           + doubleBuffer.capacity());

        // print the FloatBuffer position
        System.out.println("\ndoublebuffer position:  "
                           + doubleBuffer.position());
    }
}
```

**Output:**

```java
Array length : 3

Array element : [1.23, 2.34, 4.56]

doubleBuffer : [1.23, 2.34, 4.56]

doublebuffer capacity : 3

doublebuffer position:  0

```

**示例 2:** 演示 IndexOutOfBoundsException

```java
// Java program to demonstrate
// asReadOnlyBuffer() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declare and initialize the Double array
        double[] fbb = { 1.23D, 2.34D, 4.56D };

        // print the Double array length
        System.out.println("Array length : " + fbb.length);

        // print the Double array element
        System.out.println("\nArray element : " + Arrays.toString(fbb));

        try {
            // wrap the Double array into floatBuffer
            // using wrap() method
            System.out.println("\nHere "
                               + "offset and length does not hold"
                               + " the required condition ");
            DoubleBuffer doubleBuffer = DoubleBuffer.wrap(fbb,
                                                          1,
                                                          fbb.length);

            // Rewind the Doublebuffer
            doubleBuffer.rewind();

            // print the Double buffer
            System.out.println("\ndoubleBuffer : "
                               + Arrays.toString(doubleBuffer.array()));

            // print the DoubleBuffer capacity
            System.out.println("\ndoublebuffer capacity : "
                               + doubleBuffer.capacity());

            // print the DoubleBuffer position
            System.out.println("\ndoublebuffer position:  "
                               + doubleBuffer.position());
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

Array element : [1.23, 2.34, 4.56]

Here offset and length does not hold the required condition 
Exception throws:  java.lang.IndexOutOfBoundsException

```