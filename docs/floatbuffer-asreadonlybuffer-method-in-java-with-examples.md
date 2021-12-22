# Java 中的 FloatBuffer asReadOnlyBuffer()方法，示例

> 原文:[https://www . geesforgeks . org/float buffer-as readonly buffer-method-in-Java-with-examples/](https://www.geeksforgeeks.org/floatbuffer-asreadonlybuffer-method-in-java-with-examples/)

**java.nio.FloatBuffer 类**的 **asReadOnlyBuffer()** 方法用于用该缓冲区的内容创建一个新的**只读浮动缓冲区**。新缓冲区是该缓冲区的副本。因此，对此缓冲区内容所做的更改将在新缓冲区中可见。

由于新缓冲区是只读的，因此不允许对其内容进行任何修改。两个缓冲器的位置、极限和标记值将是独立的。新缓冲区的容量、限制、位置和标记值将与该缓冲区相同。如果此缓冲区本身是只读的，则此方法的行为方式与复制方法完全相同。

**语法:**

```
public abstract FloatBuffer asReadOnlyBuffer()
```

**返回值:**该方法返回**新的只读浮动缓冲区**，其内容与该缓冲区相同。

下面是说明 asReadOnlyBuffer()方法的示例:

**实施例 1:**

```
// Java program to demonstrate
// asReadOnlyBuffer() method

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

            // print the FloatBuffer
            System.out.println("Original FloatBuffer:  "
                               + Arrays.toString(fb.array()));

            // Creating a read-only copy of FloatBuffer
            // using asReadOnlyBuffer() method
            FloatBuffer floatBuffer = fb.asReadOnlyBuffer();

            // print the FloatBuffer
            System.out.print("\nReadOnlyBuffer FloatBuffer: ");

            while (floatBuffer.hasRemaining())
                System.out.print(floatBuffer.get() + ", ");
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
Original FloatBuffer:  [8.56, 0.0, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]

ReadOnlyBuffer FloatBuffer: 8.56, 0.0, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0,

```

**实施例 2:**

```
// Java program to demonstrate
// asReadOnlyBuffer() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args) throws Exception
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
            fb.put(8.56F);
            fb.put(2, 9.61F);
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
FloatBuffer fb: [8.56, 0.0, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]

FloatBuffer fb1:  [0.0, 4.56, 6.45, 0.0, 0.0]

ReadOnlyBuffer FloatBuffer: 8.56, 0.0, 9.61, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 

Trying to get the array from ReadOnlyFb for editing
Exception thrown: java.nio.ReadOnlyBufferException

```