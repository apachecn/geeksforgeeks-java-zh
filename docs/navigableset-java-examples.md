# Java 导航集，示例

> 原文:[https://www.geeksforgeeks.org/navigableset-java-examples/](https://www.geeksforgeeks.org/navigableset-java-examples/)

NavigableSet 表示 [Java 集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)中的一个可导航集合。导航设置界面继承自[排序设置界面](https://www.geeksforgeeks.org/sortedset-java-examples/)。它的行为类似于排序集，除了排序集的排序机制之外，我们还有可用的导航方法。
例如，导航集界面可以以与排序集中定义的顺序相反的顺序导航集合。可以按升序或降序访问和遍历导航集。实现这个接口的类有， [TreeSet](https://www.geeksforgeeks.org/treeset-in-java/) 和 [ConcurrentSkipListSet](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentSkipListSet.html)

![NavigableSet in Java with Examples](img/fe0ed9520fa852c7d04e9ee3455bc168.png)

这里，E 是这个集合维护的元素类型。

**所有超界面:**

集合<e>、可迭代<e>、[集合<E>T3、](https://www.geeksforgeeks.org/set-in-java/)[排序集合<E>T5】](https://www.geeksforgeeks.org/sortedset-java-examples/)</e></e>

**所有已知的实现类:**

[并发 kipListSet](https://www.geeksforgeeks.org/concurrentskiplistset-in-java-with-examples/) 、 [TreeSet <和>](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)

**声明:**导航集声明为

> 公共界面导航集<e>扩展排序集</e>

**创建导航集对象**

由于导航集是一个接口，因此不能创建导航集类型的对象。我们总是需要一个扩展这个列表的类来创建一个对象。此外，在 Java 1.5 中引入泛型后，可以限制导航集中可以存储的对象类型。这种类型安全集合可以定义为:

> // Obj 是要存储在导航集中的对象的类型
> 
> navigatableset<obj>set = new TreeSet<obj>()；</obj></obj>

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// the working of NavigableSet
import java.util.NavigableSet;
import java.util.TreeSet;

public class NavigableSetDemo
{
    public static void main(String[] args)
    {
        NavigableSet<Integer> ns = new TreeSet<>();
        ns.add(0);
        ns.add(1);
        ns.add(2);
        ns.add(3);
        ns.add(4);
        ns.add(5);
        ns.add(6);

        // Get a reverse view of the navigable set
        NavigableSet<Integer> reverseNs = ns.descendingSet();

        // Print the normal and reverse views
        System.out.println("Normal order: " + ns);
        System.out.println("Reverse order: " + reverseNs);

        NavigableSet<Integer> threeOrMore = ns.tailSet(3, true);
        System.out.println("3 or  more:  " + threeOrMore);
        System.out.println("lower(3): " + ns.lower(3));
        System.out.println("floor(3): " + ns.floor(3));
        System.out.println("higher(3): " + ns.higher(3));
        System.out.println("ceiling(3): " + ns.ceiling(3));

        System.out.println("pollFirst(): " + ns.pollFirst());
        System.out.println("Navigable Set:  " + ns);

        System.out.println("pollLast(): " + ns.pollLast());
        System.out.println("Navigable Set:  " + ns);

        System.out.println("pollFirst(): " + ns.pollFirst());
        System.out.println("Navigable Set:  " + ns);

        System.out.println("pollFirst(): " + ns.pollFirst());
        System.out.println("Navigable Set:  " + ns);

        System.out.println("pollFirst(): " + ns.pollFirst());
        System.out.println("Navigable Set:  " + ns);

        System.out.println("pollFirst(): " + ns.pollFirst());
        System.out.println("pollLast(): " + ns.pollLast());
    }
}
```

**Output**

```java
Normal order: [0, 1, 2, 3, 4, 5, 6]
Reverse order: [6, 5, 4, 3, 2, 1, 0]
3 or  more:  [3, 4, 5, 6]
lower(3): 2
floor(3): 3
higher(3): 4
ceiling(3): 3
pollFirst(): 0
Navigable Set:  [1, 2, 3, 4, 5, 6]
pollLast(): 6
Navigable Set:  [1, 2, 3, 4, 5]
pollFirst(): 1
Navigable Set:  [2, 3, 4, 5]
pollFirst(): 2
Navigable Set:  [3, 4, 5]
pollFirst(): 3
Navigable Set:  [4, 5]
pollFirst(): 4
pollLast(): 5

```

### 在导航集上执行各种操作

由于 NavigableSet 是一个接口，因此它只能与实现该接口的类一起使用。TreeSet 是实现 NavigableSet 接口的类。现在，让我们看看如何在 TreeSet 上执行一些常用的操作。

**1。添加元素:**为了给导航集添加一个元素，我们可以使用 [add()](https://www.geeksforgeeks.org/navigableset-add-method-in-java/?ref=rp) 方法。但是，插入顺序不会保留在树集中。在内部，对于每个元素，值都是按升序进行比较和排序的。我们需要注意，重复的元素是不允许的，所有重复的元素都会被忽略。此外，导航集不接受空值。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to demonstrate
// adding of elements in
// NavigableSet
import java.util.*;
import java.io.*;

class NavigableSetDemo {

    public static void main(String[] args)
    {
        NavigableSet<String> ts = new TreeSet<String>();

        // Elements are added using add() method
        ts.add("A");
        ts.add("B");
        ts.add("C");
        ts.add("A");

        System.out.println(ts);
    }
}
```

**输出:**

```java
[A, B, C]

```

**2。访问元素:**添加元素后，如果我们希望访问元素，我们可以使用内置方法，如 contains()，first()，last()，等。

*   [包含()](https://www.geeksforgeeks.org/sortedset-contains-method-in-java-with-examples/)
*   [第一个()](https://www.geeksforgeeks.org/sortedset-first-method-in-java/)
*   [最后()](https://www.geeksforgeeks.org/sortedset-last-method-in-java/)

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to access
// the elements of NavigableSet
import java.util.*;
import java.io.*;

class NavigableSetDemo {

    public static void main(String[] args)
    {
        NavigableSet<String> ts = new TreeSet<String>();

        // Elements are added using add() method
        ts.add("A");
        ts.add("B");
        ts.add("C");
        ts.add("A");

        System.out.println("Navigable Set is " + ts);

        String check = "D";

        // Check if the above string exists in
        // the NavigableSet or not
        System.out.println("Contains " + check + " "
                           + ts.contains(check));

        // Print the first element in
        // the NavigableSet
        System.out.println("First Value " + ts.first());

        // Print the last element in
        // the NavigableSet
        System.out.println("Last Value " + ts.last());
    }
}
```

**输出:**

```java
Navigable Set is [A, B, C]
Contains D false
First Value A
Last Value C

```

**3。移除值:**可以使用 remove()、pollFirst()、pollLast()方法从导航集中移除值。

*   [移除()](https://www.geeksforgeeks.org/sortedset-remove-method-in-java-with-examples/)
*   [pollFirst()](https://www.geeksforgeeks.org/navigableset-pollfirst-method-in-java/?ref=rp)
*   [pollLast()](https://www.geeksforgeeks.org/navigableset-polllast-method-in-java/?ref=rp)

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to remove the
// elements from NavigableSet
import java.util.*;
import java.io.*;

class NavigableSetDemo {

    public static void main(String[] args)
    {
        NavigableSet<String> ts = new TreeSet<String>();

        // Elements are added using add() method
        ts.add("A");
        ts.add("B");
        ts.add("C");
        ts.add("B");
        ts.add("D");
        ts.add("E");

        System.out.println("Initial TreeSet " + ts);

        // Removing the element b
        ts.remove("B");

        System.out.println("After removing element " + ts);

        // Remove the First element of TreeSet
        ts.pollFirst();

        System.out.println(
            "After the removal of First Element " + ts);

        // Remove the Last element of TreeSet
        ts.pollLast();

        System.out.println(
            "After the removal of Last Element " + ts);
    }
}
```

**输出:**

```java
Initial TreeSet [A, B, C, D, E]
After removing element [A, C, D, E]
After the removal of First Element [C, D, E]
After the removal of Last Element [C, D]

```

**4。遍历导航集:**有多种方法可以遍历导航集。最著名的一个是使用[增强为循环。](https://www.geeksforgeeks.org/loops-in-java/)

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to iterate
// through NavigableSet

import java.util.*;
import java.io.*;

class NavigableSetDemo {

    public static void main(String[] args)
    {
        NavigableSet<String> ts = new TreeSet<String>();

        // Elements are added using add() method
        ts.add("C");
        ts.add("D");
        ts.add("E");
        ts.add("A");
        ts.add("B");
        ts.add("Z");

        // Iterating though the NavigableSet
        for (String value : ts)
            System.out.print(value + ", ");
        System.out.println();
    }
}
```

**输出:**

```java
A, B, C, D, E, Z,  

```

### 导航集的方法

以下是 NavigableSet 界面中的方法。

<figure class="table">

| 

METHOD

 | 

DESCRIPTION

 |
| --- | --- |
| [ceiling (e)](https://www.geeksforgeeks.org/navigableset-ceiling-method-in-java/) | Returns the minimum element in the collection that is greater than or equal to the given element, or null if there is no such element. |
| [[order reducer] (](https://www.geeksforgeeks.org/navigableset-descendingiterator-method-in-java/) | ) returns iterators of elements in this collection in descending order. |
| [下降集()](https://www.geeksforgeeks.org/navigableset-descendingset-method-in-java/) | Returns the reverse view of the elements contained in this collection. |
| [楼(戊)](https://www.geeksforgeeks.org/navigableset-floor-method-in-java/) | Returns the largest element in the collection that is less than or equal to the given element, or null if there is no such element. |
| [耳机(和托儿)](https://www.geeksforgeeks.org/navigableset-headset-method-in-java/) | Returns a view of the part of the collection whose elements are strictly smaller than to element. |
| [耳机(和托勒密·吴经熊)](headSet​(E toElement, boolean inclusive)) | Returns a view of the part of the collection where the element is less than (or equal to, if true) to element. |
| [higher (e e)](https://www.geeksforgeeks.org/navigableset-higher-method-in-java/) | Returns the minimum element in the collection that is strictly larger than the given element, or null if there is no such element. |
| [Iterator ()](https://www.geeksforgeeks.org/navigableset-iterator-method-in-java/) | Returns iterators of elements in this collection in ascending order. |
| [下(东/东)](https://www.geeksforgeeks.org/navigableset-lower-method-in-java/) | Returns the largest element in the collection that is strictly smaller than the given element, or null if there is no such element. |
| [投票第一()](https://www.geeksforgeeks.org/navigableset-pollfirst-method-in-java/) | Retrieve and remove the first (lowest) element, or return null if the collection is empty. |
| [投票最后()](https://www.geeksforgeeks.org/navigableset-polllast-method-in-java/) | Retrieve and delete the last (highest) element, or return null if the collection is empty. |
| [subSet(E fromElement，boolean](https://www.geeksforgeeks.org/navigableset-subset-method-in-java/)[from inclusive，E toElement，boolean to inclusive)](https://www.geeksforgeeks.org/navigableset-subset-method-in-java/) | Returns a view of the part of the collection whose elements range from from element to toElement. |
| [子集(E fromElement，E toElement)](https://www.geeksforgeeks.org/navigableset-subset-method-in-java/) | Returns a view of the part of the collection whose elements range from from element to toElement. |
| 尺寸集(E fromElement) | Returns a view of the part of the collection whose element is greater than or equal to from element. |
| 尺寸集(E fromElement，rúblig)和尺寸集(fromelement，rürür) | Returns a view of the part of the collection where the element is greater than (or equal to, if true) from element. |

</figure>

### 
从接口 java.util.SortedSet 继承的方法

<figure class="table">

| 

方法

 | 

描述

 |
| --- | --- |
| [比较器()](https://www.geeksforgeeks.org/treeset-comparator-method-in-java/) | 此方法返回用于对该集合中的元素进行排序的比较器，如果该集合使用其元素的自然排序，则返回 null。 |
| [第一个()](https://www.geeksforgeeks.org/sortedset-first-method-in-java/) | 此方法返回该集合中的第一个(最低的)元素。 |
| [最后()](https://www.geeksforgeeks.org/sortedset-last-method-in-java/) | 此方法返回集合中最后(最高)的元素。 |
| 拆分器() | 在此排序集中的元素上创建拆分器。 |

</figure>

### 从接口 java.util.Set 继承的方法

<figure class="table">

| 

方法

 | 

描述

 |
| --- | --- |
| [添加(元素)](https://www.geeksforgeeks.org/set-add-method-in-java-with-examples/) | 此方法用于向集合中添加特定元素。只有当集合中没有指定的元素时，函数才会添加元素，否则，如果集合中已经有元素，函数将返回 False。 |
| add all(集合) | 此方法用于将上述集合中的所有元素追加到现有集合中。元素是随机添加的，没有遵循任何特定的顺序。 |
| [晴()](https://www.geeksforgeeks.org/set-clear-method-in-java-with-examples/) | 此方法用于从集合中移除所有元素，但不删除集合。集合的引用仍然存在。 |
| [含有(元素)](https://www.geeksforgeeks.org/set-contains-method-in-java-with-examples/) | 此方法用于检查集合中是否存在特定元素。 |
| [包含所有(集合)](https://www.geeksforgeeks.org/set-containsall-method-in-java-with-examples/) | 此方法用于检查集合是否包含给定集合中存在的所有元素。如果集合包含所有元素，则此方法返回 true 如果缺少任何元素，则返回 false。 |
| [等于()](https://www.geeksforgeeks.org/set-equals-method-in-java-with-examples/) | 将指定的对象与此相等集进行比较。 |
| [hashCode()](https://www.geeksforgeeks.org/set-hashcode-method-in-java-with-examples/) | 此方法用于获取该集合实例的哈希码值。它返回一个整数值，该整数值是该集合实例的哈希码值。 |
| [【isempty()](https://www.geeksforgeeks.org/navigableset-isempty-method-in-java/?ref=rp) | 此方法用于检查导航集是否为空。 |
| [移除(元素)](https://www.geeksforgeeks.org/set-remove-method-in-java-with-examples/) | 此方法用于从集合中移除给定的元素。如果集合中存在指定的元素，此方法返回真，否则返回假。 |
| [移除所有(集合)](https://www.geeksforgeeks.org/set-removeall-method-in-java-with-examples/) | 此方法用于从集合中移除集合中存在的所有元素。如果此集合因调用而改变，则此方法返回 true。 |
| [零售(集合)](https://www.geeksforgeeks.org/set-retainall-method-in-java-with-example/) | 此方法用于保留给定集合中提到的集合中的所有元素。如果此集合因调用而改变，则此方法返回 true。 |
| [尺寸()](https://www.geeksforgeeks.org/set-size-method-in-java-with-example/) | 此方法用于获取集合的大小。这将返回一个表示元素数量的整数值。 |
| [toaarray()](https://www.geeksforgeeks.org/set-toarray-method-in-java-with-example/) | 此方法用于形成与集合元素相同元素的数组。 |
| toaarray(t[]a) | 返回包含该集合中所有元素的数组；返回数组的运行时类型是指定数组的运行时类型。 |

</figure>

### 接口 java.util.Collection 中声明的方法

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| 并行流() | 以此集合为源返回一个可能并行的流。 |
| 移除 If(谓词 super E>过滤器) | 移除此集合中满足给定谓词的所有元素。 |
| 流() | 返回以此集合为源的顺序流。 |
| toArray (IntFunction <t>生成器)</t> | 使用提供的生成器函数分配返回的数组，返回包含此集合中所有元素的数组。 |

</figure>

### 在接口 java.lang.Iterable 中声明的方法

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| [forEach(消费者<？超 T >动作)](https://www.geeksforgeeks.org/iterable-foreach-method-in-java-with-examples/) | 对 Iterable 的每个元素执行给定的操作，直到所有元素都被处理完或者该操作引发异常。 |

</figure>

本文由 [**Pratik Agarwal**](https://www.facebook.com/Pratik.Agarwal01) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。