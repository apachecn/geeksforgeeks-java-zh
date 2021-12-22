# Java 中的排序器 next()方法，带示例

> 原文:[https://www . geeksforgeeks . org/collectionelementiterator-next-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collationelementiterator-next-method-in-java-with-examples/)

**Java . text . collectionelementtiterator 类**的 **next()** 方法用于获取下一个 Collator 元素。这个方法将迭代器推到下一个元素并返回它的值。

**语法:**

```java
public int next()
```

**参数**:该方法不接受任何参数。

**返回值:**该方法将下一个排序器元素的值作为**整数**值返回。

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
        cel.setOffset(1);

        // display the result
        System.out.println("current offset before"
                           + " calling next() "
                           + cel.getOffset());

        // getting offset of the next collator element
        // using next() method
        int value = cel.next();

        // display the result
        System.out.println("\ncurrent element value"
                           + " after calling next() "
                           + value);
    }
}
```

**输出:**

```java
current offset before calling next() 1

current element value after calling next() 5439488

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
        cel.setOffset(2);

        // display the result
        System.out.println("current offset before"
                           + " calling next() "
                           + cel.getOffset());

        // getting offset of the next collator element
        // using next() method
        int value = cel.next();

        // display the result
        System.out.println("\ncurrent offset after"
                           + " calling next() "
                           + cel.getOffset());
    }
}
```

**输出:**

```java
current offset before calling next() 2

current offset after calling next() 3

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/collectionelementtiterator . html # next–](https://docs.oracle.com/javase/9/docs/api/java/text/CollationElementIterator.html#next--)