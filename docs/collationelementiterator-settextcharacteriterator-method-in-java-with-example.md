# Java 中的排序器属性设置器方法，示例

> 原文:[https://www . geeksforgeeks . org/collectionelementiterator-settextternatureterator-method-in-Java-with-example/](https://www.geeksforgeeks.org/collationelementiterator-settextcharacteriterator-method-in-java-with-example/)

**Java . text . CollationElementIterator**类的 **setText()** 方法用于为 collectionelementiterator 对象设置要迭代的新源字符串。

**语法:**

```java
public void setText(CharacterIterator source)
```

**参数**:这个方法采用了一个新的**特性迭代器对象**包含迭代器将要迭代的字符串值。

**返回值:**这个方法没有什么可返回的。

以下是说明**设置文本()**方法的示例:

**例 1:**

```java
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

        // creating and initializing
        // CharacterIterator object
        CharacterIterator str
            = new StringCharacterIterator("Code");

        // setting new text using
        // setText() method
        cel.setText(str);

        // for iteration
        for (int i = 1; i <= str.getEndIndex(); i++) {

            // getting primary component of every elmenet
            // using primaryOrder() method
            int value
                = CollationElementIterator
                      .primaryOrder(cel.next());

            // display the reslut
            System.out.println("primary order "
                               + "for order "
                               + i + " is "
                               + value);
        }
    }
}
```

**输出:**

```java
primary order for order 1 is 84
primary order for order 2 is 97
primary order for order 3 is 85
primary order for order 4 is 87

```

**例 2:**

```java
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

        // creating and initializing
        // CharacterIterator object
        CharacterIterator str
            = new StringCharacterIterator("GeeksForGeeks");

        // setting new text using
        // setText() method
        cel.setText(str);

        // for iteration
        for (int i = 1; i <= str.getEndIndex(); i++) {

            // getting primary component of every elmenet
            // using primaryOrder() method
            int value
                = CollationElementIterator
                      .primaryOrder(cel.next());

            // display the reslut
            System.out.println("primary order "
                               + "for order "
                               + i + " is "
                               + value);
        }
    }
}
```

**输出:**

```java
primary order for order 1 is 89
primary order for order 2 is 87
primary order for order 3 is 87
primary order for order 4 is 93
primary order for order 5 is 101
primary order for order 6 is 88
primary order for order 7 is 97
primary order for order 8 is 100
primary order for order 9 is 89
primary order for order 10 is 87
primary order for order 11 is 87
primary order for order 12 is 93
primary order for order 13 is 101

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/collectionelementtiterator . html # setText-Java . text .表征器-](https://docs.oracle.com/javase/9/docs/api/java/text/CollationElementIterator.html#setText-java.text.CharacterIterator-)