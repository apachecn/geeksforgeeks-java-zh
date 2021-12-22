# Java 中的 LongStream anyMatch()，示例

> 原文:[https://www . geesforgeks . org/longstream-any match-Java-examples/](https://www.geeksforgeeks.org/longstream-anymatch-java-examples/)

**LongStream any match(long 谓语)**返回此流的**任何**元素是否与提供的谓语匹配。如果不是确定结果所必需的，它可能不会计算所有元素上的谓词。这是一次 ***短路端子操作。*** 如果终端操作在无限输入时可能在有限时间内终止，则该操作为短路。
**语法:**

```
boolean anyMatch(LongPredicate predicate) 

```

**参数:**

1.  **长谓词:**一个长值参数的谓词(布尔值函数)。

**返回值:**如果流中的任何元素与提供的谓词匹配，函数返回 true，否则返回 false。

**注意:**如果流为空，则返回 false，不计算谓词。

**示例 1 :** anyMatch()函数检查列表中的任何元素是否满足给定条件。

```
// Java code for LongStream anyMatch
// (LongPredicate predicate) to check whether
// any element of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.of(1L, 2L, 3L, 4L, 5L, 6L);

        // LongStream anyMatch(LongPredicate predicate)
        boolean answer = stream.anyMatch(num -> (num - 5) > 0);

        // Displaying the result
        System.out.println(answer);
    }
}
```

输出:

```
true

```

**例 2 :** anyMatch()函数检查流中任意元素的平方根是否大于 8。

```
// Java code for LongStream anyMatch
// (LongPredicate predicate) to check whether
// any element of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.of(10L, 20L, 30L, 40L, 50L);

        // LongStream anyMatch(LongPredicate predicate)
        boolean answer = stream.anyMatch(num -> Math.sqrt(num) > 8);

        // Displaying the result
        System.out.println(answer);
    }
}
```

输出:

```
false

```

**示例 3 :** anyMatch()函数显示如果流为空，则返回 false。

```
// Java code for LongStream anyMatch
// (LongPredicate predicate) to check whether
// any element of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an empty LongStream
        LongStream stream = LongStream.empty();

        // LongStream anyMatch(LongPredicate predicate)
        boolean answer = stream.anyMatch(num -> true);

        // Displaying the result
        System.out.println(answer);
    }
}
```

输出:

```
false

```