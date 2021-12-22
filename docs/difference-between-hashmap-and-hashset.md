# 【HashMap 和 HashSet 的区别

> 原文:[https://www . geesforgeks . org/hashmap-和-hashset 之间的区别/](https://www.geeksforgeeks.org/difference-between-hashmap-and-hashset/)

[HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 是[设置接口](https://www.geeksforgeeks.org/set-in-java/)的实现，不允许重复值。最主要的是，存储在 HashSet 中的对象必须重写 equals()以检查是否相等，并且没有重复值的 hashCode()方法存储在我们的集中。 [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java/) 是[映射接口](https://www.geeksforgeeks.org/map-interface-java-examples/)的实现，将一个键映射为值。地图中不允许有重复的键。基本上，Map Interface 有两个实现类 HashMap 和 [TreeMap](https://www.geeksforgeeks.org/treemap-in-java/) 主要区别是 TreeMap 维护对象的顺序，而 HashMap 不会。HashMap 允许空值和空键。哈希集和哈希映射都不同步。

现在让我们用表格的方式来表达 HashMap 和 HashSet 之间的区别，如下所示:

<figure class="table">

| 基础 | 哈希集 | HashMap |
| --- | --- | --- |
| 工具 | 设置界面 | 地图界面 |
| 复制 | 不 | 是允许重复值，但不允许重复键 |
| 虚拟值 | 是 | 不 |
| 添加操作期间所需的对象 | one | Two |
| 添加和存储机制 | HashMap 对象 | 散列技术 |
| 速度 | 它比哈希映射相对慢 | 它比 HashSet 相对更快，因为这里使用了散列技术。 |
| 空 | 只有一个空值 | 单个空键和任意数量的空值 |
| 插入方法 | 添加() | 放() |

</figure>

让我们借助干净的 java 程序，通过窥视内部工作来掌握理解。

**例 1:** HashSet

## Java 语言（一种计算机语言，尤用于创建网站）

```java
// Java program to demonstrate working of HashSet

// Importing HashSet class from java.util package
import java.util.HashSet;

// Mai class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        HashSet<String> hs = new HashSet<String>();
        // Adding elements to the HashSet
        hs.add("geeks");
        hs.add("practice");
        hs.add("contribute");
        ;

        System.out.println(
            "Before adding duplicate values \n\n" + hs);

        // Addition of duplicate elements
        hs.add("geeks");
        hs.add("practice");

        System.out.println(
            "\nAfter adding duplicate values \n\n" + hs);

        // Addition of null values
        hs.add(null);
        hs.add(null);

        // Displaying HashSet elements
        System.out.println("\nAfter adding null values \n\n"
                           + hs);
    }
}
```

**Output**

```java
Before adding duplicate values 

[practice, geeks, contribute]

After adding duplicate values 

[practice, geeks, contribute]

After adding null values 

[null, practice, geeks, contribute]
```

**例 2:** HashMap

## Java 语言（一种计算机语言，尤用于创建网站）

```java
import java.util.HashMap;

public class HashMapExample {

    public static void main(String[] args)
    {

        // This is how to declare HashMap
        HashMap<Integer, String> hm = new HashMap<Integer, String>();

        // Adding elements to HashMap*/
        hm.put(12, "geeks");
        hm.put(2, "practice");
        hm.put(7, "contribute");

        System.out.println("\nHashMap object output :\n\n" + hm);

        // store data with duplicate key
        hm.put(12, "geeks");

        System.out.println("\nAfter inserting duplicate key :\n\n" + hm);
    }
}
```

**Output:** 

```java
HashMap object output :

{2=practice, 7=contribute, 12=geeks}

After inserting duplicate key :

{2=practice, 7=contribute, 12=geeks}
```

通过以上两个输出，在了解了它们的内部工作之后，现在我们可以谈论如下的概念差异:

1.  **实现:** HashMap 实现 Map 接口，HashSet 实现 Set 接口。
2.  **重复:**哈希集不允许重复值。HashMap 存储键、值对，并且不允许重复键。如果密钥是重复的，那么旧密钥将被新值替换。
3.  **存储对象时的对象数:** HashMap 需要放两个对象(K 键，V 值)才能给 HashMap 对象添加一个元素，而 HashSet 只需要添加一个对象(Object o)
4.  **伪值:**在 HashMap 中没有伪值的概念，
    HashSet 内部使用 HashMap 添加元素。在 HashSet 中， **add(Object)** 方法中传递的参数充当密钥 k。Java 在内部为 add(Object)方法中传递的每个值关联伪值。
5.  **存储或添加机制:** HashMap 内部使用哈希来存储或添加对象，HashSet 内部使用 HashMap 对象来存储或添加对象。
6.  **速度:** HashSet 比 HashMap 慢。
7.  **插入** HashMap 使用 put()方法存储数据，而在 HashSet 中使用 add()方法添加或存储数据。

让我们以一个例子结束

```java
HashSet is a set, e.g. {1, 2, 3, 4, 5, 6, 7},
HashMap is a key -> value pair(key to value) map, e.g. {a -> 1, b -> 2, c -> 2, d -> 1}
```

这里，在 HashMap 的例子中，不能有重复的键，但是它可能有重复的值。在哈希集中，不能有重复的元素