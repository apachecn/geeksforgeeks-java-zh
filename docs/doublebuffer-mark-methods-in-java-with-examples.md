# Java 中的 DoubleBuffer 标记()方法，示例

> 原文:[https://www . geesforgeks . org/double buffer-mark-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/doublebuffer-mark-methods-in-java-with-examples/)

[java.nio.DoubleBuffer 类](https://www.geeksforgeeks.org/tag/java-doublebuffer/)的**标记()**方法用来标记这个 DoubleBuffer 的当前位置作为这个缓冲区的标记。

**语法:**

```java
public DoubleBuffer mark()
```

**返回值:**在当前位置设置缓冲区标记后，该方法返回该双缓冲区。

下面是说明 mark()方法的示例:

**示例 1:**

```java
// Java program to demonstrate
// mark() method

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
            System.out.println("New position "
                               + "is less than "
                               + "the position "
                               + "marked before ");
            System.out.println("Exception throws: "
                               + e);
        }
    }
}
```

**输出:**

```java
position before reset: 4
position after reset: 2

```

**示例 2:** 演示无效标记异常

```java
// Java program to demonstrate
// mark() method

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

            // try to set the position at index 1
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
            System.out.println("\nNew position "
                               + "is less than "
                               + "the position "
                               + "marked before ");
            System.out.println("Exception throws: "
                               + e);
        }
    }
}
```

**输出:**

```java
position before reset: 1

New position is less than the position marked before 
Exception throws: java.nio.InvalidMarkException

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/double buffer . html # mark–](https://docs.oracle.com/javase/9/docs/api/java/nio/DoubleBuffer.html#mark--)