# Java 中的 LongBuffer get()方法

> 原文:[https://www . geesforgeks . org/longbuffer-get-methods-in-Java/](https://www.geeksforgeeks.org/longbuffer-get-methods-in-java/)

### get()

类的 **get()** 方法用于读取给定缓冲区当前位置的龙，然后增加位置。

**语法:**

```java
public abstract Long get()
```

**返回值:**该方法返回缓冲区当前位置的 Long 值。

**抛出:**此方法抛出*bufferenderflow exception*–如果缓冲区当前位置不小于其限制，则抛出此异常。

下面是说明 get()方法的示例:

**例 1:**

```java
// Java program to demonstrate
// get() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the LongBuffer
        int capacity = 5;

        // Creating the LongBuffer
        try {

            // creating object of Longbuffer
            // and allocating size capacity
            LongBuffer ib = LongBuffer.allocate(capacity);

            // putting the value in Longbuffer
            ib.put(8);
            ib.put(9);
            ib.put(1);
            ib.rewind();

            // prLong the LongBuffer
            System.out.println("Original LongBuffer:  "
                               + Arrays.toString(ib.array()));

            // Reads the Long at this buffer's current position
            // using get() method
            Long value = ib.get();

            // prLong the Long value
            System.out.println("Long Value: " + value);

            // Reads the  Long at this buffer's next position
            // using get() method
            Long value1 = ib.get();

            // prLong the Long value
            System.out.print("Next Long Value: " + value1);
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

```java
Original LongBuffer:  [8, 9, 1, 0, 0]
Long Value: 8
Next Long Value: 9

```

**例 2:**

```java
// Java program to demonstrate
// get() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the LongBuffer
        int capacity = 3;

        // Creating the LongBuffer
        try {

            // creating object of Longbuffer
            // and allocating size capacity
            LongBuffer ib = LongBuffer.allocate(capacity);

            // putting the value in Longbuffer
            ib.put(8);
            ib.put(9);

            // prLong the LongBuffer
            System.out.println("Original LongBuffer:  "
                               + Arrays.toString(ib.array()));

            // Reads the Long at this buffer's current position
            // using get() method
            Long value = ib.get();

            // prLong the Long value
            System.out.println("Long Value: " + value);

            // Reads the  Long at this buffer's next position
            // using get() method
            System.out.print("Since the buffer current position is incremented");
            System.out.print(" to greater than its limit ");

            Long value1 = ib.get();

            // prLong the Long value
            System.out.print("Next Long Value: " + value1);
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

```java
Original LongBuffer:  [8, 9, 0]
Long Value: 0
Since the buffer current position is incremented to greater than its limit Exception throws : java.nio.BufferUnderflowException

```

### get(长索引)

LongBuffer 的 **get(Long index)** 方法用于读取指定索引处的文章。

**语法:**

```java
public abstract Long get(Long index)
```

**参数:**该方法以*指标*(读取龙的指标)为参数。

**返回值:**该方法返回给定索引处的 Long 值。

**异常:**此方法抛出*indexout of boundsexception*。如果索引为负或不小于缓冲区的限制，则会引发此异常。

以下是说明 get(长索引)方法的示例:

**例 1:**

```java
// Java program to demonstrate
// get(Long index) method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the LongBuffer
        int capacity = 3;

        // Creating the LongBuffer
        try {

            // creating object of Longbuffer
            // and allocating size capacity
            LongBuffer ib = LongBuffer.allocate(capacity);

            // putting the value in Longbuffer
            ib.put(8);
            ib.put(9);
            ib.put(6);

            // prLong the LongBuffer
            System.out.println("Original LongBuffer:  "
                               + Arrays.toString(ib.array()));

            // Reads the Long at the index 0 of the Longbuffer
            // using get() method
            Long value0 = ib.get(0);

            // prLong the Long value
            System.out.println("Long Value at index 0: " + value0);

            // Reads the Long at the index 1 of the Longbuffer
            // using get() method
            Long value1 = ib.get(1);

            // prLong the Long value
            System.out.println("Long Value at index 1: " + value1);

            // Reads the Long at the index 2 of the Longbuffer
            // using get() method
            Long value2 = ib.get(2);

            // prLong the Long value
            System.out.println("Long Value at index 2: " + value2);
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

```java
Original LongBuffer:  [8, 9, 6]
Long Value at index 0: 8
Long Value at index 1: 9
Long Value at index 2: 6

```

**例 2:**

```java
// Java program to demonstrate
// get() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the LongBuffer
        int capacity = 3;

        // Creating the LongBuffer
        try {

            // creating object of Longbuffer
            // and allocating size capacity
            LongBuffer ib = LongBuffer.allocate(capacity);

            // putting the value in Longbuffer
            ib.put(6);
            ib.put(8);
            ib.put(12);

            // prLong the LongBuffer
            System.out.println("Original LongBuffer:  "
                               + Arrays.toString(ib.array()));

            // Reads the Long at the index 0 of the Longbuffer
            // using get() method
            Long value0 = ib.get(0);

            // prLong the Long value
            System.out.println("Long Value at index 0: " + value0);

            // Reads the Long at the index 1 of the Longbuffer
            // using get() method
            Long value1 = ib.get(1);

            // prLong the Long value
            System.out.println("Long Value at index 1: " + value1);

            // Reads the Long at the index 2 of the Longbuffer
            // using get() method
            System.out.println("Trying to get the Long"
                               + " of index greater than its limit ");
            Long value2 = ib.get(4);

            // prLong the Long value
            System.out.println("Long Value at index 2: " + value2);
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

```java
Original LongBuffer:  [6, 8, 12]
Long Value at index 0: 6
Long Value at index 1: 8
Trying to get the Long of index greater than its limit 
Exception thrown: java.lang.IndexOutOfBoundsException

```