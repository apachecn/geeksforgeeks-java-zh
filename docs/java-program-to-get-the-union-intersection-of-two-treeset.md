# Java 程序获取两个树集的并集&交集

> 原文:[https://www . geesforgeks . org/Java-program-to-get-union-inter 交集-two-treeset/](https://www.geeksforgeeks.org/java-program-to-get-the-union-intersection-of-two-treeset/)

两个树集合的[](https://en.wikipedia.org/wiki/Union_(set_theory))**是两个树集合中所有元素的集合。由于集合不包含重复值，因此两个树集合的并集也不包含重复值。两个树集的合并可以使用 [**addAll()**](https://www.geeksforgeeks.org/treeset-addall-method-in-java/) 方法从[**Java . util . treeset**](https://docs.oracle.com/javase/7/docs/api/java/util/TreeSet.html)完成。TreeSet 按照排序顺序存储不同的值，因此可以通过将 set2 添加到 set1 来完成联合，addAll()方法按照排序顺序添加 set1 中不存在的 set2 的所有值。**

**两个树集合的 [**交集**](https://en.wikipedia.org/wiki/Intersection_(set_theory)) 是集合 1 和集合 2 的所有相同元素的集合。两个树集合的交集也不包含重复值。可以使用 java.util.TreeSet 中的[**retainal()**](https://www.geeksforgeeks.org/treeset-retainall-method-in-java-with-example/)方法来完成两个树集的交集，retainal()方法会移除两个树集中所有不相同的元素。**

****示例:****

```java
**Input :** set1 = {10, 20, 30}
    set2 = {20, 30, 40, 50}

**Output:** Union = {10, 20, 30, 40, 50}
    Intersection = {20, 30}

**Input :** set1 = {a, b, c}
    set2 = {b, d, e}
**Output:** Union = {a, b, c, d, e}
    Intersection = {b}
```

**下面是实现:**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java Program to Get the Union
//& Intersection of Two TreeSet

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // New TreeSet1
        TreeSet<Integer> treeSet1 = new TreeSet<>();

        // Add elements to treeSet1
        treeSet1.add(10);
        treeSet1.add(20);
        treeSet1.add(30);

        // New TreeSet1
        TreeSet<Integer> treeSet2 = new TreeSet<>();

        // Add elements to treeSet2
        treeSet2.add(20);
        treeSet2.add(30);
        treeSet2.add(40);
        treeSet2.add(50);

        // Print the TreeSet1
        System.out.println("TreeSet1: " + treeSet1);

        // Print the TreeSet1
        System.out.println("TreeSet2: " + treeSet2);

        // New TreeSet
        TreeSet<Integer> union = new TreeSet<>();

        // Get a Union using addAll() method
        union.addAll(treeSet2);
        union.addAll(treeSet1);
        // Print the Union
        System.out.println("Union: " + union);

        // New TreeSet
        TreeSet<Integer> intersection = new TreeSet<>();
        intersection.addAll(treeSet1);
        intersection.retainAll(treeSet2);
        // Print the intersection
        System.out.println("Intersection: " + intersection);
    }
}
```

****Output**

```java
TreeSet1: [10, 20, 30]
TreeSet2: [20, 30, 40, 50]
Union: [10, 20, 30, 40, 50]
Intersection: [20, 30]
```**