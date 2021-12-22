# Java 中的 DoubleStream concat()

> 原文:[https://www.geeksforgeeks.org/doublestream-concat-java/](https://www.geeksforgeeks.org/doublestream-concat-java/)

**DoubleStream concat()** 方法创建一个串联流，其中元素是第一个流的所有元素，然后是第二个流的所有元素。如果两个输入流都是有序的，则结果流是有序的；如果两个输入流中的任何一个是并行的，则[并行](https://www.geeksforgeeks.org/parallel-data-processing-java-set-1/)。

**语法:**

```java
static DoubleStream concat(DoubleStream a,  DoubleStream b)

```

**参数:**

1.  **双流:**原始双值元素的序列。
2.  **a :** 代表第一个流。
3.  **b :** 代表第二流。

**返回值:**函数返回两个输入双流的连接。

对 DoubleStream . concat(DoubleStream a，DoubleStream b)的调用可以看作是形成了一棵二叉树。所有输入流的连接是在根。单个输入流在叶子上。下面给出了 3 个双流 a、b 和 c 的例子

每个额外的输入流给树增加一层深度，并增加一层间接到达所有其他流。

**注意:**double stream . concat()方法返回的元素是有序的。例如，以下两行返回相同的结果:

```java
DoubleStream.concat(DoubleStream.concat(stream1, stream2), stream3);
DoubleStream.concat(stream1, DoubleStream.concat(stream2, stream3));

```

但是下面两个的结果是不同的。

```java
DoubleStream.concat(DoubleStream.concat(stream1, stream2), stream3); 
DoubleStream.concat(DoubleStream.concat(stream2, stream1), stream3);

```

**例 1 :**

```java
// Implementation of DoubleStream.concat()
// method in Java 8 with 2 DoubleStreams
import java.util.*;
import java.util.stream.DoubleStream;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating two DoubleStreams
        DoubleStream stream1 = DoubleStream.of(2.2, 4.3, 6.4);
        DoubleStream stream2 = DoubleStream.of(1.5, 3.6, 5.7);

        // concatenating both the Streams
        // with DoubleStream.concat() function
        // and displaying the result
        DoubleStream.concat(stream1, stream2)
            .forEach(element -> System.out.println(element));
    }
}
```

**Output:**

```java
2.2
4.3
6.4
1.5
3.6
5.7

```

**例 2 :**

```java
// Implementation of DoubleStream.concat()
// method in Java 8 with 2 DoubleStreams
import java.util.*;
import java.util.stream.DoubleStream;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating two DoubleStreams
        DoubleStream stream1 = DoubleStream.of(2.2, 4.3, 6.4);
        DoubleStream stream2 = DoubleStream.of(1.5, 4.3, 2.2);

        // concatenating both the Streams
        // with DoubleStream.concat() function
        // and displaying the result
        DoubleStream.concat(stream1, stream2).distinct().forEach(element -> System.out.println(element));
    }
}
```

**Output:**

```java
2.2
4.3
6.4
1.5

```