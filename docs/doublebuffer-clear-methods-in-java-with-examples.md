# Java 中的 DoubleBuffer clear()方法，示例

> 原文:[https://www . geesforgeks . org/double buffer-clear-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/doublebuffer-clear-methods-in-java-with-examples/)

**[Java . nio . charbuffer](https://www.geeksforgeeks.org/tag/java-charbuffer/)**类的 **clear()** 方法用于清除该缓冲区。清除该缓冲区时，进行以下更改:

*   Set position to zero.
*   Set limit to capacity
*   The tag is discarded.

**语法:**

```java
public final DoubleBuffer clear()
```

**返回值:**该方法在清除 DoubleBuffer 实例中的所有数据后返回该实例。

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

            double[] darr = { 2.5, 3.5, 4.5, 6.7 };

            // creating object of DoubleBuffer
            // and allocating size capacity
            DoubleBuffer db
                = DoubleBuffer.wrap(darr);

            // try to set the position at index 2
            db.position(2);

            // Set this buffer mark position
            // using mark() method
            db.mark();

            // try to set the position at index 4
            db.position(4);

            // display position
            System.out.println("position before reset: "
                               + db.position());

            // try to call clear() to restore
            // to the position at index 0
            // by discarding the mark
            db.clear();

            // display position
            System.out.println("position after reset: "
                               + db.position());
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

        double[] carr = { 2.4, 105.4, 13.9, 23.45d };

        // creating object of DoubleBuffer
        // and allocating size capacity
        DoubleBuffer db = DoubleBuffer.wrap(carr);

        // try to set the position at index 3
        db.position(3);

        // display position
        System.out.println("position before clear: "
                           + db.position());

        // try to call clear() to restore
        // to the position at index 0
        // by discarding the mark
        db.clear();

        // display position
        System.out.println("position after clear: "
                           + db.position());
    }
}
```

**输出:**

```java
position before clear: 3
position after clear: 0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/double buffer . html # clear–](https://docs.oracle.com/javase/9/docs/api/java/nio/DoubleBuffer.html#clear--)