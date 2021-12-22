# Java 中的 BreakIterator previous()方法，示例

> 原文:[https://www . geeksforgeeks . org/breakiterator-previous-method-in-Java-with-examples/](https://www.geeksforgeeks.org/breakiterator-previous-method-in-java-with-examples/)

**java.text.BreakIterator** 类的 **previous()** 方法用于获取当前边界(通过调用 current()方法检索的边界)后面的前一个边界的索引。它提供了 BreakIterator 所指向的当前边界之前的边界的第一个字符的偏移量。

**语法:**

```
public abstract int previous()
```

**参数:**此方法不接受任何参数。

**返回值:**此方法提供当前边界之后的上一个边界的**索引**。

以下是说明**先前()**方法的示例:

**例 1:**

```
// Java program to demonstrate previous() method

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

        // setting the current position to index 11
        // By skipping 3 boundaries
        wb.next(3);

        // getting the current text boundary
        current = wb.current();

        // display the result
        System.out.println(
            "current position before"
            + " calling previous() : "
            + current);

        // calling previous() method
        next = wb.previous();

        // display the result
        System.out.println(
            "\ncurrent position after"
            + " calling 1st previous() : "
            + next);

        // calling previous() method
        next = wb.previous();

        // display the result
        System.out.println(
            "\ncurrent position after"
            + " calling 2nd previous() : "
            + next);
    }
}
```

**输出:**

```
current position before calling previous() : 11

current position after calling 1st previous() : 6

current position after calling 2nd previous() : 4

```

**例 2:**

```
// Java program to demonstrate
// previous() method

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

        // setting the current position to index 11
        // By skipping 3 boundaries
        wb.next(3);

        // getting the current text boundary
        current = wb.current();

        // display the result
        System.out.println(
            "current position before"
            + " calling previous() : "
            + current);

        // calling previous() method
        next = wb.previous();

        // display the result
        System.out.println(
            "\ncurrent position after"
            + " calling 1st previous() : "
            + next);

        // calling previous() method
        next = wb.previous();

        // display the result
        System.out.println(
            "\ncurrent position after"
            + " calling 2nd previous() : "
            + next);
    }
}
```

**输出:**

```
current position before calling previous() : 13

current position after calling 1st previous() : 0

current position after calling 2nd previous() : -1

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/breakiterator . html # previous–](https://docs.oracle.com/javase/9/docs/api/java/text/BreakIterator.html#previous--)