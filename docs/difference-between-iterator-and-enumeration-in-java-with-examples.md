# Java 中迭代器和枚举的区别及示例

> 原文:[https://www . geeksforgeeks . org/Java 中迭代器和枚举与示例的区别/](https://www.geeksforgeeks.org/difference-between-iterator-and-enumeration-in-java-with-examples/)

[**迭代器**](https://www.geeksforgeeks.org/iterators-in-java/) **:** 这是一个通用迭代器，因为我们可以将其应用于任何 Collection 对象。通过使用迭代器，我们可以执行读取和移除操作。它是枚举的改进版本，增加了元素移除功能。

每当我们想要枚举集合框架实现的所有接口(如集合、列表、队列、队列)中的元素，以及映射接口的所有实现类中的元素时，都必须使用迭代器。迭代器是整个集合框架唯一可用的游标。

**语法:**

```java
// Here "c" is any Collection object. itr is of
// type Iterator interface and refers to "c"
Iterator itr = c.iterator();
```

[**枚举**](https://www.geeksforgeeks.org/enum-in-java/) **:** 枚举(或 enum)是用户自定义的数据类型。它主要用于给整数常量赋值，这些名称使程序易于阅读和维护。在 Java 中(从 1.5 开始)，枚举使用枚举数据类型来表示。Java 枚举比 C/C++枚举更强大。在 Java 中，我们还可以向其中添加变量、方法和构造函数。枚举的主要目的是定义我们自己的数据类型(枚举数据类型)。

**语法:**

```java
// A simple enum example where enum is declared 
// outside any class (Note enum keyword instead of 
// class keyword) 
enum Color 
{ 
    RED, GREEN, BLUE; 
}
```

**迭代器和枚举的区别:**

枚举和迭代器的功能是相同的。使用枚举，你只能遍历和获取对象，像使用迭代器一样，我们也可以添加和移除对象。所以如果你想让
操作列表，迭代器会很有用，枚举是只读的。

<figure class="table">

| 迭代程序 | 列举 |
| --- | --- |
| 迭代器是一个通用游标，因为它适用于所有的集合类。 | 枚举不是通用游标，因为它只适用于旧类。 |
| 迭代器有 remove()方法。 | 枚举没有 remove()方法。 |
| 迭代器可以进行修改(例如，使用 remove()方法，它在遍历过程中从集合中移除元素)。 | 枚举接口充当只读接口，在遍历集合的元素时，不能对集合进行任何修改。 |
| 迭代器不是遗留接口。迭代器可以用来遍历 HashMap、LinkedList、ArrayList、HashSet、TreeMap、TreeSet。 | 枚举是一个遗留接口，用于遍历向量、哈希表。 |

</figure>