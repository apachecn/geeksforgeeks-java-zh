# Java 中的 DoubleStream allMatch()，示例

> 原文:[https://www . geesforgeks . org/double stream-all match-Java-examples/](https://www.geeksforgeeks.org/doublestream-allmatch-java-examples/)

**双流全部匹配(双谓词谓词)**返回该流的所有**元素是否与提供的谓词匹配。如果不是确定结果所必需的，它可能不会计算所有元素上的谓词。这是一次 ***短路端子操作。*** 如果终端操作在无限输入时可能在有限时间内终止，则该操作为短路。
**语法:****

```
boolean allMatch(DoublePredicate predicate)

```

**参数:**

1.  **双谓词:**一个双值参数的谓词(布尔值函数)。

**返回值:**如果流的所有元素都与提供的谓词匹配，或者流为空，则函数返回 true，否则返回 false。

**注意:**如果流为空，则返回 true，不计算谓词。

**例 1 :** allMatch()函数检查所有元素是否能被 3 整除。

```
// Java code for DoubleStream allMatch
// (DoublePredicate predicate) to check whether
// all elements of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = DoubleStream.of(3.8, 5.6, 9.2,
                                              12.5, 14.7);

        // Check if all elements of stream
        // are divisible by 3 or not using
        // DoubleStream allMatch(DoublePredicate predicate)
        boolean answer = stream.allMatch(num -> num % 3 == 0);

        // Displaying the result
        System.out.println(answer);
    }
}
```

**Output:**

```
false

```

**示例 2 :** allMatch()函数检查两个 DoubleStream 串接后得到的 double stream 中的所有元素是否都小于 2。

```
// Java code for DoubleStream allMatch
// (DoublePredicate predicate) to check whether
// all elements of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream after concatenating
        // two DoubleStreams
        DoubleStream stream = DoubleStream.concat(
            DoubleStream.of(-2.2, -4.3, -6.4, -8.5),
            DoubleStream.of(-1.5, 0, 1.7, 5.9));

        // Check if all elements of stream
        // are less than 2 or not using
        // DoubleStream allMatch(DoublePredicate predicate)
        boolean answer = stream.allMatch(num -> num < 2.0);

        // Displaying the result
        System.out.println(answer);
    }
}
```

**Output:**

```
false

```

**示例 3 :** allMatch()函数显示流是否为空，然后返回 true。

```
// Java code for DoubleStream allMatch
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

        boolean answer = stream.allMatch(num -> true);

        // Displaying the result
        System.out.println(answer);
    }
}
```

**Output:**

```
true

```