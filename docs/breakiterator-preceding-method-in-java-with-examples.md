# Java 中 BreakIterator 前置()方法，示例

> 原文:[https://www . geeksforgeeks . org/breakiterator-previous-method-in-Java-with-examples/](https://www.geeksforgeeks.org/breakiterator-preceding-method-in-java-with-examples/)

**java.text.BreakIterator** 类的**previous()**方法用于获取指定字符偏移量边界之前的最后一个边界的字符索引。它提供边界的第一个字符的偏移量，该偏移量在 BreakIterator 指向的当前边界之后或之前。

**语法:**

```java
public int preceding(int offset)
```

**参数:**取字符的**偏移量**，必须为其找到上一个边界。

**返回值:**该方法提供指定字符偏移量之前的边界的**索引**。

**异常:**如果指定的索引小于第一个文本边界或大于最后一个文本边界，此方法将抛出***IllegalArgumentException***。

以下是示例，说明前面的**()**方法:

**例 1:**

```java
// Java program to demonstrate preceding() method

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

        // setting the current position to 11
        // by skipping 3 boundaries
        wb.next(3);

        // getting the current text boundary
        current = wb.current();

        // display the result
        System.out.println(
            "current position before"
            + " calling preceding() : "
            + current);

        // calling preceding() method
        next = wb.preceding(6);

        // display the result
        System.out.println(
            "\ncurrent position after"
            + " calling 1st preceding() : "
            + next);

        // calling preceding() method
        next = wb.preceding(11);

        // display the result
        System.out.println(
            "\ncurrent position after"
            + " calling 2nd preceding() : "
            + next);
    }
}
```

**输出:**

```java
current position before calling preceding() : 11

current position after calling 1st preceding() : 4

current position after calling 2nd preceding() : 6

```

**例 2:**

```java
// Java program to demonstrate preceding() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            // creating and initializing with zero
            int current = 0, next = 0;

            // creating and initializing BreakIterator
            BreakIterator wb
                = BreakIterator.getWordInstance();

            // setting text for BreakIterator
            wb.setText("Code  Geeks");

            // setting the current position to 11
            // by skipping 3 boundaries
            wb.next(3);

            // getting the current text boundary
            current = wb.current();

            // display the result
            System.out.println(
                "current position before"
                + " calling preceding() : "
                + current);

            // calling preceding() method
            next = wb.preceding(6);

            // display the result
            System.out.println(
                "\ncurrent position after"
                + " calling 1st preceding() : "
                + next);

            // calling preceding() method
            next = wb.preceding(-1);

            // display the result
            System.out.println(
                "\ncurrent position after"
                + " calling 2nd preceding() : "
                + next);
        }
        catch (IllegalArgumentException e) {

            System.out.println(
                "\noffset is less than the first boundary");
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**输出:**

```java
current position before calling preceding() : 11

current position after calling 1st preceding() : 4

offset is less than the first boundary
Exception thrown : java.lang.IllegalArgumentException: offset out of bounds

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/breakiterator . html # previous-int-](https://docs.oracle.com/javase/9/docs/api/java/text/BreakIterator.html#preceding-int-)