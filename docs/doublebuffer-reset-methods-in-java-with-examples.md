# Java 中的 DoubleBuffer reset()方法，示例

> 原文:[https://www . geesforgeks . org/double buffer-reset-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/doublebuffer-reset-methods-in-java-with-examples/)

[java.nio.DoubleBuffer 类](https://www.geeksforgeeks.org/tag/java-doublebuffer/)的 **reset()** 方法用于将该缓冲区的位置重置到之前标记的位置。在这种情况下，既不会更改也不会丢弃标记的值。它有助于恢复缓冲区中以前标记的值。

**语法:**

```java
public final DoubleBuffer reset()
```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回这个缓冲区。

以下是说明 reset()方法的示例:

**示例 1:**

```java
// Java program to demonstrate
// reset() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        try {

            double[] darr = { 10.5, 20.5, 30.5, 40.5 };

            // creating object of DoubleBuffer
            // and allocating size capacity
            DoubleBuffer db = DoubleBuffer.wrap(darr);

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

            // try to call reset() to restore
            // to the position we marked
            db.reset();

            // display position
            System.out.println("position after reset: "
                               + db.position());
        }

        catch (InvalidMarkException e) {
            System.out.println("new position is less than "
                               + "the position we"
                               + " marked before ");
            System.out.println("Exception throws: " + e);
        }
    }
}
```

**输出:**

```java
position before reset: 4
position after reset: 2

```

**示例 2:**

```java
// Java program to demonstrate
// reset() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        try {

            double[] darr = { 10.5, 20.5, 30.5, 40.5 };

            // creating object of DoubleBuffer
            // and allocating size capacity
            DoubleBuffer db = DoubleBuffer.wrap(darr);

            // try to set the position at index 2
            db.position(2);

            // Set this buffer mark position
            // using mark() method
            db.mark();

            // try to set the position at index 4
            db.position(1);

            // display position
            System.out.println("position before reset: "
                               + db.position());

            // try to call reset() to restore
            // to the position we marked
            db.reset();

            // display position
            System.out.println("position after reset: "
                               + db.position());
        }

        catch (InvalidMarkException e) {
            System.out.println("\nnew position is less than "
                               + "the position we"
                               + " marked before ");
            System.out.println("Exception throws: " + e);
        }
    }
}
```

**输出:**

```java
position before reset: 1

new position is less than the position we marked before 
Exception throws: java.nio.InvalidMarkException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/double buffer . html # order–](https://docs.oracle.com/javase/9/docs/api/java/nio/DoubleBuffer.html#order--)