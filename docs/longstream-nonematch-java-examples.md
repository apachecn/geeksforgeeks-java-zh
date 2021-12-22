# Java 中的 LongStream noneMatch()，示例

> 原文:[https://www . geesforgeks . org/longstream-non match-Java-examples/](https://www.geeksforgeeks.org/longstream-nonematch-java-examples/)

**LongStream none match(long 谓语)**返回此流中是否没有元素与提供的谓语匹配。如果不是确定结果所必需的，它可能不会计算所有元素上的谓词。这是一次 ***短路端子操作。*** 如果终端操作在无限输入时可能在有限时间内终止，则该操作为短路。
**语法:**

```java
boolean noneMatch(LongPredicate predicate) 

```

**参数:**

1.  **长谓词:**一个长值参数的谓词(布尔值函数)。

**返回值:**如果流的所有元素都与提供的谓词匹配，或者流为空，则函数返回 true，否则返回 false。

**注意:**如果流为空，则返回 true，不计算谓词。

**例 1 :** noneMatch()函数，检查 LongStream 的元素是否都不能被 5 整除。

```java
// Java code for LongStream noneMatch
// (LongPredicate predicate) to check whether
// no element of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.of(3L, 5L, 9L, 12L, 14L);

        // Check if no element of stream
        // is divisible by 5 using
        // LongStream noneMatch(LongPredicate predicate)
        boolean answer = stream.noneMatch(num -> num % 5 == 0);

        // Displaying the result
        System.out.println(answer);
    }
}
```

**Output:**

```java
false

```

**示例 2 :** noneMatch()函数，用于检查连接两个 LongStream 后得到的 LongStream 中是否没有元素小于 2。

```java
// Java code for LongStream noneMatch
// (LongPredicate predicate) to check whether
// no element of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream after concatenating
        // two LongStreams
        LongStream stream = LongStream.concat(LongStream.of(3L, 4L, 5L, 6L),
                                              LongStream.of(7L, 8L, 9L, 10L));

        // Check if no element of stream
        // is less than 2 using
        // LongStream noneMatch(LongPredicate predicate)
        boolean answer = stream.noneMatch(num -> num < 2);

        // Displaying the result
        System.out.println(answer);
    }
}
```

**Output:**

```java
true

```

**示例 3 :** noneMatch()函数显示流是否为空，然后返回 true。

```java
// Java code for LongStream noneMatch
// (LongPredicate predicate) to check whether
// no element of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an empty LongStream
        LongStream stream = LongStream.empty();

        // Using LongStream noneMatch() on empty stream
        boolean answer = stream.noneMatch(num -> true);

        // Displaying the result
        System.out.println(answer);
    }
}
```

**Output:**

```java
true

```