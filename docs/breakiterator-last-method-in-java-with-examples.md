# Java 中 BreakIterator last()方法，示例

> 原文:[https://www . geeksforgeeks . org/breakiterator-Java 中的最后一种方法-带示例/](https://www.geeksforgeeks.org/breakiterator-last-method-in-java-with-examples/)

**java.text.BreakIterator** 类的 **last()** 方法用于获取最后一个边界的索引。它总是返回最后一个边界的最后一个字符的偏移量。

**语法:**

```java
public abstract int last()
```

**参数:**此方法不接受任何参数。

**返回值:**此方法提供最后一个边界的**索引**。

以下是举例说明**最后()**方法的例子:

**例 1:**

```java
// Java program to demonstrate last() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing BreakIterator
        BreakIterator wb
            = BreakIterator.getWordInstance();

        // setting text for BreakIterator
        wb.setText("Code  Geeks");

        // getting the index of last text boundary
        int last = wb.last();

        // display the result
        System.out.println("last boundary : " + last);
    }
}
```

**输出:**

```java
last boundary : 11

```

**例 2:**

```java
// Java program to demonstrate last() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing BreakIterator
        BreakIterator wb
            = BreakIterator.getWordInstance();

        // setting text for BreakIterator
        wb.setText("GeeksForGeeks");

        // getting the index of last text boundary
        int last = wb.last();

        // display the result
        System.out.println("last boundary : " + last);
    }
}
```

**输出:**

```java
last boundary : 13

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/breakiterator . html # last–](https://docs.oracle.com/javase/9/docs/api/java/text/BreakIterator.html#last--)