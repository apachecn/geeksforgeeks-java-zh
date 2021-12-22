# Java 中的 CharBuffer wrap()方法

> 原文:[https://www . geesforgeks . org/char buffer-wrap-method-in-Java/](https://www.geeksforgeeks.org/charbuffer-wrap-method-in-java/)

### 换行(char[ ]数组)

**java.nio.CharBuffer** 类的 **wrap()** 方法用于将字符数组包装到缓冲区中。新的缓冲区将由给定的 char 数组支持。因此，对缓冲区的任何修改都会导致数组被修改，反之亦然。新缓冲器的容量由*阵长*决定，其位置为零，标记未定义。它的支持数组将是给定的数组，并且它的数组偏移量将为零。

**语法:**

```
public static CharBuffer wrap(char[] array)
```

**参数:**该方法接受一个**数组**作为支持该缓冲区的参数。

**返回值:**该方法返回新的字符缓冲区。

以下是说明**包裹()**方法的示例:

**示例-1:**

```
// Java program to demonstrate
// wrap() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declare and initialize the char array
        char[] cbb = { 'a', 'b', 'c' };

        // print the char array length
        System.out.println("Array length : " + cbb.length);

        // print the char array element
        System.out.println("\nArray element : "
                           + Arrays.toString(cbb));

        // wrap the char array into charBuffer
        // using wrap() method
        CharBuffer charBuffer = CharBuffer.wrap(cbb);

        // Rewind the intbuffer
        charBuffer.rewind();

        // print the char buffer
        System.out.println("\ncharBuffer : "
                           + Arrays.toString(charBuffer.array()));

        // print the CharBuffer capacity
        System.out.println("\ncharbuffer capacity : "
                           + charBuffer.capacity());

        // print the CharBuffer position
        System.out.println("\ncharbuffer position: "
                           + charBuffer.position());
    }
}
```

**Output:**

```
Array length : 3

Array element : [a, b, c]

charBuffer : [a, b, c]

charbuffer capacity : 3

charbuffer position: 0

```

### 换行(char[ ]数组，int 偏移量，int 长度)

新的缓冲区将由给定的 char 数组支持。因此，对缓冲区的任何修改都会导致数组被修改，反之亦然。新缓冲器的容量由*数组决定，长度*，其位置将偏移，其极限将偏移+长度，其标记将未定义。它的支持数组将是给定的数组，并且它的数组偏移量将为零。

**语法:**

```
public static CharBuffer wrap(char[ ] array, int offset, int length)
```

**参数:**该方法取以下参数:

*   **数组:**将支持新缓冲区的数组。
*   **偏移量:**要使用的子阵列的偏移量；必须为非负且不大于数组长度。新缓冲区的位置将被设置为该值。
*   **长度:**要使用的子阵列的长度；必须为非负且不大于 array . length–offset。新缓冲区的限制将设置为偏移量+长度。

**返回值:**该方法返回新的字符缓冲区。

**抛出:**此方法抛出**指数超出边界异常**(如果偏移和长度参数的前提条件不成立)。

下面是说明 wrap()方法的示例:

**示例-1:**

```
// Java program to demonstrate
// wrap() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declare and initialize the char array
        char[] cbb = { 'a', 'b', 'c' };

        // print the char array length
        System.out.println("Array length : " + cbb.length);

        // print the char array element
        System.out.println("\nArray element : "
                           + Arrays.toString(cbb));

        // wrap the char array into charBuffer
        // using wrap() method
        CharBuffer charBuffer = CharBuffer.wrap(cbb, 0, cbb.length);
        // Rewind the intbuffer
        charBuffer.rewind();

        // print the char buffer
        System.out.println("\ncharBuffer : "
                           + Arrays.toString(charBuffer.array()));

        // print the CharBuffer capacity
        System.out.println("\ncharbuffer capacity : "
                           + charBuffer.capacity());

        // print the CharBuffer position
        System.out.println("\ncharbuffer position: "
                           + charBuffer.position());
    }
}
```

**Output:**

```
Array length : 3

Array element : [a, b, c]

charBuffer : [a, b, c]

charbuffer capacity : 3

charbuffer position: 0

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
        char[] cbb = { 'a', 'b', 'c' };

        // print the char array length
        System.out.println("Array length : " + cbb.length);

        // print the char array element
        System.out.println("\nArray element : " + Arrays.toString(cbb));

        try {
            // wrap the char array into charBuffer
            // using wrap() method
            System.out.println("\nHere "
                               + "offset and length does not hold"
                               + " the required condition ");
            CharBuffer charBuffer = CharBuffer.wrap(cbb, 1, cbb.length);

            // Rewind the intbuffer
            charBuffer.rewind();

            // print the char buffer
            System.out.println("\ncharBuffer : "
                               + Arrays.toString(charBuffer.array()));

            // print the CharBuffer capacity
            System.out.println("\ncharbuffer capacity : "
                               + charBuffer.capacity());

            // print the CharBuffer position
            System.out.println("\ncharbuffer position: "
                               + charBuffer.position());
        }
        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception throws: " + e);
        }
    }
}
```

**Output:**

```
Array length : 3

Array element : [a, b, c]

Here offset and length does not hold the required condition 
Exception throws: java.lang.IndexOutOfBoundsException

```