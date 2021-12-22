# 用 Java 将流转换为集

> 原文:[https://www.geeksforgeeks.org/convert-stream-set-java/](https://www.geeksforgeeks.org/convert-stream-set-java/)

下面给出了一些在 Java 中可以用来将流转换为集的方法。

### **方法 1:使用收集器**

Stream collect()方法从流中获取元素，并将它们存储在集合中。**收集(Collector.toSet())** 从一个流收集元素到一个集合。

Stream.collect()方法可用于收集容器中的流元素。可以传递由 Collectors.toSet()返回的收集器，它将流的元素累积到一个新的集合中。

```java
// Java code for converting 
// Stream to Set using Collectors
import java.util.*;
import java.util.stream.Stream;
import java.util.stream.Collectors;

class GFG {

    // Driver code
    public static void main(String[] args) {

    // Creating a Stream of Integers
    Stream<Integer> stream = Stream.of(-2, -1, 0, 1, 2);

    // Using Stream.collect() to collect the 
    // elements of stream in a container.
    Set<Integer> streamSet = stream.collect(Collectors.toSet());

    // Displaying the elements
    streamSet.forEach(num -> System.out.println(num));
    }
}
```

**输出:**

```java
-1
0
-2
1
2

```