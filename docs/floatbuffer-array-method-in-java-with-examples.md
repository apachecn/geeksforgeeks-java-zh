# Java 中的 FloatBuffer 数组()方法，带示例

> 原文:[https://www . geeksforgeeks . org/float buffer-array-method-in-Java-with-examples/](https://www.geeksforgeeks.org/floatbuffer-array-method-in-java-with-examples/)

**java.nio.FloatBuffer** 类的**数组()**方法用于返回支持该缓冲区的 float 数组。对此缓冲区内容的修改将导致返回数组的内容被修改，反之亦然。Invoke()在调用此方法之前使用 hasArray()方法，以确保此缓冲区具有可访问的后备数组

**语法:**

```
public final float[] array()
```

**返回值:**该方法返回支持该缓冲区的**数组**。

**抛出:**这个方法抛出**readonlybufferenexception**(如果这个缓冲区由数组支持，但是是只读的)

下面程序说明了**数组()**的方法:

**实施例 1:**

```
// Java program to demonstrate
// array() method

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

            // getting array from fb FloatBuffer using array() method
            float[] fbb = fb.array();

            // printing the FloatBuffer fb
            System.out.println("FloatBuffer:  "
                               + Arrays.toString(fbb));
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
FloatBuffer:  [8.56, 0.0, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]

```

**实施例 2:**

```
// Java program to demonstrate
// array() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the fb
        int capacity1 = 10;

        // Declaring the capacity of the fb1
        int capacity2 = 5;

        // Creating the FloatBuffer
        try {
            //
            // fb
            //
            // creating object of floatbuffer fb
            // and allocating size capacity
            FloatBuffer fb = FloatBuffer.allocate(capacity1);

            // putting the value in fb
            fb.put(9.56F);
            fb.put(2, 7.61F);
            fb.put(3, 4.61F);
            fb.rewind();

            // print the FloatBuffer
            System.out.println("FloatBuffer fb: "
                               + Arrays.toString(fb.array()));

            //
            // fb1
            //
            // creating object of floatbuffer fb1
            // and allocating size capacity
            FloatBuffer fb1 = FloatBuffer.allocate(capacity2);

            // putting the value in fb1
            fb1.put(1, 4.56F);
            fb1.put(2, 6.45F);
            fb1.rewind();

            // print the FloatBuffer
            System.out.println("\nFloatBuffer fb1:  "
                               + Arrays.toString(fb1.array()));

            // Creating a read-only copy of FloatBuffer
            // using asReadOnlyBuffer() method
            FloatBuffer readOnlyFb = fb.asReadOnlyBuffer();

            // print the FloatBuffer
            System.out.print("\nReadOnlyBuffer FloatBuffer: ");

            while (readOnlyFb.hasRemaining())
                System.out.print(readOnlyFb.get() + ", ");

            // try to change readOnlyFb
            System.out.println("\n\nTrying to get the array"
                               + " from ReadOnlyFb for editing");

            float[] fbarr = readOnlyFb.array();
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

```
FloatBuffer fb: [9.56, 0.0, 7.61, 4.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]

FloatBuffer fb1:  [0.0, 4.56, 6.45, 0.0, 0.0]

ReadOnlyBuffer FloatBuffer: 9.56, 0.0, 7.61, 4.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 

Trying to get the array from ReadOnlyFb for editing
Exception thrown: java.nio.ReadOnlyBufferException

```