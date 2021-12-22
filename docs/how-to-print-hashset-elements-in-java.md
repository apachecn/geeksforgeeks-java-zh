# 如何用 Java 打印 HashSet 元素？

> 原文:[https://www . geesforgeks . org/how-print-hashset-elements-in-Java/](https://www.geeksforgeeks.org/how-to-print-hashset-elements-in-java/)

在 [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 中，不允许重复。如果我们试图插入重复项，那么我们不会得到任何编译时或运行时错误，add()方法只是返回 false。

**我们可以用 2 种方式打印 HashSet 元素:**

1.  使用迭代器()方法遍历集合元素并打印它。
2.  使用引用变量直接打印。

**方法 1:使用** [**迭代器**](https://www.geeksforgeeks.org/iterators-in-java/) **的光标。**

*   如果我们想从集合中一个接一个地获取对象，那么我们应该选择光标。
*   我们可以对任何集合对象应用迭代器概念，因此它是一个通用游标。
*   通过使用迭代器，我们可以执行读取和移除操作。
*   我们可以使用集合接口的迭代器方法创建一个迭代器对象。

> 公共迭代器 Iterator()；//集合接口的迭代器方法。

*   创建迭代器对象

> iterator itr = c . iterator()；//其中 c 是任何集合对象，如数组列表、哈希集等。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to print the elements
// of HashSet using iterator cursor

import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        HashSet<Integer> hs = new HashSet<Integer>();
        hs.add(5);
        hs.add(2);
        hs.add(3);
        hs.add(6);
        hs.add(null);

        // print HashSet elements one by one.
        // Inserton order in not preserved and it is based
        // on hash code of objects.

        // creates Iterator oblect.
        Iterator itr = hs.iterator();

        // check element is present or not. if not loop will
        // break.
        while (itr.hasNext()) {
            System.out.println(itr.next());
        }
    }
}
```

**Output**

```java
null
2
3
5
6
```

**方法二:**我们可以使用 HashSet 对象引用变量直接打印 HashSet 元素。它将打印完整的 HashSet 对象。

**注意:**如果我们不知道哈希码，那么就无法决定插入的顺序。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to directly print the
// elements of HashSet

import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // create HashSet object
        HashSet<String> hs = new HashSet<String>();

        // add element in HashSet object
        hs.add("B");
        hs.add("C");
        hs.add("D");
        hs.add("A");
        hs.add("Z");
        hs.add("null");
        hs.add("10");

        // print HashSet
        // we dont't know hash code,
        // so we don't know order
        // of insertion
        System.out.println(hs);
    }
}
```

**Output**

```java
[A, B, C, D, null, Z, 10]
```