# Java 中 HashSet、LinkedHashSet 和 TreeSet 的异同

> 原文:[https://www . geeksforgeeks . org/hashset-link edhashset-and-treeset-in-Java/](https://www.geeksforgeeks.org/difference-and-similarities-between-hashset-linkedhashset-and-treeset-in-java/)

在本文中，我们将学习 HashSet 与 LinkedHashSet 和 TreeSet 之间的区别以及 LinkedHashSet 和 TreeSet 之间的相似之处。HashSet、LinkedHashSet 和 TreeSet 都实现了 Set 接口。因此，我们试图列出 java 中的 HashSet、LinkedHashSet 和 TreeSet 之间的异同。

【HashSet、LinkedHashSet 、**和 TreeSet 的区别:**

<figure class="table">

| 

特征

 | 

哈希集

 | 

LinkedHashSet

 | 

TreeSet(树集)

 |
| --- | --- | --- | --- |
| 内部工作 | HashSet 在内部使用 HashMap 来存储对象 | LinkedHashSet 在内部使用 LinkedHashMap 来存储对象 | TreeSet 在内部使用 TreeMap 来存储对象 |
| 何时使用 | 如果您不想保持插入顺序，但想存储唯一的对象

 | 如果您想保持元素的插入顺序，那么您可以使用 LinkedHashSet | 如果你想根据一些比较器对元素进行排序，那么就使用 TreeSet |
| 命令 | HashSet 不维护插入顺序 | LinkedHashSet 维护对象的插入顺序 | 而 TreeSet 根据提供的比较器对元素进行排序。默认情况下，对象将按照自然的升序排列。 |
| 操作的复杂性 | HashSet 为插入、移除和检索对象提供了 O(1)的复杂性 | LinkedHashSet 按照 O(1)的顺序给出插入、移除和检索操作的性能。 | 而 TreeSet 为插入、移除和检索操作提供了 O(log(n))阶的性能。

 |
| 表演 | 与 LinkedHashSet 和 TreeSet 相比，HashSet 的性能更好。 | LinkedHashSet 的性能比 TreeSet 慢。它几乎类似于 HashSet，但速度较慢，因为 LinkedHashSet 在内部维护 LinkedList 以维护元素的插入顺序 | 除了插入和移除操作之外，TreeSet 的性能优于 LinkedHashSet，因为它必须在每次插入和移除操作之后对元素进行排序。 |
| 比较 | HashSet 使用 equals()和 hashCode()方法来比较对象 | LinkedHashSet 使用 equals()和 hashCode()方法来比较它的对象 | TreeSet 使用 compare()和 compareTo()方法来比较对象 |
| 空元素 | HashSet 只允许一个空值。 | LinkedHashSet 只允许一个空值。 | TreeSet 不允许空值。如果将空值插入 TreeSet，它将引发 NullPointerException。 |
| 句法 | HashSet obj = new HashSet（）; | LinkedHashSet obj = new LinkedHashSet（）; | TreeSet obj = new TreeSet()： |

</figure>

**根据插入顺序和时间，哈希集、链接哈希集**、**和树集之间的差异:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate difference between
// HashSet, LinkedHashSet and TreeSet according
// to insertion order and insertion time

import java.util.Arrays;
import java.util.HashSet;
import java.util.LinkedHashSet;
import java.util.TreeSet;

class GFG1 {
    // Function show insertion order of
    // LinkedHashSet, TreeSet and HashSet

    private static void insertionOrder()
    {
        LinkedHashSet<String> geekLinkSet
            = new LinkedHashSet<>();
        TreeSet<String> geekTreeSet = new TreeSet<>();
        HashSet<String> geekHashSet = new HashSet<String>();

        // Add three object in
        // LinkedHashSet and TreeSet
        for (String str : Arrays.asList("Geek2", "Geek1",
                                        "Geek3", "Geek1")) {

            geekLinkSet.add(str);
            geekTreeSet.add(str);
            geekHashSet.add(str);
        }

        // should be sorted order HashSet
        // stores element in sorted order
        System.out.println("Insertion Order"
                           + " of objects in HashSet :"
                           + geekHashSet);

        // insertion order or elements LinkedHashSet
        // storeds elements as insertion
        System.out.println("Insertion Order of "
                           + "objects in LinkedHashSet :"
                           + geekLinkSet);

        // should be sorted order TreeSet
        // stores element in sorted order
        System.out.println("Insertion Order of"
                           + " objects in TreeSet :"
                           + geekTreeSet);
    }

    // Function calculate insertion time of
    // 1000 objects of LinkedHashSet,
    // TreeSet and HashSet

    private static void insertionTime()
    {
        // HashSet performance Test
        // inserting 1000 elements
        HashSet<Integer> numbersHS = new HashSet<>();
        long startTime = System.nanoTime();
        for (int i = 0; i < 1000; i++) {
            numbersHS.add(i);
        }
        long endTime = System.nanoTime();
        System.out.println("Total time to insert"
                           + " 1000 elements in"
                           + " HashSet in nanoseconds: "
                           + (endTime - startTime));

        // LinkedHashSet performance Test
        // inserting 1000 elements
        LinkedHashSet<Integer> numbersLLS
            = new LinkedHashSet<>();

        startTime = System.nanoTime();
        for (int i = 0; i < 1000; i++) {
            numbersLLS.add(i);
        }
        endTime = System.nanoTime();
        System.out.println("Total time to insert"
                           + " 1000 elements in"
                           + " LinkedHashSet nanoseconds: "
                           + (endTime - startTime));

        // TreeSet performance Test inserting 1000 objects
        TreeSet<Integer> numbersTS = new TreeSet<>();

        startTime = System.nanoTime();
        for (int i = 0; i < 1000; i++) {
            numbersTS.add(i);
        }
        endTime = System.nanoTime();
        System.out.println("Total time to insert"
                           + " 1000 elements in"
                           + " TreeSet in nanoseconds: "
                           + (endTime - startTime));
    }

    // Function calculate deletion time
    // of 1000 objects LinkedHashSet,
    // TreeSet and HashSet
    // Deletion time always vary
    private static void deletion()
    {
        // HashSet performance Test inserting
        // and deletion 1000 elements
        HashSet<Integer> deletionHS = new HashSet<>();

        for (int i = 0; i < 1000; i++) {
            deletionHS.add(i);
        }

        long startingTime = System.nanoTime();
        for (int i = 0; i < 1000; i++) {
            deletionHS.remove(i);
        }

        long endedTime = System.nanoTime();
        System.out.println(
            "Total time to Deletion "
            + "1000 elements in HashSet in nanoseconds: "
            + Math.abs(startingTime - endedTime));

        // LinkedHashSet  performance Test inserting
        // and deletion 1000 elements
        LinkedHashSet<Integer> deletionLLS
            = new LinkedHashSet<>();

        for (int i = 0; i < 1000; i++) {
            deletionLLS.add(i);
        }
        startingTime = System.nanoTime();
        for (int i = 0; i < 1000; i++) {
            deletionLLS.remove(i);
        }

        endedTime = System.nanoTime();
        System.out.println(
            "Total time to Deletion 1000"
            + " elements in LinkedHashSet in nanoseconds: "
            + Math.abs(startingTime - endedTime));

        // TreeSet performance Test inserting
        // and deletion 1000 elements
        TreeSet<Integer> deletionTS = new TreeSet<>();

        for (int i = 0; i < 1000; i++) {
            deletionTS.add(i);
        }

        startingTime = System.nanoTime();
        for (int i = 0; i < 1000; i++) {
            deletionTS.remove(i);
        }

        endedTime = System.nanoTime();
        System.out.println(
            "Total time to Deletion 1000"
            + " elements in TreeSet in nanoseconds: "
            + Math.abs(startingTime - endedTime));
    }

    public static void main(String args[])
    {

        insertionOrder();
        insertionTime();
        deletion();
    }
}
```

**Output**

```java
Insertion Order of objects in HashSet :[Geek3, Geek2, Geek1]
Insertion Order of objects in LinkedHashSet :[Geek2, Geek1, Geek3]
Insertion Order of objects in TreeSet :[Geek1, Geek2, Geek3]
Total time to insert 1000 elements in HashSet in nanoseconds: 791869
Total time to insert 1000 elements in LinkedHashSet nanoseconds: 882417
Total time to insert 1000 elements in TreeSet in nanoseconds: 11797657
Total time to Deletion 1000 elements in HashSet in nanoseconds: 834509
Total time to Deletion 1000 elements in LinkedHashSet in nanoseconds: 898922
Total time to Deletion 1000 elements in TreeSet in nanoseconds: 7437577
```

【HashSet、LinkedHashSet 、**和 TreeSet 的相似之处:**

*   重复:HashSet、LinkedHashSet、TreeSet 都是实现 Set 接口，所以不允许存储重复的对象。

*   线程安全:如果我们想在多线程环境中使用 HashSet、LinkedHashSet 和 TreeSet，那么首先我们要使其外部同步，因为 LinkedHashSet 和 TreeSet 都不是线程安全的。

*   这三个都是可克隆的和可序列化的。

**何时使用 HashSet、TreeSet** 、**以及 Java 中的 linked HashSet:**

1.  **HashSet:** 如果不想维持插入顺序但想存储唯一对象。
2.  **LinkedHashSet:** 如果想要保持元素的插入顺序，那么可以使用 LinkedHashSet。
3.  **TreeSet:** 如果你想根据某个比较器对元素进行排序，那么就使用 TreeSet。

因此，正如您根据这一点和您的要求看到上述程序的输出一样，您可以从 HashSet、TreeSet 和 LinkedHashSet 中选择任何人。