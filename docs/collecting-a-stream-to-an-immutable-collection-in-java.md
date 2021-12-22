# 在 Java 中将流收集到不可变集合中

> 原文:[https://www . geesforgeks . org/collecting-a-stream-to-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a-a](https://www.geeksforgeeks.org/collecting-a-stream-to-an-immutable-collection-in-java/)

流和收集器在 Java 8 中引入了流的概念。流是一个序列，一个对象序列。我们从数组、列表等输入源生成流。，并支持聚合操作，如筛选、映射、限制、减少等。我们使用流来传输数据，并最终将其收集到某种形式的收集器中。收集器只是用来存储流处理结果的容器。收集器可以是列表、地图或集合。

一个[不可变集合](https://www.geeksforgeeks.org/immutable-list-in-java/)是一个我们一旦创建就不能改变其值的集合。我们确实需要不可变的集合，因为很多时候我们可以拥有不变的数据集合，即查找列表。例如，一年中的月份列表或一周中的天数列表等。使这样的列表(包含不变的数据)不变会使它们更节省内存和空间。它们本质上也是线程安全的。一般来说，不可变对象比可变对象需要更少的内存。

> 如果一个对象的状态在构造后不能改变，那么它就被认为是不可变的。创建集合的不可变实例后，只要对它的引用存在，它就会保存相同的数据。

**方法:**根据 java 版本的不同，根据 Java 版本的进步，有多种方法可用于创建不可变对象，我们可以使用这些方法创建不可变集合。

1.  Java 10 之前
    *   使用“*集合*创建流并将其收集到不可修改的结构中
    *   谷歌的番石榴图书馆
2.  Java 10 之后
    *   *tou modifiable list()*
    *   *图元可修饰图()*
    *   *tou modifiable set()*

### 场景 1:Java 10 之前

**方法 1:** 创建流并将其收集到不可修改的结构中。在 Java 10 之前，没有用 Java 创建不可变集合的直接方法。一种方法是创建一个流，并使用“*收集”方法将其收集到一个不可修改的结构中。*

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate Collecting a Stream to an
// Immutable Collection
// Pre java 10
// Using collectingAndThen method

// Importing Collections, Collectors and Stream classes
// from java.util package
import java.util.Collections;
import java.util.stream.Collectors;
import java.util.stream.Stream;

// Main class
// PreJava10ImmutableCollections
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Custom inputs integer elements in List
        var unmodifiableList
            = Stream.of(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)
                  .collect(Collectors.collectingAndThen(
                      Collectors.toList(),
                      Collections::unmodifiableList));

        System.out.println(unmodifiableList);

        // Operations like this will result in an exception
        unmodifiableList.add(12);
    }
}
```

**输出:**

![](img/3fdaf1e9a510fe5404343d19a1971436.png)

**方法二:**使用谷歌的番石榴库。为此，需要一个先决条件，即包含 JAR 文件。番石榴库的 JAR 是[下载](https://search.maven.org/classic/#search%7Cgav%7C1%7Cg%3A%22com.google.guava%22%20AND%20a%3A%22guava%22)JAR 并将其添加到 eclipse 中的构建路径中。番石榴图书馆提供了不变的列表类。下面给出了一个相同的例子。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate Collecting a
// Stream to an Immutable Collection
// Pre java 10  Using Google’s Guava library

// Importing Guava library
import com.google.common.collect.ImmutableList;
// Importing classes from java.util package
import java.util.List;
import java.util.stream.IntStream;

// Main class
public class PreJava10ImmutableCollections {

    // main driver method
    public static void main(String[] args) {

        // Using the Guava Libraries
        List<Integer> someList
            = IntStream.range(0, 15).boxed().collect(
                  ImmutableList.toImmutableList());

        // Print and display the elements
        System.out.println(someList);
    }
}
```