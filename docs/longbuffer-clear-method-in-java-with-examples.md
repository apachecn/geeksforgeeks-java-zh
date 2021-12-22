# Java 中的 LongBuffer clear()方法，带示例

> 原文:[https://www . geesforgeks . org/longbuffer-clear-method-in-Java-with-examples/](https://www.geeksforgeeks.org/longbuffer-clear-method-in-java-with-examples/)

**[Java . nio . longbuffer](https://www.geeksforgeeks.org/tag/java-longbuffer/)**类的 **clear()** 方法用来清除这个缓冲区。清除该缓冲区时，进行以下更改:

*   Set position to zero.
*   Set limit to capacity
*   The tag is discarded.

**语法:**

```java
public final LongBuffer clear()
```

**参数:**该方法不取任何参数。

**返回值:**该方法在清除 LongBuffer 实例中的所有数据后返回该 LongBuffer 实例。

以下是说明 clear()方法的示例:

**示例 1:**

```java
// Java program to demonstrate
// clear() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        try {

            long[] arr = { 10, 20, 30, 40 };

            // creating object of LongBuffer
            // and allocating size capacity
            LongBuffer lb
                = LongBuffer.wrap(arr);

            // try to set the position at index 2
            lb.position(2);

            // Set this buffer mark position
            // using mark() method
            lb.mark();

            // try to set the position at index 4
            lb.position(4);

            // display position
            System.out.println("position before reset: "
                               + lb.position());

            // try to call clear() to restore
            // to the position at index 0
            // by discarding the mark
            lb.clear();

            // display position
            System.out.println("position after reset: "
                               + lb.position());
        }

        catch (InvalidMarkException e) {
            System.out.println("new position is less than "
                               + "the position we "
                               + "marked before ");
            System.out.println("Exception throws: " + e);
        }
    }
}
```

**输出:**

```java
position before reset: 4
position after reset: 0

```

**示例 2:**

```java
// Java program to demonstrate
// clear() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        long[] arr = { 10, 20, 30, 40 };

        // creating object of LongBuffer
        // and allocating size capacity
        LongBuffer lb = LongBuffer.wrap(arr);

        // try to set the position at index 3
        lb.position(3);

        // display position
        System.out.println("position before clear: "
                           + lb.position());

        // try to call clear() to restore
        // to the position at index 0
        // by discarding the mark
        lb.clear();

        // display position
        System.out.println("position after clear: "
                           + lb.position());
    }
}
```

**输出:**

```java
position before clear: 3
position after clear: 0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/longbuffer . html](https://docs.oracle.com/javase/9/docs/api/java/nio/LongBuffer.html)