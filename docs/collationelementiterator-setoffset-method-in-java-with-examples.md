# Java 中的排序器 setOffset()方法，带示例

> 原文:[https://www . geeksforgeeks . org/collectionelementiterator-setoffset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collationelementiterator-setoffset-method-in-java-with-examples/)

类的 **setOffset()** 方法用于将迭代器的光标设置为作为参数传递的特定索引。

**语法:**

```java
public void setOffset(int newOffset)
```

**参数**:该方法取一个**整数值 newOffset** ，此时光标必须被设置。

**返回值:**这个方法没有什么可返回的。

以下是举例说明 **setOffset()** 方法的例子:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// setOffset() method

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
        // using setOffset() method
        cel.setOffset(4);

        // display the result
        System.out.println("current offset is "
                           + cel.getOffset());
    }
}
```

**Output:** 

```java
current offset is 4
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// setOffset() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing testString
        String test = "GeeksForGeeks";

        // creating and initializing
        // RuleBasedCollator object
        RuleBasedCollator rbc
            = (RuleBasedCollator)(Collator.getInstance());

        // creating and initializing
        // CollationElementIterator
        CollationElementIterator cel
            = rbc.getCollationElementIterator(test);

        // after call of setOffset() method
        // all next() method will become redundent
        cel.next();
        cel.next();
        cel.next();
        cel.next();

        // setting cursor of iterator to index 0
        // using setOffset() method
        cel.setOffset(0);

        // display the result
        System.out.println("current offset is "
                           + cel.getOffset());
    }
}
```

**Output:** 

```java
current offset is 0
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/collectionelementtiterator . html # setOffset-int-T4】