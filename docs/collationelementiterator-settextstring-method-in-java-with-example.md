# Java 中的排序器设置文本(字符串)方法，示例

> 原文:[https://www . geeksforgeeks . org/collionelementiterator-settextstring-method-in-Java-with-example/](https://www.geeksforgeeks.org/collationelementiterator-settextstring-method-in-java-with-example/)

**Java . text . CollationElementIterator**类的 **setText()** 方法用于为 collectionelementiterator 对象设置要迭代的新源字符串。

**语法:**

```
public void setText(String source)
```

**参数**:这个方法取一个新的**源字符串**，迭代器将要对其进行迭代。
**返回值:**这个方法没有什么可返回的。

以下是说明**设置文本()**方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// setText() method

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

        String str = "Code";

        // setting new text using
        // setText() method
        cel.setText(str);

        // for iteration
        for (int i = 1; i <= str.length(); i++) {

            // getting primary component of every element
            // using primaryOrder() method
            int value
                = CollationElementIterator
                      .primaryOrder(cel.next());

            // display the result
            System.out.println("primary order "
                               + "for order "
                               + i + " is "
                               + value);
        }
    }
}
```

**Output:** 

```
primary order for order 1 is 84
primary order for order 2 is 97
primary order for order 3 is 85
primary order for order 4 is 87
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// setText() method

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

        String str = "Tajmahal";

        // setting new text using
        // setText() method
        cel.setText(str);

        // for iteration
        for (int i = 1; i <= str.length(); i++) {

            // getting primary component of every element
            // using primaryOrder() method
            int value
                = CollationElementIterator
                      .primaryOrder(cel.next());

            // display the result
            System.out.println("primary order "
                               + "for order "
                               + i + " is "
                               + value);
        }
    }
}
```

**Output:** 

```
primary order for order 1 is 102
primary order for order 2 is 82
primary order for order 3 is 92
primary order for order 4 is 95
primary order for order 5 is 82
primary order for order 6 is 90
primary order for order 7 is 82
primary order for order 8 is 94
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/collectionelementtiterator . html # setText-Java . lang . string-T4】