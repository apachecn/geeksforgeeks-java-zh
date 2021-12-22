# 【Collection.stream()之间的差异。Java 中的 forEach()和 Collection.forEach()

> 原文:[https://www . geesforgeks . org/collection-stream-foreach-and-collection-foreach-in-Java/](https://www.geeksforgeeks.org/difference-between-collection-stream-foreach-and-collection-foreach-in-java/)

Collection.forEach()和 Collection.stream()。forEach()用于迭代集合，两者之间没有太大的区别，因为两者给出了相同的结果，尽管它们的内部工作方式有些不同。

**Collection.stream()。forEach()** 基本上用于一组对象中的迭代，方法是将一个集合转换为流，然后迭代集合的流。迭代集合时，如果对集合进行了任何结构更改，那么它将引发并发修改异常。

**Collection.forEach()** 使用集合的迭代器(以指定的为准)。大多数集合在遍历该集合时不允许修改结构。如果该集合发生任何更改，即添加元素或移除元素，那么它们将引发并发修改错误。如果 collection.forEach()正在迭代一个同步的集合，那么它们将锁定该集合的段，并将其保留在所有可以对该集合进行的调用上。

### Collection.stream()之间的差异。forEach()和 Collection.forEach()

<figure class="table">

| 

**Collection.stream()。forEach()**

 | **Collection.forEach()** |
| --- | --- |
| Collection.stream()。forEach()也用于迭代集合，但它首先将集合转换为流，然后迭代集合的流。 | Collection.forEach()使用集合迭代器。 |
| 与 Collection.forEach()不同，它不以任何特定的顺序执行，即没有定义顺序。 | 如果指定了迭代顺序，则总是按迭代顺序执行。 |
| 在集合的结构修改过程中，稍后将引发异常。 | 如果我们使用 collection.forEach()在集合中执行任何结构修改，它将立即引发异常。 |
| 如果迭代发生在同步集合上，那么它不会锁定集合。 | 如果迭代发生在同步集合上，那么它会锁定集合并在所有调用中保持它。 |

</figure>

下面是一个展示 Collection.stream.forEach()用法的 Java 程序:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to show the demonstration of
// Collection.stream().forEach()
import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        List<Integer> list = new ArrayList<>();

        list.add(5);
        list.add(6);
        list.add(3);
        list.add(4);
        // printing each element of list using forEach loop
        list.stream().forEach(System.out::print);
    }
}
```

**Output**

```
5634
```

下面是一个展示 Collection.forEach()方法用法的 Java 程序:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to show the demonstration of
// Collection.forEach()
import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        List<Integer> list = new ArrayList<>();

        list.add(5);
        list.add(6);
        list.add(3);
        list.add(4);
        // printing each element of list
        list.forEach(System.out::print);
    }
}
```

**Output**

```
5634
```