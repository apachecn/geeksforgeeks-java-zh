# 迭代器 vs Java 中的集合

> 原文:[https://www . geesforgeks . org/iterator-vs-collection-in-Java/](https://www.geeksforgeeks.org/iterator-vs-collection-in-java/)

[**【迭代器】**](https://www.geeksforgeeks.org/iterators-in-java/)[**集合**](https://www.geeksforgeeks.org/collections-in-java-2/) ，都曾多次帮助和安慰程序员。但是用法和应用有很大的区别。

**1。迭代器**

*   **申报**

```java
public interface Iterator

Type Parameters:
E - the type of elements returned by this iterator
```

*   迭代器在 Java 的 Collection 框架中用于逐个检索元素。
*   **方法总结**

<figure class="table">

| 修饰符和类型 | 方法 | 描述 |
| --- | --- | --- |
| 默认无效 | 前剩余(消费者 super E>行动) | 对剩余的每个元素执行给定的操作，直到所有元素都已处理完毕或该操作引发异常。 |
| 布尔 | 哈斯下一步() | 如果迭代包含更多元素，则返回 true。 |
| E | 下一个() | 返回迭代中的下一个元素。 |
| 默认无效 | 移除() | 从基础集合中移除此迭代器返回的最后一个元素(可选操作)。 |

</figure>

**2。收藏**

*   **申报:**

```java
public interface Collection<E> extends Iterable<E>

Type Parameters:
E - the type of elements returned by this iterator
```

*   集合是表示为单个单元的一组单个对象。Java 提供了集合框架，该框架定义了几个类和接口，将一组对象表示为一个单元。
*   **方法总结**

<figure class="table">

| 修饰符和类型 | 方法 | 描述 |
| --- | --- | --- |
| 布尔 | 添加(英、法) | 确保此集合包含指定的元素(可选操作)。 |
| 布尔 | addAll(集合〔t0〕c) | 将指定集合中的所有元素添加到此集合中(可选操作)。 |
| 空的 | 清除() | 从此集合中移除所有元素(可选操作)。 |
| 布尔 | 包含(对象 o) | 如果此集合包含指定的元素，则返回 true。 |
| 布尔 | 包含所有(集合> c) | 如果此集合包含指定集合中的所有元素，则返回 true。 |
| 布尔 | 等于(对象 0) | 将指定的对象与此集合进行比较，看是否相等。 |
| （同 Internationalorganizations）国际组织 | hashCode() | 返回此集合的哈希代码值。 |
| 布尔 | isEmpty() | 如果此集合不包含元素，则返回 true。 |
| 迭代器 | 迭代器() | 返回集合中元素的迭代器。 |
| 默认流 | 并行流() | 以此集合为源返回一个可能并行的流。 |
| 布尔 | 移除(对象 o) | 从该集合中移除指定元素的单个实例(如果存在)(可选操作)。 |
| 布尔 | 移除所有(集合> c) | 移除此集合中也包含在指定集合中的所有元素(可选操作)。 |
| 默认布尔值 | 移除 If(谓词 super E>过滤器) | 移除此集合中满足给定谓词的所有元素。 |
| 布尔 | 零售(集合> c) | 仅保留此集合中包含在指定集合中的元素(可选操作)。 |
| （同 Internationalorganizations）国际组织 | 大小() | 返回此集合中的元素数量。 |
| 默认 sppolitieator | 拆分器() | 在此集合中的元素上创建拆分器。 |
| 默认流 | 流() | 返回以此集合为源的顺序流。 |
| 对象[] | toarray() | 返回包含此集合中所有元素的数组。 |
| T[] | toaarray(t[]a) | 返回包含此集合中所有元素的数组；返回数组的运行时类型是指定数组的运行时类型。 |

</figure>

**迭代器与集合**

*   迭代器只能移动到**下一个()**元素或**移除()**元素。
    然而，集合可以**添加()**、迭代、**移除()**或**清除()**集合的元素。
*   迭代器提供了比集合更好的速度，因为迭代器接口的操作数量有限。
*   **java.sql.SQLException 扩展了 Iterable** 。因此，它允许调用者安全地迭代 SQLException 的原因。
    在这种情况下，使用集合将是昂贵的，因为在 n 个异常的链中，在 SQLException 接口中使用集合可能需要构造 O(n^2)元素。
    但是，Iterable 的使用提供了对异常链的 O(n)访问。