# Java 中的 DoubleStream noneMatch()，示例

> 原文:[https://www . geesforgeks . org/double stream-non match-Java-examples/](https://www.geeksforgeeks.org/doublestream-nonematch-java-examples/)

**双流无匹配(双谓词谓词)**返回该流中是否没有元素与提供的谓词匹配。如果不是确定结果所必需的，它可能不会计算所有元素上的谓词。这是一次 ***短路端子操作。*** 如果终端操作在无限输入时可能在有限时间内终止，则该操作为短路。
**语法:**

```java
boolean noneMatch(DoublePredicate predicate)

Where, DoublePredicate represents a predicate 
(boolean-valued function) of one double-valued argument.

```

**返回值:**如果流的所有元素都与提供的谓词匹配，或者流为空，则函数返回 true，否则返回 false。

**注意:**如果流为空，则返回 true，不计算谓词。

**例 1 :** noneMatch()函数检查 DoubleStream 的元素是否不能被 5 整除。

```java
// Java code for DoubleStream noneMatch
// (DoublePredicate predicate) to check whether
// no element of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream =
              DoubleStream.of(3.2, 5.0, 9.3, 12.4, 14.7);

        // Check if no element of stream
        // is divisible by 5 using
        // DoubleStream noneMatch(DoublePredicate predicate)
        boolean answer =
             stream.noneMatch(num -> num % 5 == 0);

        // Displaying the result
        System.out.println(answer);
    }
}
```

**Output:**

```java
false

```

**示例 2 :** noneMatch()函数，用于检查在连接两个 DoubleStream 后获得的 double stream 中是否没有元素小于 2。

```java
// Java code for DoubleStream noneMatch
// (DoublePredicate predicate) to check whether
// no element of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream after
        // concatenating two DoubleStreams
        DoubleStream stream = DoubleStream.concat(
            DoubleStream.of(3.3, 4.2, 5.1, 6.6),
            DoubleStream.of(7.2, 8.3, 9.1, 10.5));

        // Check if no element of stream
        // is less than 2 using
        // DoubleStream noneMatch(DoublePredicate predicate)
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
// Java code for DoubleStream noneMatch
// (DoublePredicate predicate) to check whether
// no element of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an empty DoubleStream
        DoubleStream stream = DoubleStream.empty();

        // Using DoubleStream noneMatch() on empty stream
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