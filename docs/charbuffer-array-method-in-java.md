# Java 中的 CharBuffer 数组()方法

> 原文:[https://www . geesforgeks . org/char buffer-array-in-method-Java/](https://www.geeksforgeeks.org/charbuffer-array-method-in-java/)

**java.nio.CharBuffer** 类的**数组()**方法用于返回支持该缓冲区的 char 数组。对此缓冲区内容所做的任何修改都会导致返回数组的内容也被修改，反之亦然。在调用此方法之前调用 hasArray()方法，以确保此缓冲区具有可访问的后备数组。

**语法:**

```java
public final char[] array()
```

**返回值:**该方法返回支持该缓冲区的**数组**。

**抛出:**这个方法抛出**readonlybufferenexception**(如果这个缓冲区由数组支持，但是是只读的)

下面程序说明了**数组()**的方法:

**例 1:**

```java
// Java program to demonstrate
// array() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the CharBuffer
        int capacity = 10;

        // Creating the CharBuffer
        try {

            // creating object of CharBuffer
            // and allocating size capacity
            CharBuffer cb = CharBuffer.allocate(capacity);

            // putting the value in CharBuffer
            cb.put('a');
            cb.put(2, 'b');
            cb.rewind();

            // getting array from cb
            // CharBuffer using array() method
            char[] cbb = cb.array();

            // printing the CharBuffer cb
            System.out.println("CharBuffer: "
                               + Arrays.toString(cbb));
        }

        catch (IllegalArgumentException e) {

            System.out.println("IllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("ReadOnlyBufferException catched");
        }
    }
}
```

**Output:**

```java
CharBuffer: [a, , b, , , , , , , ]

```

**例 2:**

```java
// Java program to demonstrate
// array() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the cb
        int capacity1 = 10;

        // Declaring the capacity of the cb1
        int capacity2 = 5;

        // Creating the CharBuffer
        try {
            //
            // cb
            //
            // creating object of CharBuffer cb
            // and allocating size capacity
            CharBuffer cb = CharBuffer.allocate(capacity1);

            // putting the value in cb
            cb.put('a');
            cb.put(2, 'b');
            cb.put(3, 'c');
            cb.rewind();

            // print the CharBuffer
            System.out.println("CharBuffer cb: "
                               + Arrays.toString(cb.array()));

            //
            // cb1
            //
            // creating object of CharBuffer cb1
            // and allocating size capacity
            CharBuffer cb1 = CharBuffer.allocate(capacity2);

            // putting the value in cb1
            cb1.put(1, 'd');
            cb1.put(2, 'e');
            cb1.rewind();

            // print the CharBuffer
            System.out.println("\nCharBuffer cb1: "
                               + Arrays.toString(cb1.array()));

            // Creating a read-only copy of CharBuffer
            // using asReadOnlyBuffer() method
            CharBuffer readOnlycb = cb.asReadOnlyBuffer();

            // print the CharBuffer
            System.out.print("\nReadOnlyBuffer CharBuffer: ");

            while (readOnlycb.hasRemaining())
                System.out.print(readOnlycb.get() + ", ");

            // try to change readOnlycb
            System.out.println("\n\nTrying to get the array"
                               + " from ReadOnlycb for editing");

            char[] cbarr = readOnlycb.array();
        }
        catch (IllegalArgumentException e) {
            System.out.println("IllegalArgumentException catched");
        }
        catch (ReadOnlyBufferException e) {
            System.out.println("Exception thrown: " + e);
        }
    }
}
```

**Output:**

```java
CharBuffer cb: [a,, b, c,,,,,, ]

CharBuffer cb1: [, d, e,, ]

ReadOnlyBuffer CharBuffer: a,, b, c,,,,,,, 

Trying to get the array from ReadOnlycb for editing
Exception thrown: java.nio.ReadOnlyBufferException

```