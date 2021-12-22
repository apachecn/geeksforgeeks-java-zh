# Java 中的 CharBuffer hasArray()方法

> 原文:[https://www . geesforgeks . org/char buffer-hasarray-method-in-Java/](https://www.geeksforgeeks.org/charbuffer-hasarray-method-in-java/)

**java.nio.CharBuffer** 类的 **hasArray()** 方法用于确保给定的缓冲区是否由可访问的 char 数组支持。如果该缓冲区有可访问的后备数组，则返回 true，否则返回 false。如果此方法返回 true，则可以安全地调用 array()和 arrayOffset()方法，因为它们在支持数组上工作。

**语法:**

```java
public final boolean hasArray()
```

**返回值:**当且仅当该缓冲区由数组支持且不是只读时，该方法将返回**真**。否则返回**假**。

以下是说明 **hasArray()** 方法的例子:

**示例 1:** 当缓冲区由数组支持时

```java
// Java program to demonstrate
// hasArray() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the CharBuffer
        int capacity = 10;

        // Creating the CharBuffer
        try {

            // creating object of Intbuffer
            // and allocating size capacity
            CharBuffer cb = CharBuffer.allocate(capacity);

            // putting the value in Intbuffer
            cb.put('a');
            cb.put(2, 'b');
            cb.rewind();

            // checking CharBuffer cb is backed by array or not
            boolean isArray = cb.hasArray();

            // checking if else condition
            if (isArray)
                System.out.println("CharBuffer cb is"
                                   + " backed by array");
            else
                System.out.println("CharBuffer cb is"
                                   + " not backed by any array");
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
CharBuffer cb is backed by array

```

**示例 2:** 当缓冲区没有数组支持时

```java
// Java program to demonstrate
// hasArray() method

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

            // Creating a read-only copy of CharBuffer
            // using asReadOnlyBuffer() method
            CharBuffer cb1 = cb.asReadOnlyBuffer();

            // checking CharBuffer cb is backed by array or not
            boolean isArray = cb1.hasArray();

            // checking if else condition
            if (isArray)
                System.out.println("CharBuffer cb is"
                                   + " backed by array");
            else
                System.out.println("CharBuffer cb is"
                                   + " not backed by any array");
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
CharBuffer cb is not backed by any array

```