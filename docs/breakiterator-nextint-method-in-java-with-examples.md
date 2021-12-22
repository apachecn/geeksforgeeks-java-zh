# Java 中的 BreakIterator next(int)方法，示例

> 原文:[https://www . geesforgeks . org/breakiterator-nextint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/breakiterator-nextint-method-in-java-with-examples/)

**java.text.BreakIterator** 类的 **next()** 方法用于从当前边界(通过调用 current()方法检索的边界)获取第 n 个下一个边界的索引。它提供边界的第一个字符的偏移量，该偏移量在 BreakIterator 指向的当前边界之后或之前。

**语法:**

```
public abstract int next(int n)
```

**参数:**取 n(要跳过的边界数)作为参数。如果 n 为正，它将向前跳过边界，否则向后跳过边界。

**返回值:**此方法提供第 n 个下一个边界的**索引形成当前边界。**

以下是说明 **next()** 方法的示例:

**例 1:**

```
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
        next = wb.next(2);

        // display the result
        System.out.println(
            "\ncurrent position after"
            + " calling 1st next() : "
            + next);

        // calling next method
        next = wb.next(-1);

        // display the result
        System.out.println(
            "\ncurrent position after"
            + " calling 2nd next() : "
            + next);
    }
}
```

**输出:**

```
current position before calling next() : 0

current position after calling 1st next() : 6

current position after calling 2nd next() : 4

```

**例 2:**

```
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
        next = wb.next(1);

        // display the result
        System.out.println(
            "\ncurrent position after"
            + " calling 1st next() : "
            + next);

        // calling next method
        next = wb.next(2);

        // display the result
        System.out.println(
            "\ncurrent position after"
            + " calling 2nd next() : "
            + next);
    }
}
```

**输出:**

```
current position before calling next() : 0

current position after calling 1st next() : 4

current position after calling 2nd next() : 11

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/breakiterator . html # next-int-](https://docs.oracle.com/javase/9/docs/api/java/text/BreakIterator.html#next-int-)