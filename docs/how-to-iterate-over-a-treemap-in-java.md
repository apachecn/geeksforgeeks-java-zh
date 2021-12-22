# 如何在 Java 中迭代一个 TreeMap？

> 原文:[https://www . geeksforgeeks . org/如何迭代 java 中的树图/](https://www.geeksforgeeks.org/how-to-iterate-over-a-treemap-in-java/)

给定一个[树形图](https://www.geeksforgeeks.org/treemap-in-java/)，任务是用 Java 迭代这个树形图。Java 中的 TreeMap 与[抽象类](https://www.geeksforgeeks.org/abstract-classes-in-java/)一起实现[地图界面](https://www.geeksforgeeks.org/map-interface-java-examples/)和[导航地图](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/)。我们不能直接使用迭代器迭代树图，因为树图不是集合。所以我们将不得不使用 [TreeMap.entrySet()方法](https://www.geeksforgeeks.org/treemap-entryset-method-in-java/)。该方法返回一个集合视图(设置<地图)。条目>)中包含的映射。因此，我们可以使用 Map.Entry 的 getKey()和 getValue()方法迭代键值对。这种方法是最常见的，如果您在循环中需要映射键和值，应该使用这种方法。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to iterate over a TreeMap

import java.util.Map;
import java.util.TreeMap;

class IterationDemo {
    public static void main(String[] arg)
    {
        Map<String, String> gfg
            = new TreeMap<String, String>();

        // enter name/url pair
        gfg.put("GFG", "geeksforgeeks.org");
        gfg.put("Practice", "practice.geeksforgeeks.org");
        gfg.put("Code", "code.geeksforgeeks.org");
        gfg.put("Quiz", "quiz.geeksforgeeks.org");

        // using for-each loop for
        // iteration over TreeMap.entrySet()
        for (Map.Entry<String, String>
                 entry : gfg.entrySet())
            System.out.println(
                "[" + entry.getKey()
                + ", " + entry.getValue() + "]");
    }
}
```

**Output:** 

```
[Code, code.geeksforgeeks.org]
[GFG, geeksforgeeks.org]
[Practice, practice.geeksforgeeks.org]
[Quiz, quiz.geeksforgeeks.org]
```

现在让我们来看看遍历 TreeMap 对象中的条目。为了实现，我们正在考虑非常简单的映射元素关联性，其中我们有三个元素说它们是“极客”、“for”、“极客”，并且是整数类型的键值“1”、“2”和“3”。因此，只有这样我们才能得到我们需要制作一个树形图类的对象。

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Iterate Over Entries in a TreeMap

import java.util.*;

// Importing required
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating a TreeMap class object
        // Objects are of key-value pairs (integer and
        // string type)
        TreeMap<Integer, String> tm
            = new TreeMap<Integer, String>();

        // Customly adding elements
        tm.put(1, "Geeks");
        tm.put(2, "For");
        tm.put(3, "Geeks");

        //  Get all entries using the entrySet() method
        Set<Map.Entry<Integer, String> > entries
            = tm.entrySet();

        // Way 1
        // Using for loops
        for (Map.Entry<Integer, String> entry : entries) {
            System.out.println(entry.getKey() + "->"
                               + entry.getValue());
        }

        // New line to differenciate differences in output
        // between for loop and for each loop
        System.out.println();

        // Way 2 - getting code shorter and simpler
        // For each loops

        entries.forEach(entry -> {
            System.out.println(entry.getKey() + "->"
                               + entry.getValue());
        });

        // New line to differenciate differences in output
        // between for each loop and iterator traversal
        System.out.println();

        // Way 3 - New way to
        // Getting an iterator
        Iterator<Map.Entry<Integer, String> > iterator
            = entries.iterator();

        // Additional step here
        // To Initialize object holding for
        // key-value pairs to null
        Map.Entry<Integer, String> entry = null;

        // Holds true till there is no element remaining in
        // the object using hasNExt() method
        while (iterator.hasNext()) {

            // Moving onto next pairs using next() method
            entry = iterator.next();

            // Printing the key-value pairs
            // using getKet() and getValue() methods
            System.out.println(entry.getKey() + "->"
                               + entry.getValue());
        }
    }
}
```

**Output**

```
1->Geeks
2->For
3->Geeks

1->Geeks
2->For
3->Geeks

1->Geeks
2->For
3->Geeks
```