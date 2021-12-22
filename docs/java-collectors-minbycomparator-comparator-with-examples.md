# Java | Collectors minBy(比较器比较器)示例

> 原文:[https://www . geesforgeks . org/Java-collectors-min bycomparator-comparator-with-examples/](https://www.geeksforgeeks.org/java-collectors-minbycomparator-comparator-with-examples/)

**采集器 minBy(比较器< **？超级 T** >比较器)**用于根据作为参数传递的比较器找到一个元素。它返回一个收集器，该收集器根据给定的比较器产生最小元素，被描述为一个**可选的<T>T5。**

**语法:**

```
public static 
    <T> Collector<T, ?, Optional<T>> 
        minBy(Comparator<? super T> comparator)

```

其中使用的术语如下:

*   **接口收集器< T，A，R >** :一种可变的约简操作，将输入元素累积到一个可变的结果容器中，在处理完所有输入元素后，可选地将累积的结果转换为最终表示。还原操作可以顺序执行，也可以并行执行。
    *   **T:** 归约运算的输入元素类型。
    *   **A:** 还原操作的可变累加类型。
    *   **R:** 归约运算的结果类型。
*   **可选:**可能包含也可能不包含非空值的容器对象。如果存在值，is present()将返回 true，get()将返回该值。
*   **比较器:**一种比较函数，它对一些对象集合进行总排序。可以将比较器传递给排序方法，以便对排序顺序进行精确控制。比较器还可以用来控制某些数据结构(如排序集或排序图)的顺序，或者为没有自然顺序的对象集合提供顺序。

**参数:**该方法取一个 comparator 类型的参数**比较器**，它是一个比较函数，对一些对象集合进行总排序。可以将比较器传递给排序方法，以便对排序顺序进行精确控制。比较器还可以用来控制某些数据结构(如排序集或排序图)的顺序，或者为没有自然顺序的对象集合提供顺序。

**返回值:**这个方法返回一个 Collector，根据传递的比较器产生最小值。

下面是一些示例来说明 minBy()的实现:

**程序 1:** 使用 naturalOrder()演示 minBy()

```
// Java code to show the implementation of
// Collectors minBy(Comparator comparator) function

import java.util.Comparator;
import java.util.Optional;
import java.util.stream.Collectors;
import java.util.stream.Stream;

class GFG {
    // Driver code
    public static void main(String[] args)
    {
        // creating a Stream of strings
        Stream<String> s = Stream.of("2", "3", "4", "5");

        // using Collectors minBy(Comparator comparator)
        // and finding the minimum element
        // in reverse order
        Optional<String> obj = s
                                   .collect(Collectors
                                                .minBy(Comparator
                                                           .naturalOrder()));

        // if present, print the element
        // else print the message
        if (obj.isPresent()) {
            System.out.println(obj.get());
        }
        else {
            System.out.println("no value");
        }
    }
}
```

**Output:**

```
2

```

**程序 2:** 使用 reverseOrder()演示 minBy()

```
// Java code to show the implementation of
// Collectors minBy(Comparator comparator) function

import java.util.Comparator;
import java.util.Optional;
import java.util.stream.Collectors;
import java.util.stream.Stream;

class GFG {
    // Driver code
    public static void main(String[] args)
    {
        // creating a Stream of strings
        Stream<String> s = Stream.of("2", "3", "4", "5");

        // using Collectors minBy(Comparator comparator)
        // and finding the minimum element
        // in reverse order
        Optional<String> obj = s
                                   .collect(Collectors
                                                .minBy(Comparator
                                                           .reverseOrder()));

        // if present, print the element
        // else print the message
        if (obj.isPresent()) {
            System.out.println(obj.get());
        }
        else {
            System.out.println("no value");
        }
    }
}
```

**Output:**

```
5

```

**程序 3:** 演示当没有值通过时的 minBy()。

```
// Java code to show the implementation of
// Collectors minBy(Comparator comparator) function

import java.util.Comparator;
import java.util.Optional;
import java.util.stream.Collectors;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // creating a Stream of strings
        Stream<String> s = Stream.of();

        // using Collectors minBy(Comparator comparator)
        // and finding the minimum element
        // in reverse order
        Optional<String> obj = s
                                   .collect(Collectors
                                                .minBy(Comparator
                                                           .reverseOrder()));

        // if present, print the element
        // else print the message
        if (obj.isPresent()) {
            System.out.println(obj.get());
        }
        else {
            System.out.println("no value");
        }
    }
}
```

**Output:**

```
no value

```