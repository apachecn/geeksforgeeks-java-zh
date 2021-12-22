# Java 中的 DoubleBuffer get()方法，示例

> 原文:[https://www . geesforgeks . org/double buffer-get-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/doublebuffer-get-methods-in-java-with-examples/)

[java.nio.DoubleBuffer](https://www.geeksforgeeks.org/tag/java-doublebuffer/) 类的 **get()** 方法用于读取给定缓冲区当前位置的 double，然后递增该位置。

**语法:**

```java
public abstract double get()
```

**返回值:**该方法返回缓冲区当前位置的双精度值。

**异常:**此方法抛出**bufferenderflow Exception**如果缓冲区当前位置不小于其极限，则抛出此异常。

下面是说明 get()方法的示例:

**示例 1:**

```java
// Java program to demonstrate
// get() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the FloatBuffer
        int capacity = 5;

        // Creating the FloatBuffer
        try {

            // creating object of floatbuffer
            // and allocating size capacity
            DoubleBuffer fb
                = DoubleBuffer.allocate(capacity);

            // putting the value in Doublebuffer
            fb.put(8.56D);
            fb.put(9.61D);
            fb.put(1.24D);
            fb.rewind();

            // print the DoubleBuffer
            System.out.println("Original DoubleBuffer:  "
                               + Arrays.toString(fb.array()));

            // Reads the double at this buffer's current position
            // using get() method
            double value = fb.get();

            // print the double value
            System.out.println("\nDouble Value: "
                               + value);

            // Reads the  double at this buffer's next position
            // using get() method
            double value1 = fb.get();

            // print the double value
            System.out.print("\nNext double Value: " + value1);
        }

        catch (IllegalArgumentException e) {

            System.out.println("\nIllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("\nReadOnlyBufferException catched");
        }

        catch (BufferUnderflowException e) {

            System.out.println("\nException throws: " + e);
        }
    }
}
```

**输出:**

```java
Original DoubleBuffer:  [8.56, 9.61, 1.24, 0.0, 0.0]

Double Value: 8.56

Next double Value: 9.61

```

**示例 2:**

```java
// Java program to demonstrate
// get() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the DoubleBuffer
        int capacity = 3;

        // Creating the DoubleBuffer
        try {

            // creating object of Doublebuffer
            // and allocating size capacity
            DoubleBuffer fb = DoubleBuffer.allocate(capacity);

            // putting the value in Doublebuffer
            fb.put(8.56F);
            fb.put(9.61F);

            // print the DoubleBuffer
            System.out.println("Original DoubleBuffer:  "
                               + Arrays.toString(fb.array()));

            // Reads the Double at this buffer's current position
            // using get() method
            Double value = fb.get();

            // print the Double value
            System.out.println("\nDouble Value: " + value);

            // Reads the  Double at this buffer's next position
            // using get() method
            System.out.print("\nsince the buffer current"
                             + " position is incremented");
            System.out.print(" to greater than its limit ");

            Double value1 = fb.get();

            // print the Double value
            System.out.print("\nNext Double Value: " + value1);
        }

        catch (IllegalArgumentException e) {

            System.out.println("\nIllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("\nReadOnlyBufferException catched");
        }

        catch (BufferUnderflowException e) {

            System.out.println("\nException throws: " + e);
        }
    }
}
```

**输出:**

```java
Original DoubleBuffer:  [8.5600004196167, 9.609999656677246, 0.0]

Double Value: 0.0

since the buffer current position is incremented to greater than its limit 
Exception throws: java.nio.BufferUnderflowException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/double buffer . html # get–](https://docs.oracle.com/javase/9/docs/api/java/nio/DoubleBuffer.html#get--)