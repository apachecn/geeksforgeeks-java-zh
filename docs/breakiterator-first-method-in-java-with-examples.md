# Java 中 BreakIterator first()方法，带示例

> 原文:[https://www . geeksforgeeks . org/breakiterator-Java 中的第一种方法-示例/](https://www.geeksforgeeks.org/breakiterator-first-method-in-java-with-examples/)

**java.text.BreakIterator** 类的 **first()** 方法用于获取第一个边界的索引，它总是返回第一个边界的起始索引，它提供第一个边界的第一个字符的偏移量。

**语法:**

```
public abstract int first()
```

**参数:**此方法不接受任何参数。

**返回值:**此方法提供第一个边界的**索引**。

以下是说明**第一种()**方法的例子:

**例 1:**

```
// Java program to demonstrate first() method

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

        // getting the index of first text boundary
        int first = wb.first();

        // display the result
        System.out.println("first boundary : " + first);
    }
}
```

**输出:**

```
first boundary : 0

```

**例 2:**

```
// Java program to demonstrate
// first() method

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
        wb.setText("    GeeksForGeeks");

        // getting the index of first text boundary
        int first = wb.first();

        // display the result
        System.out.println("first boundary : " + first);
    }
}
```

**输出:**

```
first boundary : 0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/breakiterator . html # first–](https://docs.oracle.com/javase/9/docs/api/java/text/BreakIterator.html#first--)