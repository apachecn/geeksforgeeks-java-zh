# Java 中的排序器 tertiaryOrder()方法，带示例

> 原文:[https://www . geeksforgeeks . org/collectionelementiterator-tertiaryorder-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collationelementiterator-tertiaryorder-method-in-java-with-examples/)

类的 **tertiaryOrder()** 方法用于提供 CollationElementIterator 对象的每个排序元素的第三级组件。

**语法:**

```java
public static final short tertiaryOrder(int order)
```

**参数**:该方法以整数格式的**排序元素**作为参数，必须找到其三级分量。

**返回值:**该方法返回特定科利森元素的**三元组**。

以下是说明 **tertiaryOrder()** 方法的示例:

**例 1:**

```java
// Java program to demonstrate
// tertiaryOrder() method

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

        // for iteration
        for (int i = 1; i <= test.length(); i++) {

            // getting tertiary component of every elmenet
            // using tertiaryOrder() method
            int value
                = CollationElementIterator
                      .tertiaryOrder(cel.next());

            // display the reslut
            System.out.println("tertiary order "
                               + "for order "
                               + i + " is "
                               + value);
        }
    }
}
```

**输出:**

```java
tertiary order for order 1 is 1
tertiary order for order 2 is 0
tertiary order for order 3 is 0
tertiary order for order 4 is 0
tertiary order for order 5 is 0
tertiary order for order 6 is 1
tertiary order for order 7 is 0
tertiary order for order 8 is 0
tertiary order for order 9 is 1
tertiary order for order 10 is 0
tertiary order for order 11 is 0
tertiary order for order 12 is 0
tertiary order for order 13 is 0

```

**例 2:**

```java
// Java program to demonstrate
// tertiaryOrder() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // creating and initializing testString
        String test = "aBcDeFgH<>?:";

        // creating and initializing
        // RuleBasedCollator object
        RuleBasedCollator rbc
            = (RuleBasedCollator)(Collator.getInstance());

        // creating and initializing
        // CollationElementIterator
        CollationElementIterator cel
            = rbc.getCollationElementIterator(test);

        // for iteration
        for (int i = 1; i <= test.length(); i++) {

            // getting tertiary component of every elmenet
            // using tertiaryOrder() method
            int value
                = CollationElementIterator
                      .tertiaryOrder(cel.next());

            // display the reslut
            System.out.println("tertiary order "
                               + "for order "
                               + i + " is "
                               + value);
        }
    }
}
```

**输出:**

```java
tertiary order for order 1 is 0
tertiary order for order 2 is 1
tertiary order for order 3 is 0
tertiary order for order 4 is 1
tertiary order for order 5 is 0
tertiary order for order 6 is 1
tertiary order for order 7 is 0
tertiary order for order 8 is 1
tertiary order for order 9 is 0
tertiary order for order 10 is 0
tertiary order for order 11 is 0
tertiary order for order 12 is 0

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/collectionelementtiterator . html # tertiaryOrder-int-](https://docs.oracle.com/javase/9/docs/api/java/text/CollationElementIterator.html#tertiaryOrder-int-)