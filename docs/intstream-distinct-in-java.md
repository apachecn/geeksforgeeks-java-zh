# Java 中的 IntStream distinct()，示例

> 原文:[https://www.geeksforgeeks.org/intstream-distinct-in-java/](https://www.geeksforgeeks.org/intstream-distinct-in-java/)

**IntStream distinct()** 是 java.util.stream.IntStream 中的一个方法，这个方法返回一个由 distinct 元素组成的流。这是一个有状态的中间操作，也就是说，当处理新的元素时，它可以包含来自以前看到的元素的状态。

**语法:**

```
IntStream distinct()

Where, IntStream is a sequence of 
primitive int-valued elements.

```

下面给出了一些例子来更好地理解这个函数。
**例 1 :** 打印整数流的不同元素。

```
// Java code for IntStream distinct()
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args) {

    // creating a stream     
    IntStream stream = IntStream.of(2, 3, 3, 5, 6, 6, 8);

    // Displaying only distinct elements
    // using the distinct() method
    stream.distinct().forEach(System.out::println);

}
}
```

输出:

```
2
3
5
6
8

```

**示例 2 :** 计算流中不同元素的值。

```
// Java code for IntStream distinct() method
// to count the number of distinct 
// elements in given stream
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args) {

    // creating a stream     
    IntStream stream = IntStream.of(2, 3, 3, 5, 6, 6, 8);

    // storing the count of distinct elements
    // in a variable named total
    long total = stream.distinct().count();

    // displaying the total number of elements
    System.out.println(total);
}
}
```

输出:

```
5

```