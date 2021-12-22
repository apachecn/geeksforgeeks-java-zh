# Java 中的 LongStream concat()

> 原文:[https://www.geeksforgeeks.org/longstream-concat-java/](https://www.geeksforgeeks.org/longstream-concat-java/)

**LongStream concat()** 方法创建一个串联流，其中元素是第一个流的所有元素，后面是第二个流的所有元素。如果两个输入流都是有序的，则结果流是有序的；如果两个输入流中的任何一个是并行的，则[并行](https://www.geeksforgeeks.org/parallel-data-processing-java-set-1/)。

**语法:**

```
static LongStream concat(LongStream a, LongStream b)

```

**参数:**

1.  **LongStream :** 原始长值元素的序列。
2.  **a :** 代表第一个流。
3.  **b :** 代表第二流。

**返回值:**函数返回两个输入长流的连接。

对 LongStream.concat(LongStream a，LongStream b)的调用可以看作是形成了一棵二叉树。所有输入流的连接是在根。单个输入流在叶子上。下面给出了 3 个长流的例子

每个额外的输入流给树增加一层深度，并增加一层间接到达所有其他流。

**注意:**longstream . concat()方法返回的元素是有序的。例如，以下两行返回相同的结果:

```
LongStream.concat(LongStream.concat(stream1, stream2), stream3);
LongStream.concat(stream1, LongStream.concat(stream2, stream3));

```

但是下面两个的结果是不同的。

```
LongStream.concat(LongStream.concat(stream1, stream2), stream3); 
LongStream.concat(LongStream.concat(stream2, stream1), stream3);

```

**例 1 :**

```
// Implementation of LongStream concat()
// method in Java 8 with 2 LongStreams
import java.util.*;
import java.util.stream.LongStream;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating two LongStreams
        LongStream stream1 = LongStream.of(2L, 4L, 6L);
        LongStream stream2 = LongStream.of(1L, 3L, 5L);

        // concatenating both the Streams
        // with LongStream concat() function
        // and displaying the result
        LongStream.concat(stream1, stream2)
            .forEach(element -> System.out.println(element));
    }
}
```

**Output:**

```
2
4
6
1
3
5

```

**例 2 :**

```
// Implementation of LongStream concat()
// method in Java 8 with 2 LongStreams
import java.util.*;
import java.util.stream.LongStream;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating two LongStreams
        LongStream stream1 = LongStream.of(2L, 4L, 6L);
        LongStream stream2 = LongStream.of(1L, 2L, 4L);

        // concatenating both the Streams
        // with LongStream concat() function
        // and displaying distinct elements
        // in the concatenated LongStream
        LongStream.concat(stream1, stream2).distinct().
             forEach(element -> System.out.println(element));
    }
}
```

**Output:**

```
2
4
6
1

```