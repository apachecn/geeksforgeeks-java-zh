# Java 中的 CharBuffer get()方法

> 原文:[https://www . geesforgeks . org/char buffer-get-methods-in-Java/](https://www.geeksforgeeks.org/charbuffer-get-methods-in-java/)

**java.nio.CharBuffer** 类的 **get()** 方法用于读取给定缓冲区当前位置的字符，然后递增该位置。

**语法:**

```
public abstract char get()
```

**返回值:**该方法返回缓冲区当前位置的字符值。

**异常:**此方法抛出*bufferenderflow exception*–如果缓冲区的当前位置不小于其限制，则抛出此异常。

以下是举例说明 **get()** 方法的例子:

**例 1:**

```
// Java program to demonstrate
// get() method
import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the CharBuffer
        int capacity = 5;

        // Creating the CharBuffer
        try {

            // creating object of Charbuffer
            // and allocating size capacity
            CharBuffer cb = CharBuffer.allocate(capacity);

            // putting the value in Charbuffer
            cb.put('a');
            cb.put('b');
            cb.put('c');
            cb.rewind();

            // print the CharBuffer
            System.out.println("Original CharBuffer: "
                               + Arrays.toString(cb.array()));

            // Reads the Int at this buffer's current position
            // using get() method
            char value = cb.get();

            // print the Int value
            System.out.println("Int Value: " + value);

            // Reads the Int at this buffer's next position
            // using get() method
            char value1 = cb.get();

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
Original CharBuffer: [a, b, c, , ]
Int Value: a
Next Int Value: b

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

        // Declaring the capacity of the CharBuffer
        int capacity = 3;

        // Creating the CharBuffer
        try {

            // creating object of Charbuffer
            // and allocating size capacity
            CharBuffer cb = CharBuffer.allocate(capacity);

            // putting the value in Charbuffer
            cb.put('a');
            cb.put('b');

            // print the CharBuffer
            System.out.println("Original CharBuffer: "
                               + Arrays.toString(cb.array()));

            // Reads the Char at this buffer's current position
            // using get() method
            char value = cb.get();

            // print the Char value
            System.out.println("Char Value: " + value);

            // Reads the Char at this buffer's next position
            // using get() method
            System.out.print("Since the buffer current position is incremented\n");
            System.out.print(" to greater than its limit ");

            char value1 = cb.get();

            // print the Char value
            System.out.print("Next Char Value: " + value1);
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
Original CharBuffer: [a, b, ]
Char Value: 
Since the buffer current position is incremented
to greater than its limit Exception throws : java.nio.BufferUnderflowException

```

### get(int 索引)

CharBuffer 的 **get(int index)** 方法用于读取指定索引处的文章。

**语法:**

```
public abstract char get(int index)
```

**参数:**该方法以**索引**(将读取字符的索引)为参数。

**返回值:**该方法返回给定索引处的**字符值**。

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

        // Declaring the capacity of the CharBuffer
        int capacity = 3;

        // Creating the CharBuffer
        try {

            // creating object of Charbuffer
            // and allocating size capacity
            CharBuffer cb = CharBuffer.allocate(capacity);

            // putting the value in Charbuffer
            cb.put('a');
            cb.put('b');
            cb.put('c');

            // print the CharBuffer
            System.out.println("Original CharBuffer: "
                               + Arrays.toString(cb.array()));

            // Reads the Char at the index 0 of the Charbuffer
            // using get() method
            char value0 = cb.get(0);

            // print the Char value
            System.out.println("Char Value at index 0: " + value0);

            // Reads the Char at the index 1 of the Charbuffer
            // using get() method
            char value1 = cb.get(1);

            // print the Char value
            System.out.println("Char Value at index 1: " + value1);

            // Reads the Char at the index 2 of the Charbuffer
            // using get() method
            char value2 = cb.get(2);

            // print the Char value
            System.out.println("Char Value at index 2: " + value2);
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
Original CharBuffer: [a, b, c]
Char Value at index 0: a
Char Value at index 1: b
Char Value at index 2: c

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

        // Declaring the capacity of the CharBuffer
        int capacity = 3;

        // Creating the CharBuffer
        try {

            // creating object of Charbuffer
            // and allocating size capacity
            CharBuffer cb = CharBuffer.allocate(capacity);

            // putting the value in Charbuffer
            cb.put('a');
            cb.put('b');
            cb.put('c');

            // print the CharBuffer
            System.out.println("Original CharBuffer: "
                               + Arrays.toString(cb.array()));

            // Reads the Char at the index 0 of the Charbuffer
            // using get() method
            char value0 = cb.get(0);

            // print the Char value
            System.out.println("Char Value at index 0: " + value0);

            // Reads the Char at the index 1 of the Charbuffer
            // using get() method
            char value1 = cb.get(1);

            // print the Char value
            System.out.println("Char Value at index 1: " + value1);

            // Reads the Char at the index 2 of the Charbuffer
            // using get() method
            System.out.println("Trying to get the Char"
                               + " of index greater than its limit ");
            char value2 = cb.get(4);

            // print the Char value
            System.out.println("Char Value at index 2: " + value2);
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
Original CharBuffer: [a, b, c]
Char Value at index 0: a
Char Value at index 1: b
Trying to get the Char of index greater than its limit 
Exception thrown: java.lang.IndexOutOfBoundsException

```