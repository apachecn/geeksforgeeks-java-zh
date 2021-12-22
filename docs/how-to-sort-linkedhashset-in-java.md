# 如何在 Java 中对 LinkedHashSet 进行排序？

> 原文:[https://www . geesforgeks . org/how-sort-link edhashset-in-Java/](https://www.geeksforgeeks.org/how-to-sort-linkedhashset-in-java/)

[链接哈希集](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/)是[哈希集](https://www.geeksforgeeks.org/hashset-in-java/)的有序版本，在所有元素中维护一个[双链表](https://www.geeksforgeeks.org/data-structures/linked-list/doubly-linked-list/)。当[迭代](https://www.geeksforgeeks.org/iterating-arraylists-java/)一个 HashSet 时，顺序是不可预测的，而 LinkedHashSet 让我们按照元素插入的顺序迭代元素。当使用[迭代器](https://www.geeksforgeeks.org/iterators-in-java/)在 LinkedHashSet 中循环时，元素将按照它们被插入的顺序返回。

Java 中有三种方法可以对 LinkedHashSet 进行排序。以下哪一项:

*   使用[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)
*   使用[树集](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)
*   使用[流](https://www.geeksforgeeks.org/stream-in-java/)

**方法 1(使用数组列表)**

在这个方法中，我们将 LinkedHashSet 转换成一个 ArrayList，然后使用[集合](https://www.geeksforgeeks.org/collections-in-java-2/)类的 [sort()](https://www.geeksforgeeks.org/collections-sort-java-examples/) **方法**对 ArrayList 进行排序。

```
// Convert LinkedHashSet to an ArrayList
ArrayList<Integer> array = new ArrayList<>(set);

// sort ArrayList
Collections.sort(array);
```

**申报**

```
public static void sort(List myList)
```

**参数:** *myList* 是我们要排序的一个对象。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate how to sort LinkedHashSet
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // New Empty LinkedHashSet
        LinkedHashSet<Integer> set = new LinkedHashSet<>();

        // Adding elements
        set.add(10);
        set.add(50);
        set.add(20);
        set.add(40);
        set.add(30);

        // Print LinkedHashSet before sort
        System.out.println("Before sort: " + set);

        // Convert LinkedHashSet to an ArrayList
        ArrayList<Integer> array = new ArrayList<>(set);

        // sort ArrayList
        Collections.sort(array);

        // Print after sort
        System.out.println("After sort: " + array);
    }
}
```

**Output**

```
Before sort: [10, 50, 20, 40, 30]
After sort: [10, 20, 30, 40, 50]
```

**方法二:使用** [**树集**](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)

在这个方法中，我们使用 [**构造函数**](https://www.geeksforgeeks.org/constructors-c/) 将 LinkedHashSet 转换为一个 TreeSet，以自动对元素进行排序。

```
// Convert LinkedHashSet to a TreeSet
TreeSet<Integer> tree_set = new TreeSet<>(set);
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate how to sort LinkedHashSet
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // New Empty LinkedHashSet
        LinkedHashSet<Integer> set = new LinkedHashSet<>();

        // Adding elements
        set.add(10);
        set.add(50);
        set.add(20);
        set.add(40);
        set.add(30);

        // Print LinkedHashSet before sort
        System.out.println("Before sort: " + set);

        // Convert LinkedHashSet to a TreeSet using
        // constructor
        TreeSet<Integer> tree_set = new TreeSet<>(set);

        // Print after sort
        System.out.println("After sort: " + tree_set);
    }
}
```

**Output**

```
Before sort: [10, 50, 20, 40, 30]
After sort: [10, 20, 30, 40, 50]
```

**方法 3:使用流**

在这个方法中，我们使用流和流的 [sorted()](https://www.geeksforgeeks.org/stream-sorted-in-java/) 函数对 LinkedHashSet 进行排序。

```
// Sort and print using stream
set.stream().sorted().forEach(System.out::println);
```

下面是实现:

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate how to sort LinkedHashSet
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // New Empty LinkedHashSet
        LinkedHashSet<Integer> set = new LinkedHashSet<>();

        // Adding elements
        set.add(10);
        set.add(50);
        set.add(20);
        set.add(40);
        set.add(30);

        // Print LinkedHashSet before sort
        System.out.println("Before sort: " + set);

        // Print after sort
        System.out.println("After sort: ");

        // Sort and print using stream
        set.stream().sorted().forEach(System.out::println);
    }
}
```

**Output**

```
Before sort: [10, 50, 20, 40, 30]
After sort: 
10
20
30
40
50
```