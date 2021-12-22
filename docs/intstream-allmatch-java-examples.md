# Java 中的 IntStream allMatch()，示例

> 哎哎哎:# t0]https://www . geeksforgeeks . org/intstream-all patch-Java-examples/

**int stream all match(int predicate 谓词)**返回该流的所有元素是否与提供的谓词匹配。如果不是确定结果所必需的，它可能不会计算所有元素上的谓词。这是一次 ***短路端子操作。*** 如果终端操作在无限输入时可能在有限时间内终止，则该操作为短路。
**语法:**

```java
boolean allMatch(IntPredicate predicate)

Where, IntPredicate represents a predicate (boolean-valued function)
of one int-valued argument and the function returns true if either
all elements of the stream match the provided predicate or 
the stream is empty, otherwise false.

```

**注意:**如果流为空，则返回 true，不计算谓词。

**例 1 :** allMatch()函数检查所有元素是否能被 3 整除。

```java
// Java code for IntStream allMatch
// (Predicate predicate) to check whether
// all elements of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating an IntStream
        IntStream stream = IntStream.of(3, 5, 9, 12, 14);

        // Check if all elements of stream
        // are divisible by 3 or not using
        // IntStream allMatch(Predicate predicate)
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

**示例 2 :** allMatch()函数，检查串联两个 IntStream 后得到的 int stream 中的所有元素是否都小于 2。

```java
// Java code for IntStream allMatch
// (Predicate predicate) to check whether
// all elements of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating an IntStream after concatenating
        // two IntStreams
        IntStream stream = IntStream.concat(IntStream.of(-2, -4, -6, -8),
                                            IntStream.of(-1, 0, 1, 5));

        // Check if all elements of stream
        // are less than 2 or not using
        // IntStream allMatch(Predicate predicate)
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
// Java code for IntStream allMatch
// (Predicate predicate) to check whether
// any element of this stream match
// the provided predicate.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating an empty IntStream
        IntStream stream = IntStream.empty();

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