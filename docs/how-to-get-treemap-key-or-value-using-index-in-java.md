# 如何在 Java 中使用 Index 获取 TreeMap 键值？

> 原文:[https://www . geesforgeks . org/如何使用 java 中的索引获取树图键或值/](https://www.geeksforgeeks.org/how-to-get-treemap-key-or-value-using-index-in-java/)

Java 中的[树形图](https://www.geeksforgeeks.org/treemap-in-java/)是用来实现[**图**](https://www.geeksforgeeks.org/java-util-hashmap-in-java/) 接口和 [**导航图**](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/) 以及[**抽象图**](https://www.geeksforgeeks.org/abstractmap-in-java/) 类的。树形图根据其键的自然顺序进行排序。TreeMap 类是 Map 接口的红黑树实现，因此不公开任何我们可以使用其索引访问 TreeMap 键或值的方法。

**Java 中使用 index 获取 key 或 TreeMap 值有三种简单的方法，如下:**

1.  使用数组
2.  使用列表
3.  使用迭代

**方法 1:** 使用 [**阵**](https://www.geeksforgeeks.org/arraylist-in-java/)

我们可以通过使用数组，在 Java 中使用索引来获取树映射键或树映射值。该过程分为三个步骤:

1.  使用树图类的 [**entrySet()**](https://www.geeksforgeeks.org/hashmap-entryset-method-in-java/) 方法获取存储在树图对象中的所有条目的集合视图。
2.  使用 [**到**](https://www.geeksforgeeks.org/set-toarray-method-in-java-with-example/) 方法将条目集转换为数组。
3.  并借助[**【getKey()】**](https://www.geeksforgeeks.org/keystore-getkey-method-in-java-with-examples/)和 [**getValue()**](https://www.geeksforgeeks.org/java-tuples-getvalue-method/) 方法使用索引获取 TreeMap 键或 TreeMap 值

**语法:**

```
Set<Map.Entry<Integer, String>> entrySet = treeMap.entrySet();
```

> 地图！地图！entry<integer string="">[]entry yar ray = entry array . toaarray(新地图)。entry[entry set . size()]；</integer>

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to get TreeMap key or TreeMap value
// using index

// Importing all classes of
// java.util package
import java.util.*;

// Class
public class GFG {

    // MAin driver method
    public static void main(String[] args)
    {

        // Creating a New TreeMap
        TreeMap<Integer, String> treeMap
            = new TreeMap<Integer, String>();

        // Add elements to TreeMap
        // Custom inputs
        treeMap.put(1, "Welcome");
        treeMap.put(2, "geeks");
        treeMap.put(3, "on");
        treeMap.put(4, "geeksforgeeks");

        // Get entry set of the TreeMap using entrySet
        // method
        Set<Map.Entry<Integer, String> > entrySet
            = treeMap.entrySet();

        // Convert entrySet to Array using toArray method
        Map.Entry<Integer, String>[] entryArray
            = entrySet.toArray(
                new Map.Entry[entrySet.size()]);

        // For loop for iteration  and printing
        for (int i = 0; i < 4; i++)
        {
            // Get Key using index and print
            System.out.println("Key at " + i + ":"
                               + entryArray[i].getKey());

            // Get value using index and print
            System.out.println("Value at " + i + ":"
                               + entryArray[i].getValue());
        }

    }
}
```

**输出:**

```
1
Welcome
2
geeks
3
on
4
geeksforgeeks
```

**方法二:**使用 [**列表**](https://www.geeksforgeeks.org/arraylist-in-java/)

我们可以通过使用列表而不是数组，在 Java 中使用索引来获取树映射键或树映射值。该过程分为三个步骤:

1.  使用 TreeMap 类的 entrySet()方法获取存储在 TreeMap 对象中的所有条目的集合视图。
2.  现在，使用 toArray()方法将条目集转换为数组。
3.  最后，在 get()，getKey()和 getValue()方法的帮助下，使用索引获取 TreeMap 键或 TreeMap 值。

**语法:**

```
Set<Map.Entry<Integer, String>> entrySet = treeMap.entrySet();
```

> 列表 <map.entry string="">> entryList =新数组列表<map.entry string="">>(entrySet)；</map.entry></map.entry>

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to get TreeMap key or TreeMap value
// using index

// Importing all classes of
// java.util package
import java.util.*;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating a TreeMap
        TreeMap<Integer, String> treeMap = new TreeMap<>();

        // Add elements to TreeMap
        // Custom inputs
        treeMap.put(1, "Welcome");
        treeMap.put(2, "geeks");
        treeMap.put(3, "on");
        treeMap.put(4, "geeksforgeeks");

        // Get entry set of the TreeMap
        // using entrySet method
        Set<Map.Entry<Integer, String> > entrySet
            = treeMap.entrySet();

        // Converting entrySet to ArrayList
        List<Map.Entry<Integer, String> > entryList
            = new ArrayList<>(entrySet);

        // For each loop for iteration
        for (int i = 0; i < 4; i++) {

            // Print Key and Values using index

            // Get Key using index
            System.out.println("Key at " + i + ":"
                               + entryList.get(i).getKey());

            // Get value using index
            System.out.println(
                "Value at " + i + ":"
                + entryList.get(i).getValue());
        }
    }
}
```

**Output**

```
Key at 0:1
Value at 0:Welcome
Key at 1:2
Value at 1:geeks
Key at 2:3
Value at 2:on
Key at 3:4
Value at 3:geeksforgeeks
```

**方法三:**利用[**迭代**](https://www.geeksforgeeks.org/iterate-map-java/)

我们可以通过一次迭代，在 Java 中使用索引来获取 TreeMap 键或 TreeMap 值。该过程分为两个步骤:

1.  使用 TreeMap 类的 [entrySet()](https://www.geeksforgeeks.org/treemap-entryset-method-in-java/) 方法获取存储在 TreeMap 对象中的所有条目的 Set 视图。
2.  在 entrySet 上迭代，在 getKey()和 getValue()方法的帮助下，使用索引获取树映射键或树映射值。

**语法:**

```
Set<Map.Entry<Integer, String>> entrySet = treeMap.entrySet();
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to get TreeMap key or TreeMap value using
// index

// Importing all classes of
// java.util package
import java.util.*;

// Class
public class GFG {

    // MAin driver method
    public static void main(String[] args)
    {
        // Creating a TreeMp
        TreeMap<Integer, String> treeMap = new TreeMap<>();

        // Add elements to TreeMap
        // Custom inputs
        treeMap.put(1, "Welcome");
        treeMap.put(2, "geeks");
        treeMap.put(3, "on");
        treeMap.put(4, "geeksforgeeks");

        // Get entry set of the TreeMap
        // using entrySet method
        Set<Map.Entry<Integer, String> > entrySet
            = treeMap.entrySet();

        int index = 0;

        // For-each loop for iteration
        for (Map.Entry<Integer, String> currentEntry :
             entrySet) {

            // Print Key and Values using index

            // Get Key using index
            System.out.println("Key at " + index + ":"
                               + currentEntry.getKey());

            // Get value using index
            System.out.println("Value at " + index + ":"
                               + currentEntry.getValue());
            index++;
        }
    }
}
```

**Output**

```
Key at 0:1
Value at 0:Welcome
Key at 1:2
Value at 1:geeks
Key at 2:3
Value at 2:on
Key at 3:4
Value at 3:geeksforgeeks
```