# Java 中排序的 IntStream()

> 原文:[https://www.geeksforgeeks.org/intstream-sorted-java/](https://www.geeksforgeeks.org/intstream-sorted-java/)

**IntStream sorted()** 返回一个由这个流的元素按排序顺序组成的流。这是一个 ***有状态的中间操作*** ，也就是说，在处理新元素时，它可能会包含来自以前看到的元素的状态。有状态的中间操作可能需要在产生结果之前处理整个输入。例如，在看到流的所有元素之前，无法对流进行排序。

**语法:**

```java
IntStream sorted()

Where, IntStream is a sequence of primitive int-valued 
elements. This is the int primitive specialization of Stream.

```

**异常:**如果该流的元素不可比较，则在执行终端操作时可能会抛出***Java . lang . class castexception***。

**返回值:** IntStream sorted()方法返回新的流。

**示例 1 :** 使用 IntStream sorted()对给定 IntStream 中的数字进行排序。

```java
// Java code to sort IntStream
// using IntStream.sorted()
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(10, 9, 8, 7, 6);

        // displaying the stream with sorted elements
        // using IntStream.sorted() function
        stream.sorted().forEach(System.out::println);
    }
}
```

**Output:**

```java
6
7
8
9
10

```

**例 2 :** 使用 IntStream sorted()对 [IntStream 生成器()](https://www.geeksforgeeks.org/intstream-generate-method-java/)生成的随机数进行排序。

```java
// Java code to sort IntStream
// using IntStream.sorted()
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream by generating
        // random elements using IntStream.generate()
        IntStream stream = IntStream.generate(()
                          -> (int)(Math.random() * 10000))
                             .limit(5);

        // displaying the stream with sorted elements
        // using IntStream.sorted() function
        stream.sorted().forEach(System.out::println);
    }
}
```

**Output:**

```java
501
611
7991
8467
9672

```