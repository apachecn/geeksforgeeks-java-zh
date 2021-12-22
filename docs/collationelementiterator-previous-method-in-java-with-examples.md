# Java 中的排序器上一个()方法，带示例

> 原文:[https://www . geeksforgeeks . org/collectionelementiterator-previous-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collationelementiterator-previous-method-in-java-with-examples/)

**Java . text . collectionelementtiterator 类**的 **previous()** 方法用于获取 previous Collator 元素。这个方法将迭代器推到前一个元素并返回它的值。

**语法:**

```java
public int previous()
```

**参数**:该方法不接受任何参数。

**返回值:**该方法返回**上一个排序器元素**的值。

以下是说明**先前()**方法的示例:

**例 1:**

```java
// Java program to demonstrate previous() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing testString
        String test = "abcd";

        // creating and initializing
        // RuleBasedCollator object
        RuleBasedCollator rbc
            = (RuleBasedCollator)(Collator.getInstance());

        // creating and initializing
        // CollationElementIterator
        CollationElementIterator cel
            = rbc.getCollationElementIterator(test);

        // setting offset to index 4
        cel.setOffset(3);

        // display the result
        System.out.println("current offset before"
                           + " calling previous() "
                           + cel.getOffset());

        // getting offset of the previous collator element
        // using previous() method
        int value = cel.previous();

        // display the result
        System.out.println("\ncurrent element value after"
                           + " calling previous() "
                           + value);
    }
}
```

**输出:**

```java
current offset before calling previous() 3

current element value after calling previous() 5505024

```

**例 2:**

```java
// Java program to demonstrate previous() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing testString
        String test = "abcd";

        // creating and initializing
        // RuleBasedCollator object
        RuleBasedCollator rbc
            = (RuleBasedCollator)(Collator.getInstance());

        // creating and initializing
        // CollationElementIterator
        CollationElementIterator cel
            = rbc.getCollationElementIterator(test);

        // setting offset to index 2
        cel.setOffset(2);

        // display the result
        System.out.println("current offset before"
                           + " calling previous() "
                           + cel.getOffset());

        // getting offset of the previous collator element
        // using previous() method
        int value = cel.previous();

        // display the result
        System.out.println("\ncurrent offset after"
                           + " calling previous() "
                           + cel.getOffset());
    }
}
```

**输出:**

```java
current offset before calling previous() 2

current offset after calling previous() 1

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/collectionelementtiterator . html # next–](https://docs.oracle.com/javase/9/docs/api/java/text/CollationElementIterator.html#next--)