# Java 中 BreakIterator 跟随()方法，示例

> 原文:[https://www . geesforgeks . org/breakiterator-following-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/breakiterator-following-method-in-java-with-examples/)

**java.text.BreakIterator** 类的**以下()**方法用于返回文本行中指定偏移量之后出现的第一个边界的索引。它提供下一个边界的第一个字符的偏移量，下一个边界跟随传递的偏移量的边界。
**语法:**

```java
public abstract int following(int offset)
```

**参数:**该方法将**偏移**作为参数，必须找到第一个参数之后的所需边界。
**返回值:**此方法提供指定偏移量后的第一个边界。
**异常:**如果偏移量小于第一个边界且大于最后一个边界，该方法抛出**IllegalArgumentException**。
以下是举例说明**以下()**方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate following() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            int current = 0;

            // creating and initializing BreakIterator
            BreakIterator wb
                = BreakIterator.getWordInstance();

            // setting text for BreakIterator
            wb.setText("Code  Geeks");

            // getting the text boundary
            current = wb.following(0);

            // display the result
            System.out.println(
                "first boundary for offset 0 : "
                + current);

            // getting the text boundary
            current = wb.following(4);

            // display the result
            System.out.println(
                "\nfirst boundary for offset 4 : "
                + current);

            // getting the text boundary
            current = wb.following(8);

            // display the result
            System.out.println(
                "\nfirst boundary for offset 8 : "
                + current);
        }

        catch (IllegalArgumentException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
first boundary for offset 0 : 4

first boundary for offset 4 : 6

first boundary for offset 8 : 11
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate following() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        try {
            int current = 0;

            // creating and initializing BreakIterator
            BreakIterator wb
                = BreakIterator.getWordInstance();

            // setting text for BreakIterator
            wb.setText("Code  Geeks");

            // getting the text boundary
            current = wb.following(0);

            // display the result
            System.out.println(
                "first boundary for offset 0 : "
                + current);

            // getting the text boundary
            current = wb.following(4);

            // display the result
            System.out.println(
                "\nfirst boundary for offset 4 : "
                + current);

            // getting the text boundary
            current = wb.following(-8);

            // display the result
            System.out.println(
                "\nfirst boundary for offset 8 : "
                + current);
        }

        catch (IllegalArgumentException e) {
            System.out.println(
                "\noffset is less than"
                + " the first boundary");
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
first boundary for offset 0 : 4

first boundary for offset 4 : 6

offset is less than the first boundary
Exception thrown : java.lang.IllegalArgumentException: offset out of bounds
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/breakiterator . html # following-int-](https://docs.oracle.com/javase/9/docs/api/java/text/BreakIterator.html#following-int-)