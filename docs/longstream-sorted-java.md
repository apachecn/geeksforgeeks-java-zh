# Java 中 LongStream 排序的()

> 原文:[https://www.geeksforgeeks.org/longstream-sorted-java/](https://www.geeksforgeeks.org/longstream-sorted-java/)

**LongStream sorted()** 返回一个由这个流的元素按排序顺序组成的流。这是一个 ***有状态的中间操作*** ，也就是说，在处理新元素时，它可能会包含来自以前看到的元素的状态。有状态的中间操作可能需要在产生结果之前处理整个输入。例如，在看到流的所有元素之前，无法对流进行排序。

**语法:**

```
LongStream sorted()

Where, LongStream is a sequence of primitive long-valued 
elements. This is the long primitive specialization of Stream.

```

**异常:**如果该流的元素不可比较，则在执行终端操作时可能会抛出***Java . lang . class castexception***。

**返回值:** LongStream sorted()方法返回新的流。

**示例 1 :** 使用 LongStream sorted()对给定 LongStream 中的数字进行排序。

```
// Java code to sort LongStream
// using LongStream.sorted()
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.of(10L, 9L, 8L, 7L, 6L);

        // displaying the stream with sorted elements
        // using LongStream.sorted() function
        stream.sorted().forEach(System.out::println);
    }
}
```

**Output:**

```
6
7
8
9
10

```

**例 2 :** 使用 LongStream sorted()对 LongStream 生成器()生成的随机数进行排序。

```
// Java code to sort LongStream
// using LongStream.sorted()
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream by generating
        // random elements using LongStream.generate()
        LongStream stream = LongStream.generate(()
                                                    -> (long)(Math.random() * 10000))
                                .limit(5);

        // displaying the stream with sorted elements
        // using LongStream.sorted() function
        stream.sorted().forEach(System.out::println);
    }
}
```

**Output:**

```
2218
6150
6757
8020
8266

```