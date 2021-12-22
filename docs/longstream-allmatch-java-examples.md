# Java 中的 LongStream allMatch()，示例

> 原文:[https://www . geesforgeks . org/longstream-all match-Java-examples/](https://www.geeksforgeeks.org/longstream-allmatch-java-examples/)

**LongStream all match(long 谓语)**返回该流的所有元素是否与提供的谓语匹配。如果不是确定结果所必需的，它可能不会计算所有元素上的谓词。这是一次 ***短路端子操作。*** 如果终端操作在无限输入时可能在有限时间内终止，则该操作为短路。
**语法:**

```java
boolean allMatch(LongPredicate predicate)

```

**参数:**

1.  **长谓词:**一个长值参数的谓词(布尔值函数)。

**返回值:**如果流的所有元素都与提供的谓词匹配，或者流为空，则函数返回 true，否则返回 false。

**注意:**如果流为空，则返回 true，不计算谓词。

**例 1 :** allMatch()函数检查所有元素是否能被 3 整除。

```java
// Java code for LongStream allMatch
// (LongPredicate predicate) to check whether
// all elements of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.of(3L, 5L, 9L, 12L, 14L);

        // Check if all elements of stream
        // are divisible by 3 or not using
        // LongStream allMatch(LongPredicate predicate)
        boolean answer = stream.allMatch(num -> num % 3 == 0);

        // Displaying the result
        System.out.println(answer);
    }
}
```

输出:

```java
false

```

**例 2 :** allMatch()函数，检查两个 LongStream 串接后得到的 LongStream 中的所有元素是否都小于 2。

```java
// Java code for LongStream allMatch
// (LongPredicate predicate) to check whether
// all elements of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream after concatenating
        // two LongStreams
        LongStream stream = 
         LongStream.concat(LongStream.of(-2L, -4L, -6L, -8L),
                             LongStream.of(-1L, 0L, 1L, 5L));

        // Check if all elements of stream
        // are less than 2 or not using
        // LongStream allMatch(LongPredicate predicate)
        boolean answer = stream.allMatch(num -> num < 2);

        // Displaying the result
        System.out.println(answer);
    }
}
```

输出:

```java
false

```

**示例 3 :** allMatch()函数显示流是否为空，然后返回 true。

```java
// Java code for LongStream allMatch
// (LongPredicate predicate)) to check whether
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

        boolean answer = stream.allMatch(num -> true);

        // Displaying the result
        System.out.println(answer);
    }
}
```

输出:

```java
true

```