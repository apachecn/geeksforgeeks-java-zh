# 如何在 Java 中按值对树形图进行排序？

> 原文:[https://www . geesforgeks . org/如何按 java 中的值对树图进行排序/](https://www.geeksforgeeks.org/how-to-sort-a-treemap-by-value-in-java/)

在 Java 语言中，[树形图](https://www.geeksforgeeks.org/treemap-in-java/)总是存储键-值对，这些键-值对在键的基础上按排序顺序排列。TreeMap 实现了[导航地图](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/)接口，扩展了[抽象地图](https://www.geeksforgeeks.org/abstractmap-in-java/)类。TreeMap 包含唯一的键。

**在 Java 中按值排序树形图**

*   树形图中的元素是根据关键字排序的。
*   所以，我们需要发展自己的逻辑，在价值的基础上进行排序。我们可以使用**比较器类**来实现

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Sort a TreeMap By Value

import java.util.*;
class GFG {

    public static <K, V extends Comparable<V> > Map<K, V>
    valueSort(final Map<K, V> map)
    {
        // Static Method with return type Map and
        // extending comparator class which compares values
        // associated with two keys
        Comparator<K> valueComparator = new Comparator<K>() {

                  // return comparison results of values of
                  // two keys
                  public int compare(K k1, K k2)
                  {
                      int comp = map.get(k1).compareTo(
                          map.get(k2));
                      if (comp == 0)
                          return 1;
                      else
                          return comp;
                  }

              };

        // SortedMap created using the comparator
        Map<K, V> sorted = new TreeMap<K, V>(valueComparator);

        sorted.putAll(map);

        return sorted;
    }

    public static void main(String[] args)
    {
        TreeMap<String, Integer> map = new TreeMap<String, Integer>();

        // Put elements to the map
        map.put("Anshu", 2);
        map.put("Rajiv", 4);
        map.put("Chhotu", 3);
        map.put("Golu", 5);
        map.put("Sita", 1);

        // Calling the method valueSort
        Map sortedMap = valueSort(map);

        // Get a set of the entries on the sorted map
        Set set = sortedMap.entrySet();

        // Get an iterator
        Iterator i = set.iterator();

        // Display elements
        while (i.hasNext()) {

            Map.Entry mp = (Map.Entry)i.next();
            System.out.print(mp.getKey() + ": ");
            System.out.println(mp.getValue());

        }
    }
}
```

**Output**

```
Sita: 1
Anshu: 2
Chhotu: 3
Rajiv: 4
Golu: 5
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Sort a TreeMap By Value

import java.util.*;

class GFG {
    // Method for sorting the TreeMap based on values
    public static <K, V extends Comparable<V> > Map<K, V>
    valueSort(final Map<K, V> map)
    {
        // Static Method with return type Map and
        // extending comparator class which compares values
        // associated with two keys
        Comparator<K> valueComparator = new Comparator<K>()
        {

            public int compare(K k1, K k2)
            {

                int comp = map.get(k1).compareTo(map.get(k2));

                if (comp == 0)
                     return 1;

                else
                     return comp;
            }
        };

        // SortedMap created using the comparator
        Map<K, V> sorted = new TreeMap<K, V>(valueComparator);

        sorted.putAll(map);

        return sorted;
    }

    public static void main(String[] args)

    {

        TreeMap<Integer, String> map
            = new TreeMap<Integer, String>();

        // Put elements to the map
        map.put(1, "Anshu");

        map.put(5, "Rajiv");

        map.put(3, "Chhotu");

        map.put(2, "Golu");

        map.put(4, "Sita");

        // Calling the method valueSort
        Map sortedMap = valueSort(map);

        // Get a set of the entries on the sorted map
        Set set = sortedMap.entrySet();

        // Get an iterator
        Iterator i = set.iterator();

        while (i.hasNext())
        {
            Map.Entry mp = (Map.Entry)i.next();

            System.out.print(mp.getKey() + ": ");

            System.out.println(mp.getValue());
        }
    }
}
```

**Output**

```
1: Anshu
3: Chhotu
2: Golu
5: Rajiv
4: Sita
```