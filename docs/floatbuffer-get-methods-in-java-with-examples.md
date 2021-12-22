# Java 中的 FloatBuffer get()方法，示例

> 原文:[https://www . geeksforgeeks . org/float buffer-get-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/floatbuffer-get-methods-in-java-with-examples/)

### get()

**java.nio.FloatBuffer** 类的 **get()** 方法用于读取给定缓冲区当前位置的 float，然后递增该位置。

**语法:**

```
public abstract float get()
```

**返回值:**该方法返回缓冲区当前位置的浮点值。

**抛出:**此方法抛出**bufferenderflow exception**–如果缓冲区当前位置不小于其限制，则抛出此异常。

下面是说明 get()方法的示例:

**实施例 1:**

```
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
            FloatBuffer fb = FloatBuffer.allocate(capacity);

            // putting the value in floatbuffer
            fb.put(8.56F);
            fb.put(9.61F);
            fb.put(1.24F);
            fb.rewind();

            // print the FloatBuffer
            System.out.println("Original FloatBuffer:  "
                               + Arrays.toString(fb.array()));

            // Reads the float at this buffer's current position
            // using get() method
            float value = fb.get();

            // print the Float value
            System.out.println("\nFloat Value: " + value);

            // Reads the  float at this buffer's next position
            // using get() method
            float value1 = fb.get();

            // print the Float value
            System.out.print("\nNext Float Value: " + value1);
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

**Output:**

```
Original FloatBuffer:  [8.56, 9.61, 1.24, 0.0, 0.0]

Float Value: 8.56

Next Float Value: 9.61

```

**实施例 2:**

```
// Java program to demonstrate
// get() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the FloatBuffer
        int capacity = 3;

        // Creating the FloatBuffer
        try {

            // creating object of floatbuffer
            // and allocating size capacity
            FloatBuffer fb = FloatBuffer.allocate(capacity);

            // putting the value in floatbuffer
            fb.put(8.56F);
            fb.put(9.61F);

            // print the FloatBuffer
            System.out.println("Original FloatBuffer:  "
                               + Arrays.toString(fb.array()));

            // Reads the float at this buffer's current position
            // using get() method
            float value = fb.get();

            // print the Float value
            System.out.println("\nFloat Value: " + value);

            // Reads the  float at this buffer's next position
            // using get() method
            System.out.print("\nsince the buffer current position is incremented");
            System.out.print(" to greater than its limit ");

            float value1 = fb.get();

            // print the Float value
            System.out.print("\nNext Float Value: " + value1);
        }

        catch (IllegalArgumentException e) {

            System.out.println("\nIllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("\nReadOnlyBufferException catched");
        }

        catch (BufferUnderflowException e) {

            System.out.println("\nException throws : " + e);
        }
    }
}
```

**Output:**

```
Original FloatBuffer:  [8.56, 9.61, 0.0]

Float Value: 0.0

since the buffer current position is incremented to greater than its limit 
Exception throws : java.nio.BufferUnderflowException

```

### get(int 索引)

FloatBuffer 的 **get(int index)** 方法用于读取指定索引处的文章。

**语法:**

```
public abstract float get(int index)
```

**参数:**该方法以**指数**(将读取浮点数的指数)为参数。

**返回值:**该方法返回给定指标下的**浮点值**。

**异常:**此方法抛出**indexout of boundsexception**。如果索引为负或不小于缓冲区的限制，则会引发此异常。

以下是说明 get(int index)方法的示例:

**实施例 1:**

```
// Java program to demonstrate
// get(int index) method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the FloatBuffer
        int capacity = 3;

        // Creating the FloatBuffer
        try {

            // creating object of floatbuffer
            // and allocating size capacity
            FloatBuffer fb = FloatBuffer.allocate(capacity);

            // putting the value in floatbuffer
            fb.put(8.56F);
            fb.put(9.61F);
            fb.put(6.61F);

            // print the FloatBuffer
            System.out.println("Original FloatBuffer:  "
                               + Arrays.toString(fb.array()));

            // Reads the float at the index 0 of the floatbuffer
            // using get() method
            float value0 = fb.get(0);

            // print the Float value
            System.out.println("\nFloat Value at index 0: " + value0);

            // Reads the float at the index 1 of the floatbuffer
            // using get() method
            float value1 = fb.get(1);

            // print the Float value
            System.out.println("\nFloat Value at index 1: " + value1);

            // Reads the float at the index 2 of the floatbuffer
            // using get() method
            float value2 = fb.get(2);

            // print the Float value
            System.out.println("\nFloat Value at index 2: " + value2);
        }

        catch (IllegalArgumentException e) {

            System.out.println("\nIllegalArgumentException catched");
        }

        catch (IndexOutOfBoundsException e) {

            System.out.println("\nReadOnlyBufferException catched");
        }

        catch (BufferUnderflowException e) {

            System.out.println("\nException throws : " + e);
        }
    }
}
```

**Output:**

```
Original FloatBuffer:  [8.56, 9.61, 6.61]

Float Value at index 0: 8.56

Float Value at index 1: 9.61

Float Value at index 2: 6.61

```

**实施例 2:**

```
// Java program to demonstrate
// get() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the FloatBuffer
        int capacity = 3;

        // Creating the FloatBuffer
        try {

            // creating object of floatbuffer
            // and allocating size capacity
            FloatBuffer fb = FloatBuffer.allocate(capacity);

            // putting the value in floatbuffer
            fb.put(8.56F);
            fb.put(9.61F);
            fb.put(6.61F);

            // print the FloatBuffer
            System.out.println("Original FloatBuffer:  "
                               + Arrays.toString(fb.array()));

            // Reads the float at the index 0 of the floatbuffer
            // using get() method
            float value0 = fb.get(0);

            // print the Float value
            System.out.println("\nFloat Value at index 0: " + value0);

            // Reads the float at the index 1 of the floatbuffer
            // using get() method
            float value1 = fb.get(1);

            // print the Float value
            System.out.println("\nFloat Value at index 1: " + value1);

            // Reads the float at the index 2 of the floatbuffer
            // using get() method
            System.out.println("\nTrying to get the float"
                               + " of index greater than its limit ");
            float value2 = fb.get(4);

            // print the Float value
            System.out.println("\nFloat Value at index 2: " + value2);
        }

        catch (IllegalArgumentException e) {

            System.out.println("IllegalArgumentException catched");
        }

        catch (IndexOutOfBoundsException e) {

            System.out.println("Exception thrown: " + e);
        }

        catch (BufferUnderflowException e) {

            System.out.println("Exception throws : " + e);
        }
    }
}
```

**Output:**

```
Original FloatBuffer:  [8.56, 9.61, 6.61]

Float Value at index 0: 8.56

Float Value at index 1: 9.61

Trying to get the float of index greater than its limit 
Exception thrown: java.lang.IndexOutOfBoundsException

```