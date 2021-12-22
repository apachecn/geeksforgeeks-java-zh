# Java 中的排序器重置()方法，示例

> 原文:[https://www . geeksforgeeks . org/collionelementiterator-reset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collationelementiterator-reset-method-in-java-with-examples/)

类的 **reset()** 方法用于将迭代器的光标重置到输入字符串的开头。

**语法:**

```
public void reset()
```

**参数**:此方法不接受任何参数。
**返回值:**这个方法没有什么可返回的。

以下是说明**复位()**方法的例子:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// reset() method

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

        // setting cursor of iterator
        cel.setOffset(2);
        cel.next();

        // display the result
        System.out.println(
            "current offset before calling reset() "
            + cel.getOffset());

        // reset the cursor to the
        // beginning of the string
        // using reset() method
        cel.reset();

        // display the result
        System.out.println(
            "\ncurrent offset after calling reset() "
            + cel.getOffset());
    }
}
```

**Output:** 

```
current offset before calling reset() 3

current offset after calling reset() 0
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// reset() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing
        // testString
        String test = "abcd";

        // creating and initializing
        // RuleBasedCollator object
        RuleBasedCollator rbc
            = (RuleBasedCollator)(Collator.getInstance());

        // creating and initializing
        // CollationElementIterator
        CollationElementIterator cel
            = rbc.getCollationElementIterator(test);

        // setting cursor of iterator
        cel.setOffset(3);
        cel.previous();

        // display the result
        System.out.println(
            "current offset before calling reset() "
            + cel.getOffset());

        // reset the cursor to the beginning of the string
        // using reset() method
        cel.reset();

        // display the result
        System.out.println(
            "\ncurrent offset after calling reset() "
            + cel.getOffset());
    }
}
```

**Output:** 

```
current offset before calling reset() 2

current offset after calling reset() 0
```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/collationelementiterator . html # reset–](https://docs.oracle.com/javase/9/docs/api/java/text/CollationElementIterator.html#reset--)