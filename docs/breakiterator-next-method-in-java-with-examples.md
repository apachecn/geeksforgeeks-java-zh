# Java 中的 BreakIterator next()方法，示例

> 原文:[https://www . geeksforgeeks . org/breakiterator-next-method-in-Java-with-examples/](https://www.geeksforgeeks.org/breakiterator-next-method-in-java-with-examples/)

**java.text.BreakIterator** 类的 **next()** 方法用于获取当前边界(通过调用 current()方法检索的边界)之前的下一个边界的索引。它提供边界的第一个字符的偏移量，该偏移量跟随 BreakIterator 指向的当前边界。

**语法:**

```java
public abstract int next()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法提供当前边界之后的下一个边界的**索引**。

以下是说明 **next()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate next() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing with zero
        int current = 0, next = 0;

        // creating and initializing BreakIterator
        BreakIterator wb
            = BreakIterator.getWordInstance();

        // setting text for BreakIterator
        wb.setText("Code  Geeks");

        // getting the current text boundary
        current = wb.current();

        // display the result
        System.out.println(
            "current position before"
            + " calling next() : "
            + current);

        // calling next method
        next = wb.next();

        // display the result
        System.out.println(
            "\ncurrent position after"
            + " calling 1st next() : "
            + next);

        // calling next method
        next = wb.next();

        // display the result
        System.out.println(
            "\ncurrent position after"
            + " calling 2nd next() : "
            + next);
    }
}
```

**输出:**

```java
current position before calling next() : 0

current position after calling 1st next() : 4

current position after calling 2nd next() : 6

```

**例 2:**

```java
// Java program to demonstrate next() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing with zero
        int current = 0, next = 0;

        // creating and initializing BreakIterator
        BreakIterator wb
            = BreakIterator.getWordInstance();

        // setting text for BreakIterator
        wb.setText("GeeksForGeeks");

        // getting the current text boundary
        current = wb.current();

        // display the result
        System.out.println(
            "current position before"
            + " calling next() : "
            + current);

        // calling next method
        next = wb.next();

        // display the result
        System.out.println(
            "\ncurrent position after"
            + " calling 1st next() : "
            + next);

        // calling next method
        next = wb.next();

        // display the result
        System.out.println(
            "\ncurrent position after"
            + " calling 2nd next() : "
            + next);
    }
}
```

**输出:**

```java
current position before calling next() : 0

current position after calling 1st next() : 13

current position after calling 2nd next() : -1

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/breakiterator . html # next–](https://docs.oracle.com/javase/9/docs/api/java/text/BreakIterator.html#next--)