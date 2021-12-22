# Java 中的排序器 getOffset()方法，带示例

> 原文:[https://www . geeksforgeeks . org/collectionelementiterator-get offset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collationelementiterator-getoffset-method-in-java-with-examples/)

**Java . text . CollationElementIterator 类**的 **getOffset()** 方法用于获取当前由 collectionelementiterator 指向的排序器中存在的项的索引。

**语法:**

```
public int getOffset()
```

**参数**:此方法不接受任何参数。

**返回值:**该方法返回迭代器当前指向的元素的**偏移量**。

以下是说明 **getOffset()** 方法的示例:

**例 1:**

```
// Java program to demonstrate getOffset() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing testString
        String test = "Code Geeks 123";

        // creating and initializing
        // RuleBasedCollator object
        RuleBasedCollator rbc
            = (RuleBasedCollator)(Collator.getInstance());

        // creating and initializing
        // CollationElementIterator
        CollationElementIterator cel
            = rbc.getCollationElementIterator(test);

        // setting offset to index 4
        cel.setOffset(4);

        // getting offset of cel
        // using getOffset() method
        int value = cel.getOffset();

        // display the result
        System.out.println("current offset is "
                           + value);
    }
}
```

**输出:**

```
current offset is 4

```

**例 2:**

```
// Java program to demonstrate getOffset() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {

        // creating and initializing testString
        String test = "Code Geeks 123";

        // creating and initializing
        // RuleBasedCollator object
        RuleBasedCollator rbc
            = (RuleBasedCollator)(Collator.getInstance());

        // creating and initializing
        // CollationElementIterator
        CollationElementIterator cel
            = rbc.getCollationElementIterator(test);

        // setting offset to index 4
        cel.setOffset(4);

        // calling next element
        cel.next();

        // getting offset of cel
        // using getOffset() method
        int value = cel.getOffset();

        // display the result
        System.out.println("current offset is "
                           + value);
    }
}
```

**输出:**

```
current offset is 5

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/collationelementtiterator . html # getOffset–](https://docs.oracle.com/javase/9/docs/api/java/text/CollationElementIterator.html#getOffset--)