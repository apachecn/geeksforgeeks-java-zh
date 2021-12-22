# Java 流计数()方法举例

> 原文:[https://www . geesforgeks . org/Java-util-stream-collectors-counting-method-examples/](https://www.geeksforgeeks.org/java-util-stream-collectors-counting-method-examples/)

在 Java 8 中，有一个由 **Collectors** 类 **counting()** 方法返回的预定义 **counting()** 方法来计算流中的元素数量。

> **语法:**
> **公共静态收集器计数()**其中，输出是**收集器**，作用于类型为 **T** 的元素流，其整理器返回类型为 Long 的“已收集”值。这是一个终端操作，它返回流中经过各种流水线流操作(如过滤)后到达 **collect()** 方法的元素总数。

**示例 1 :** 对整数流中的元素进行计数。

```
// Java code to count number of elements 
// in stream
import java.util.stream.Stream;
import java.util.stream.Collectors;
class counting {
    public static void main(String[] args)
    {
        // creating stream of integers
        Stream<Integer> i = Stream.of(1, 2, 3, 4, 5, 6);

        // counting number of integer in stream
        long count_int = i.collect(Collectors.counting());

        System.out.println(count_int);
    }
}
```

**Output:**

```
6

```

**示例 2 :** 对字符串流中的元素进行计数。

```
// JAVA code to count number of elements in stream
import java.util.stream.Stream;
import java.util.stream.Collectors;

class counting {
    public static void main(String[] args)
    {
        // creating stream of strings
        Stream<String> s = Stream.of("Akash","Harsh",
                        "Shubham","Nishant","Pratik");

        // counting number of strings in stream
        long count_string =  s.collect(Collectors.counting());

        System.out.println(count_string);
    }
}
```

**Output:**

```
5

```