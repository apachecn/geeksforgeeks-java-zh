# Java 中的 FloatBuffer hasArray()方法，示例

> 原文:[https://www . geeksforgeeks . org/float buffer-hasarray-method-in-Java-with-examples/](https://www.geeksforgeeks.org/floatbuffer-hasarray-method-in-java-with-examples/)

**java.nio.FloatBuffer** 类的 **hasArray()** 方法用于确保给定的缓冲区是否由可访问的 float 数组支持。如果该缓冲区有可访问的后备数组，则返回 true，否则返回 false。如果此方法返回 true，则可以安全地调用 array()和 arrayOffset()方法，因为它们在支持数组上工作。

**语法:**

```
public final boolean hasArray()
```

**返回:**如果且仅当该缓冲区由数组支持且不是只读的，则该方法将返回**真**。否则返回**假**。

以下是说明 **hasArray()** 方法的例子:

**示例 1:** 当缓冲区由数组支持时

```
// Java program to demonstrate
// hasArray() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the FloatBuffer
        int capacity = 10;

        // Creating the FloatBuffer
        try {

            // creating object of floatbuffer
            // and allocating size capacity
            FloatBuffer fb = FloatBuffer.allocate(capacity);

            // putting the value in floatbuffer
            fb.put(8.56F);
            fb.put(2, 9.61F);
            fb.rewind();

            // checking FloatBuffer fb is backed by array or not
            boolean isArray = fb.hasArray();

            // checking if else condition
            if (isArray)
                System.out.println("FloatBuffer fb is"
                                   + " backed by array");
            else
                System.out.println("FloatBuffer fb is"
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

```
FloatBuffer fb is backed by array

```

**示例 2:** 当缓冲区由数组支持时

```
// Java program to demonstrate
// hasArray() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the FloatBuffer
        int capacity = 10;

        // Creating the FloatBuffer
        try {

            // creating object of floatbuffer
            // and allocating size capacity
            FloatBuffer fb = FloatBuffer.allocate(capacity);

            // putting the value in floatbuffer
            fb.put(8.56F);
            fb.put(2, 9.61F);
            fb.rewind();

            // Creating a read-only copy of FloatBuffer
            // using asReadOnlyBuffer() method
            FloatBuffer fb1 = fb.asReadOnlyBuffer();

            // checking FloatBuffer fb is backed by array or not
            boolean isArray = fb1.hasArray();

            // checking if else condition
            if (isArray)
                System.out.println("FloatBuffer fb is"
                                   + " backed by array");
            else
                System.out.println("FloatBuffer fb is"
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

```
FloatBuffer fb is not backed by any array

```