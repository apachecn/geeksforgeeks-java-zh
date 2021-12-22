# Java 中的 DoubleBuffer hasArray()方法，示例

> 原文:[https://www . geesforgeks . org/double buffer-hasarray-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doublebuffer-hasarray-method-in-java-with-examples/)

**java.nio.DoubleBuffer** 类的 **hasArray()** 方法用于确保给定的缓冲区是否由可访问的浮点数组支持。如果该缓冲区有可访问的后备数组，则返回 true，否则返回 false。如果此方法返回 true，则可以安全地调用 array()和 arrayOffset()方法，因为它们在支持数组上工作。

**语法:**

```java
public final boolean hasArray()
```

**返回:**如果且仅当该缓冲区由数组支持且不是只读的，则该方法将返回**真**。否则它返回**假。**

下面是一些示例来说明 hasArray()方法:

**示例 1:** 当缓冲区由数组支持时

```java
// Java program to demonstrate
// hasArray() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the DoubleBuffer
        int capacity = 10;

        // Creating the DoubleBuffer
        try {

            // creating object of Doublebuffer
            // and allocating size capacity
            DoubleBuffer fb = DoubleBuffer.allocate(capacity);

            // putting the value in Doublebuffer
            fb.put(8.56F);
            fb.put(2, 9.61F);
            fb.rewind();

            // checking DoubleBuffer fb is backed by array or not
            boolean isArray = fb.hasArray();

            // checking if else condition
            if (isArray)
                System.out.println("DoubleBuffer fb is"
                                   + " backed by array");
            else
                System.out.println("DoubleBuffer fb is"
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
DoubleBuffer fb is backed by array

```

**示例 2:** 当缓冲区由数组支持时

```java
// Java program to demonstrate
// hasArray() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the DoubleBuffer
        int capacity = 10;

        // Creating the DoubleBuffer
        try {

            // creating object of Doublebuffer
            // and allocating size capacity
            DoubleBuffer fb = DoubleBuffer.allocate(capacity);

            // putting the value in Doublebuffer
            fb.put(8.56F);
            fb.put(2, 9.61F);
            fb.rewind();

            // Creating a read-only copy of DoubleBuffer
            // using asReadOnlyBuffer() method
            DoubleBuffer fb1 = fb.asReadOnlyBuffer();

            // checking DoubleBuffer fb is backed by array or not
            boolean isArray = fb1.hasArray();

            // checking if else condition
            if (isArray)
                System.out.println("DoubleBuffer fb is"
                                   + " backed by array");
            else
                System.out.println("DoubleBuffer fb is"
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
DoubleBuffer fb is not backed by any array

```