# Java 中列表和集合的区别

> 原文:[https://www . geesforgeks . org/Java 中列表和集合的区别/](https://www.geeksforgeeks.org/difference-between-list-and-set-in-java/)

[**列表界面**](https://www.geeksforgeeks.org/list-interface-java-examples/) 允许存储有序集合。是[收藏](https://www.geeksforgeeks.org/collections-in-java-2/)的子界面。它是对象的有序集合，其中允许存储重复的值。列表保留插入顺序，它允许位置访问和元素插入。

**申报:**

```java
public abstract interface List extends Collection
```

[java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包中的 [**设置界面**](https://www.geeksforgeeks.org/set-in-java/) 并扩展[集合界面](https://www.geeksforgeeks.org/collections-in-java-2/)是一个无序的对象集合，其中不能存储重复的值。这是一个实现数学集合的接口。此接口包含从集合接口继承的方法，并添加了一个限制插入重复元素的功能。

**声明:**设置界面声明为:

```java
public interface Set extends Collection
```

**示例:**

```java
Input :  Add Elements = [1, 2, 3, 1]
Output:  Set = [1, 2, 3]
     List = [1, 2, 3, 1]

Input :  Add Elements = [a, b, d, b]
Output:  Set = [a, b, d]
     List = [a, b, d, b]
```

下面是集合和列表的图示:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Implementation of List and Set in Java
import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // List declaration
        List<Integer> l = new ArrayList<>();
        l.add(5);
        l.add(6);
        l.add(3);
        l.add(5);
        l.add(4);

        // Set declaration
        Set<Integer> s = new HashSet<>();
        s.add(5);
        s.add(6);
        s.add(3);
        s.add(5);
        s.add(4);

        // printing list
        System.out.println("List = " + l);
        // printing Set
        System.out.println("Set = " + s);
    }
}
```

**Output**

```java
List = [5, 6, 3, 5, 4]
Set = [3, 4, 5, 6]
```

**列表和集合的区别:**

<figure class="table">

| 目录 | 一组 |
| --- | --- |
| 1.列表是有序的序列。 | 1.集合是一个无序的序列。 |
| 2.列表允许重复元素 | 2.集合不允许重复元素。 |
| 3.可以通过位置访问元素。 | 3.不允许对元素进行位置访问。 |
| 4.可以存储多个空元素。 | 4.Null 元素只能存储一次。 |
| 5.列表实现有数组列表、链表、向量、栈 | 5.集合实现有 HashSet、LinkedHashSet。 |

</figure>