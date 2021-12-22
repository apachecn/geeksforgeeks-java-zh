# Java 中的 CharBuffer clear()方法，示例

> 原文:[https://www . geesforgeks . org/char buffer-clear-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/charbuffer-clear-methods-in-java-with-examples/)

**[Java . nio . charbuffer](https://www.geeksforgeeks.org/tag/java-charbuffer/)**类的 **clear()** 方法用于清除该缓冲区。位置设置为零，限制设置为容量，标记被丢弃。在使用一系列通道读取或放置操作来填充此缓冲区之前，请调用此方法。

**例如:**

```java

// Prepare buffer for reading
buf.clear();

// Read data
in.read(buf);

```

这种方法实际上并不擦除缓冲区中的数据，但它的命名就好像它擦除了数据一样，因为它最常用于这种情况。

**语法:**

```java
public final CharBuffer clear()
```

**返回值:**这个方法返回这个缓冲区。

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

            char[] carr = { 'a', 'b', 'c', 'd' };

            // creating object of CharBuffer
            // and allocating size capacity
            CharBuffer cb = CharBuffer.wrap(carr);

            // try to set the position at index 2
            cb.position(2);

            // Set this buffer mark position
            // using mark() method
            cb.mark();

            // try to set the position at index 4
            cb.position(4);

            // display position
            System.out.println("position before reset: "
                               + cb.position());

            // try to call clear() to restore
            // to the position at index 0
            // by discarding the mark
            cb.clear();

            // display position
            System.out.println("position after reset: "
                               + cb.position());
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

        char[] carr = { '.', '<', '@', 'a' };

        // creating object of CharBuffer
        // and allocating size capacity
        CharBuffer cb = CharBuffer.wrap(carr);

        // try to set the position at index 2
        cb.position(3);

        // display position
        System.out.println("position before clear: "
                           + cb.position());

        // try to call clear() to restore
        // to the position at index 0
        // by discarding the mark
        cb.clear();

        // display position
        System.out.println("position after clear: "
                           + cb.position());
    }
}
```

**输出:**

```java
position before clear: 3
position after clear: 0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charbuffer . html # clear–](https://docs.oracle.com/javase/9/docs/api/java/nio/CharBuffer.html#clear--)