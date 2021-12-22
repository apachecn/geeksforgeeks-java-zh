# 计算列表元素在 Java 中的出现次数

> 原文:[https://www . geesforgeks . org/count-occurs-elements-list-Java/](https://www.geeksforgeeks.org/count-occurrences-elements-list-java/)

假设我们在[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)中有一个元素，我们可以通过多种方式计算元素出现的次数。

**[HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)**

这种数据结构使用散列函数将类似的值(称为键)映射到它们的关联值。可以使用键检索映射值，因为它包含键-值对。

```java
// Java program to count frequencies of elements
// using HashMap.
import java.util.HashMap;
import java.util.Map;
import java.util.Map.Entry;
import java.util.*;

class GFG {
    public static void countFrequencies(ArrayList<String> list)
    {
        // hashmap to store the frequency of element
        Map<String, Integer> hm = new HashMap<String, Integer>();

        for (String i : list) {
            Integer j = hm.get(i);
            hm.put(i, (j == null) ? 1 : j + 1);
        }

        // displaying the occurrence of elements in the arraylist
        for (Map.Entry<String, Integer> val : hm.entrySet()) {
            System.out.println("Element " + val.getKey() + " "
                               + "occurs"
                               + ": " + val.getValue() + " times");
        }
    }

    public static void main(String[] args)
    {
        ArrayList<String> list = new ArrayList<String>();
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");
        countFrequencies(list);
    }
}
```

**Output:**

```java
Element Geeks occurs: 2 times
Element for occurs: 1 times

```

**[HashSet](https://www.geeksforgeeks.org/hashset-in-java/)**

该数据结构不允许重复元素，因为它实现了[设置接口](https://www.geeksforgeeks.org/set-in-java/)。根据对象的哈希代码插入对象。

为了计算数组列表元素的出现次数，我们创建了一个哈希集，并添加了数组列表的所有元素。我们用 [Collections.frequency(集合 c，对象 o)](https://www.geeksforgeeks.org/java-util-collections-frequency-java/) 来统计集合 c 中对象 o 的出现次数

下面的程序说明了 HashSet 的工作原理:

**查找单词出现的程序**

```java
// Java program to count frequencies of elements
// using HashSet and Collections.frequency.
import java.util.HashMap;
import java.util.Map;
import java.util.Map.Entry;
import java.util.*;

class GFG {
    public static void countFrequencies(ArrayList<String> list)
    {

        // hash set is created and elements of
        // arraylist are insertd into it
        Set<String> st = new HashSet<String>(list);
        for (String s : st)
            System.out.println(s + ": " + Collections.frequency(list, s));
    }

    public static void main(String[] args)
    {
        ArrayList<String> list = new ArrayList<String>();
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");
        countFrequencies(list);
    }
}
```

**Output:**

```java
Geeks: 2
for: 1

```

**[TreeMap](https://www.geeksforgeeks.org/differences-treemap-hashmap-linkedhashmap-java/)**

这种数据结构按照排序顺序存储唯一的元素。它在后台使用[红黑树](https://www.geeksforgeeks.org/red-black-tree-set-1-introduction-2/)的概念来防止重复。

```java
// Java program to count frequencies of elements
// using HashMap.
import java.util.HashMap;
import java.util.Map;
import java.util.Map.Entry;
import java.util.*;

class GFG {
    public static void countFrequencies(ArrayList<String> list)
    {

        TreeMap<String, Integer> tmap = new TreeMap<String, Integer>();
        for (String t : list) {
            Integer c = tmap.get(t);
            tmap.put(t, (c == null) ? 1 : c + 1);
        }

        for (Map.Entry m : tmap.entrySet())
            System.out.println("Frequency of " + m.getKey() + " is " + m.getValue());
    }

    public static void main(String[] args)
    {
        ArrayList<String> list = new ArrayList<String>();
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");
        countFrequencies(list);
    }
}
```

**Output:**

```java
Frequency of Geeks is 2
Frequency of for is 1

```

**要点:**

*   哈希映射实现映射接口，而树映射实现排序映射接口。
*   哈希映射使用哈希，而树映射使用红黑树。因此**基于 HashMap 的解决方案通常比基于 TreeMap 的解决方案**快得多。