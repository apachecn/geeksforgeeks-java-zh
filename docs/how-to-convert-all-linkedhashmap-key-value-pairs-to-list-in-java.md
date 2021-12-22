# 如何在 Java 中将所有 LinkedHashMap 键值对转换为 List？

> 原文:[https://www . geesforgeks . org/如何将 all-linked hashmap-key-value-pairs 转换为 java 中的列表/](https://www.geeksforgeeks.org/how-to-convert-all-linkedhashmap-key-value-pairs-to-list-in-java/)

**链接的哈希表** 就像 [哈希表](https://www.geeksforgeeks.org/java-util-hashmap-in-java/) 一样，有一个额外的功能，即维护插入其中的元素的顺序。HashMap 提供了快速插入、搜索和删除的优势，但是它从来没有维护过 LinkedHashMap 提供的插入的轨迹和顺序，在那里元素可以按照它们的插入顺序被访问。

我们必须将所有 LinkedHashMap 键值对转换为 list，因此我们有一个 LinkedHashMap 对象，它包含一些键值对，我们必须使用 **keySet()** 和 **values()** 方法将其转换为 list。

**keySet():** 该方法用于获取其被调用的 LinkedHashMap 对象的密钥。

**values():** 该方法用于获取其被调用的 LinkedHashMap 对象的值。

**进场:**

*   创建一个包含一些键和值对的 LinkedHashMap。
*   创建一个包含 LinkedHashMap 对象的键的列表 1。
*   创建一个包含 LinkedHashMap 对象值的列表 2。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Convert all LinkedHashMap
// Key-Value pairs to List

import java.util.ArrayList;
import java.util.LinkedHashMap;
import java.util.List;

public class Sias {

    public static void main(String[] args)
    {

        // create LinkedHashMap
        LinkedHashMap<Integer, String> lhmap
            = new LinkedHashMap<Integer, String>();

        // add elements in LinkedHashMap
        lhmap.put(1, "One");
        lhmap.put(2, "Two");
        lhmap.put(3, "Three");
        lhmap.put(4, "Four");
        lhmap.put(5, "Five");

        // Create List 1 that store keys
        List<Integer> list1
            = new ArrayList<Integer>(lhmap.keySet());

        // display List 1
        System.out.println("List 1 - " + list1);

        // Create List 2 that store values
        List<String> list2
            = new ArrayList<String>(lhmap.values());

        // display List 1
        System.out.println("List 2 - " + list2);
    }
}
```

**Output**

```
List 1 - [1, 2, 3, 4, 5]
List 2 - [One, Two, Three, Four, Five]
```