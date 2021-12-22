# 如何在 Java 中将集合中的选定项添加到 ArrayList 中？

> 原文:[https://www . geesforgeks . org/如何将精选项目从集合添加到 java 中的数组列表/](https://www.geeksforgeeks.org/how-to-add-selected-items-from-a-collection-to-an-arraylist-in-java/)

给定一个具有一些值的集合，任务是将这个集合的选定项添加到 Java 中的数组列表中。

**示例:**

> **输入:**集合= [1，2，3]，条件=(项！= 2)
> **输出:**数组列表= [1，3]
> 
> **输入:**收藏=【GFG，极客，极客 ForGeeks】，条件=(物品！= GFG)
> **输出:**数组列表=[极客，极客 ForGeeks]

**进场:**

*   获取要将其选定项添加到数组列表中的集合
*   创建数组列表
*   使用[流](https://www.geeksforgeeks.org/stream-in-java/)将所选的集合项目添加到该数组列表中
*   使用 [stream()方法](https://www.geeksforgeeks.org/stream-in-java/)生成集合中所有项目的流
*   使用[过滤器()方法](https://www.geeksforgeeks.org/stream-filter-java-examples/)从流中选择所需项目
*   使用 [forEachOrdered()方法](https://www.geeksforgeeks.org/stream-foreachordered-method-java-examples/)将流中的选定项目收集为数组列表
*   已创建带有选定集合项的数组列表。

下面是上述方法的实现:

```java
// Java program to add selected items
// from a collection to an ArrayList

import java.io.*;
import java.util.*;
import java.util.stream.*;

class GFG {

    // Function to add selected items
    // from a collection to an ArrayList
    public static <T> ArrayList<T>
    createArrayList(List<T> collection, T N)
    {

        // Create an ArrayList
        ArrayList<T> list = new ArrayList<T>();

        // Add selected items of Collection
        // into this ArrayList
        // Here select items if
        // they are not equal to N
        collection.stream()
            .filter(item -> !item.equals(N))
            .forEachOrdered(list::add);

        return list;
    }

    // Driver code
    public static void main(String[] args)
    {

        List<Integer> collection1
            = Arrays.asList(1, 2, 3);
        System.out.println(
            "ArrayList with selected "
            + "elements of collection "
            + collection1 + ": "
            + createArrayList(collection1, 2));

        List<String> collection2
            = Arrays.asList("GFG",
                            "Geeks",
                            "GeeksForGeeks");
        System.out.println(
            "ArrayList with selected "
            + "elements of collection "
            + collection2 + ": "
            + createArrayList(collection2, "GFG"));
    }
}
```

**Output:**

> 包含精选集合元素的数组列表[1，2，3]: [1，3]
> 包含精选集合元素的数组列表[GFG，极客，极客暴客]: [极客，极客暴客]