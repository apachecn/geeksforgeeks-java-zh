# Java 中的双流 anyMatch()，示例

> 原文:[https://www . geesforgeks . org/double stream-any match-Java-examples/](https://www.geeksforgeeks.org/doublestream-anymatch-java-examples/)

**双流 anyMatch(双谓词谓词)**返回此流的任何**元素是否与提供的谓词匹配。如果不是确定结果所必需的，它可能不会计算所有元素上的谓词。这是一次 ***短路端子操作。*** 如果终端操作在无限输入时可能在有限时间内终止，则该操作为短路。
**语法:****

```
boolean anyMatch(DoublePredicate predicate)

```

**参数:**

1.  **双谓词:**一个双值参数的谓词(布尔值函数)。

**返回值:**如果流中的任何元素与提供的谓词匹配，函数返回 true，否则返回 false。

**注意:**如果流为空，则返回 false，不计算谓词。

**示例 1 :** anyMatch()函数检查列表中的任何元素是否满足给定条件。

```
// Java code for DoubleStream anyMatch
// (DoublePredicate predicate) to check whether
// any element of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = DoubleStream.of(1.2, 2.3,
                                    3.4, 4.5, 5.6, 6.7);

        // Stream anyMatch(DoublePredicate predicate)
        boolean answer = stream.anyMatch(num -> (num - 5) > 0);

        // Displaying the result
        System.out.println(answer);
    }
}
```

**Output:**

```
true

```

**例 2 :** anyMatch()函数检查流中任意元素的平方根是否大于 8。

```
// Java code for DoubleStream anyMatch
// (DoublePredicate predicate) to check whether
// any element of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = DoubleStream.of(10.3, 20.4, 30.5,
                                              40.9, 50.4);

        // Stream anyMatch(DoublePredicate predicate)
        boolean answer = stream.anyMatch(num -> Math.sqrt(num) > 8);

        // Displaying the result
        System.out.println(answer);
    }
}
```

**Output:**

```
false

```

**示例 3 :** anyMatch()函数显示如果流为空，则返回 false。

```
// Java code for DoubleStream anyMatch
// (DoublePredicate predicate) to check whether
// any element of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an empty DoubleStream
        DoubleStream stream = DoubleStream.empty();

        boolean answer = stream.anyMatch(num -> true);

        // Displaying the result
        System.out.println(answer);
    }
}
```

**Output:**

```
false

```