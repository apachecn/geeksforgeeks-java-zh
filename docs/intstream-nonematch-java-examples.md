# Java 中的 IntStream noneMatch()，示例

> 原文:[https://www . geesforgeks . org/int stream-none match-Java-examples/](https://www.geeksforgeeks.org/intstream-nonematch-java-examples/)

**int stream none match(int predicate 谓词)**返回此流中是否没有元素与提供的谓词匹配。如果不是确定结果所必需的，它可能不会计算所有元素上的谓词。这是一次 ***短路端子操作。*** 如果终端操作在无限输入时可能在有限时间内终止，则该操作为短路。
**语法:**

```java
boolean noneMatch(IntPredicate predicate)

Where, IntPredicate represents a predicate (boolean-valued function)
of one int-valued argument and the function returns true if either
all elements of the stream match the provided predicate or 
the stream is empty, otherwise false.

```

**注意:**如果流为空，则返回 true，不计算谓词。

**例 1 :** noneMatch()函数检查 IntStream 的元素是否没有被 5 整除。

```java
// Java code for IntStream noneMatch
// (Predicate predicate) to check whether
// no element of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating an IntStream
        IntStream stream = IntStream.of(3, 5, 9, 12, 14);

        // Check if no element of stream
        // is divisible by 5 using
        // IntStream noneMatch(Predicate predicate)
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