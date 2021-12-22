# Java 中的收集器 toSet()，示例

> 原文:[https://www . geesforgeks . org/collectors-to set-in-Java-with-examples/](https://www.geeksforgeeks.org/collectors-toset-in-java-with-examples/)

**收集器 toSet()** 返回一个收集器，该收集器将输入元素累积到一个新的集合中。无法保证返回的集合的类型、可变性、可序列化性或线程安全性。这是一个*无序*收集器，即收集操作不承诺保持输入元素的相遇顺序。

**语法:**

```
public static <T> Collector<T, ?, Set<T>> toSet()

```

其中:

*   **T:** 输入元素的类型。
*   **接口收集器< T，A，R > :** 将输入元素累积到可变结果容器中的可变约简操作，可选地在所有输入元素都被处理后将累积的结果转换为最终表示。还原操作可以顺序执行，也可以并行执行。
    *   **T:** 归约运算的输入元素类型。
    *   **A:** 还原操作的可变累加类型。
    *   **R:** 归约运算的结果类型。
*   **集合:**不包含重复元素的集合。更正式地说，集合不包含一对元素 e1 和 e2，因此 e1 等于(e2)，最多包含一个空元素。

**返回值:**将所有输入元素收集到一个集合中的收集器。

以下是说明 toSet()方法的示例:

**例 1:**

```
// Java code to show the implementation of
// Collectors toSet() function

import java.util.Set;
import java.util.stream.Collectors;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a Stream of strings
        Stream<String> s = Stream.of("Geeks",
                                     "for",
                                     "GeeksforGeeks",
                                     "Geeks Classes");

        // using Collectors toSet() function
        Set<String> mySet = s.collect(Collectors.toSet());

        // printing the elements
        System.out.println(mySet);
    }
}
```

**Output:**

```
[Geeks Classes, GeeksforGeeks, Geeks, for]

```

**例 2:**

```
// Java code to show the implementation of
// Collectors toSet() function

import java.util.Set;
import java.util.stream.Collectors;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // creating a Stream of strings
        Stream<String> s = Stream.of("1", "2", "3", "4");

        // using Collectors toSet() function
        Set<String> mySet = s.collect(Collectors.toSet());

        // printing the elements
        System.out.println(mySet);
    }
}
```

**Output:**

```
[1, 2, 3, 4]

```