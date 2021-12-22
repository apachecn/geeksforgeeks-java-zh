# Java 中的 IntBuffer get()方法| Set 1

> 原文:[https://www . geesforgeks . org/int buffer-get-methods-in-Java-set-1/](https://www.geeksforgeeks.org/intbuffer-get-methods-in-java-set-1/)

### get()

**java.nio.IntBuffer** 类的 **get()** 方法用于读取给定缓冲区当前位置的 int，然后递增该位置。

**语法:**

```
public abstract int get()
```

**返回值:**该方法返回缓冲区当前位置的 int 值。

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

        // Declaring the capacity of the IntBuffer
        int capacity = 5;

        // Creating the IntBuffer
        try {

            // creating object of Intbuffer
            // and allocating size capacity
            IntBuffer ib = IntBuffer.allocate(capacity);

            // putting the value in Intbuffer
            ib.put(8);
            ib.put(9);
            ib.put(1);
            ib.rewind();

            // print the IntBuffer
            System.out.println("Original IntBuffer:  "
                               + Arrays.toString(ib.array()));

            // Reads the Int at this buffer's current position
            // using get() method
            int value = ib.get();

            // print the Int value
            System.out.println("Int Value: " + value);

            // Reads the  Int at this buffer's next position
            // using get() method
            int value1 = ib.get();

            // print the Int value
            System.out.print("Next Int Value: " + value1);
        }

        catch (IllegalArgumentException e) {

            System.out.println("IllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("ReadOnlyBufferException catched");
        }

        catch (BufferUnderflowException e) {

            System.out.println("Exception throws: " + e);
        }
    }
}
```

**Output:**

```
Original IntBuffer:  [8, 9, 1, 0, 0]
Int Value: 8
Next Int Value: 9

```

**示例 2:** 演示 Java . nio . bufferenderflow exception

```
// Java program to demonstrate
// get() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the IntBuffer
        int capacity = 3;

        // Creating the IntBuffer
        try {

            // creating object of Intbuffer
            // and allocating size capacity
            IntBuffer ib = IntBuffer.allocate(capacity);

            // putting the value in Intbuffer
            ib.put(8);
            ib.put(9);

            // print the IntBuffer
            System.out.println("Original IntBuffer:  "
                               + Arrays.toString(ib.array()));

            // Reads the Int at this buffer's current position
            // using get() method
            int value = ib.get();

            // print the Int value
            System.out.println("Int Value: " + value);

            // Reads the  Int at this buffer's next position
            // using get() method
            System.out.print("Since the buffer current position is incremented");
            System.out.print(" to greater than its limit ");

            int value1 = ib.get();

            // print the Int value
            System.out.print("Next Int Value: " + value1);
        }

        catch (IllegalArgumentException e) {

            System.out.println("IllegalArgumentException catched");
        }

        catch (ReadOnlyBufferException e) {

            System.out.println("ReadOnlyBufferException catched");
        }

        catch (BufferUnderflowException e) {

            System.out.println("Exception throws : " + e);
        }
    }
}
```

**Output:**

```
Original IntBuffer:  [8, 9, 0]
Int Value: 0

Since the buffer current position is incremented to greater than its limit Exception throws : java.nio.BufferUnderflowException

```

### get(int 索引)

IntBuffer 的 **get(int index)** 方法用于读取指定索引处的文章。

**语法:**

```
public abstract int get(int index)
```

**参数:**该方法以**索引**(从中读取 int 的索引)为参数。

**返回值:**该方法返回给定索引处的**整数值**。

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

        // Declaring the capacity of the IntBuffer
        int capacity = 3;

        // Creating the IntBuffer
        try {

            // creating object of Intbuffer
            // and allocating size capacity
            IntBuffer ib = IntBuffer.allocate(capacity);

            // putting the value in Intbuffer
            ib.put(8);
            ib.put(9);
            ib.put(6);

            // print the IntBuffer
            System.out.println("Original IntBuffer:  "
                               + Arrays.toString(ib.array()));

            // Reads the Int at the index 0 of the Intbuffer
            // using get() method
            int value0 = ib.get(0);

            // print the Int value
            System.out.println("Int Value at index 0: " + value0);

            // Reads the Int at the index 1 of the Intbuffer
            // using get() method
            int value1 = ib.get(1);

            // print the Int value
            System.out.println("Int Value at index 1: " + value1);

            // Reads the Int at the index 2 of the Intbuffer
            // using get() method
            int value2 = ib.get(2);

            // print the Int value
            System.out.println("Int Value at index 2: " + value2);
        }

        catch (IllegalArgumentException e) {
            System.out.println("IllegalArgumentException catched");
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("ReadOnlyBufferException catched");
        }

        catch (BufferUnderflowException e) {
            System.out.println("Exception throws : " + e);
        }
    }
}
```

**Output:**

```
Original IntBuffer:  [8, 9, 6]
Int Value at index 0: 8
Int Value at index 1: 9
Int Value at index 2: 6

```

**示例 2:** 演示 IndexOutOfBoundsException

```
// Java program to demonstrate
// get() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the IntBuffer
        int capacity = 3;

        // Creating the IntBuffer
        try {

            // creating object of Intbuffer
            // and allocating size capacity
            IntBuffer ib = IntBuffer.allocate(capacity);

            // putting the value in Intbuffer
            ib.put(6);
            ib.put(8);
            ib.put(12);

            // print the IntBuffer
            System.out.println("Original IntBuffer:  "
                               + Arrays.toString(ib.array()));

            // Reads the Int at the index 0 of the Intbuffer
            // using get() method
            int value0 = ib.get(0);

            // print the Int value
            System.out.println("Int Value at index 0: " + value0);

            // Reads the Int at the index 1 of the Intbuffer
            // using get() method
            int value1 = ib.get(1);

            // print the Int value
            System.out.println("Int Value at index 1: " + value1);

            // Reads the Int at the index 2 of the Intbuffer
            // using get() method
            System.out.println("Trying to get the Int"
                               + " of index greater than its limit ");
            int value2 = ib.get(4);

            // print the Int value
            System.out.println("Int Value at index 2: " + value2);
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
Original IntBuffer:  [6, 8, 12]
Int Value at index 0: 6
Int Value at index 1: 8

Trying to get the Int of index greater than its limit 
Exception thrown: java.lang.IndexOutOfBoundsException

```