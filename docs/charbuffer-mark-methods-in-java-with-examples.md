# 用示例在 Java 中标记 CharBuffer()方法

> 原文:[https://www . geesforgeks . org/char buffer-mark-methods-in-Java-with-examples/](https://www.geeksforgeeks.org/charbuffer-mark-methods-in-java-with-examples/)

[java.nio.CharBuffer 类](https://www.geeksforgeeks.org/tag/java-charbuffer/)的**标记()**方法用于将该缓冲区的标记设置在其位置。

**语法:**

```java
public CharBuffer mark()
```

**返回值:**这个方法返回这个缓冲区。

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

            // try to call reset() to restore
            // to the position we marked
            cb.reset();

            // display position
            System.out.println("position after reset: "
                               + cb.position());
        }

        catch (InvalidMarkException e) {
            System.out.println("new position is less than "
                               + "the position we marked before ");
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
            cb.position(1);

            // display position
            System.out.println("position before reset: "
                               + cb.position());

            // try to call reset() to restore
            // to the position we marked
            cb.reset();

            // display position
            System.out.println("position after reset: "
                               + cb.position());
        }

        catch (InvalidMarkException e) {
            System.out.println("\nnew position is less than "
                               + "the position we marked before ");
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

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/nio/charbuffer . html # mark–](https://docs.oracle.com/javase/9/docs/api/java/nio/CharBuffer.html#mark--)