# Java 中 BreakIterator current()方法，示例

> 原文:[https://www . geesforgeks . org/breakiterator-current-method-in-Java-with-examples/](https://www.geeksforgeeks.org/breakiterator-current-method-in-java-with-examples/)

**java.text.BreakIterator** 类的 **current()** 方法用于获取该行单词中最近文本边界的索引。它提供当前由 BreakIterator 指向的文本的偏移量。

**语法:**

```java
public abstract int current()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法提供最近文本边界的**索引**。

以下是说明**电流()**方法的例子:

**例 1:**

```java
// Java program to demonstrate current() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing integer with zero
        int current = 0, last = 0;

        // creating and initializing BreakIterator
        BreakIterator wb
            = BreakIterator.getWordInstance();

        // setting text for BreakIterator
        wb.setText("Code  Geeks");

        // getting the current text boundary
        current = wb.current();

        // display the result
        System.out.println(
            "current position "
            + "before calling next(): "
            + current);

        // calling next method
        last = wb.next();

        // getting the current text boundary
        current = wb.current();

        // display the result
        System.out.println(
            "\ncurrent position after"
            + " calling 1st next(): "
            + current);

        // calling next method
        last = wb.next();

        // getting the current text boundary
        current = wb.current();

        // display the result
        System.out.println(
            "\ncurrent position after"
            + " calling 2nd next(): "
            + current);
    }
}
```

**输出:**

```java
current position before calling next(): 0

current position after calling 1st next(): 4

current position after calling 2nd next(): 6

```

**例 2:**

```java
// Java program to demonstrate current() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing integer with zero
        int current = 0, last = 0;

        // creating and initializing BreakIterator
        BreakIterator wb
            = BreakIterator.getWordInstance();

        // setting text for BreakIterator
        wb.setText("GeeksForGeeks");

        // getting the current text boundary
        current = wb.current();

        // display the result
        System.out.println(
            "current position "
            + "before calling next(): "
            + current);

        // calling next method
        last = wb.next();

        // getting the current text boundary
        current = wb.current();

        // display the result
        System.out.println(
            "\ncurrent position after"
            + " calling 1st next(): "
            + current);

        // calling next method
        last = wb.next();

        // getting the current text boundary
        current = wb.current();

        // display the result
        System.out.println(
            "\ncurrent position after"
            + " calling 2nd next(): "
            + current);
    }
}
```

**输出:**

```java
current position before calling next(): 0

current position after calling 1st next(): 13

current position after calling 2nd next(): 13

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/breakiterator . html # current–](https://docs.oracle.com/javase/9/docs/api/java/text/BreakIterator.html#current--)