# BreakIterator 是 Java 中的 Boundary()方法，带有示例

> 原文:[https://www . geesforgeks . org/breakiterator-is boundary-method-in-Java-with-examples/](https://www.geeksforgeeks.org/breakiterator-isboundary-method-in-java-with-examples/)

**java.text.BreakIterator** 类的 **isBoundary()** 方法用于检查传递的偏移量是否为边界。

**语法:**

```java
public boolean isBoundary(int offset)
```

**参数:**该方法以**偏移**为参数，检查是否为边界。

**返回值:**如果传递的偏移量是边界，则该方法提供**真**，否则提供**假**。

以下是举例说明 **isBoundary()** 方法的例子:

**例 1:**

```java
// Java program to demonstrate isBoundary() method

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

        // checking for the boundary
        // by using isBoundary() method
        boolean status = wb.isBoundary(0);

        // display the result
        if (status)
            System.out.println("offset is a boundary");
        else
            System.out.println("offset is not a boundary");
    }
}
```

**输出:**

```java
offset is a boundary

```

**例 2:**

```java
// Java program to demonstrate isBoundary() method

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

        // checking for the boundary
        // by using isBoundary() method
        boolean status = wb.isBoundary(2);

        // display the result
        if (status)
            System.out.println("offset is a boundary");
        else
            System.out.println("offset is not a boundary");
    }
}
```

**输出:**

```java
offset is not a boundary

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/breakiterator . html # isbboundary-int-](https://docs.oracle.com/javase/9/docs/api/java/text/BreakIterator.html#isBoundary-int-)