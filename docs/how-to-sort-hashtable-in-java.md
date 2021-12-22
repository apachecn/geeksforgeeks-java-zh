# Java 中哈希表如何排序？

> 原文:[https://www . geesforgeks . org/how-sort-hashtable-in-Java/](https://www.geeksforgeeks.org/how-to-sort-hashtable-in-java/)

给定一个[哈希表](https://www.geeksforgeeks.org/hashtable-in-java/)，任务是对这个哈希表进行排序。哈希表是一种以键值格式存储数据的数据结构。存储的数据既没有排序顺序，也没有保持插入顺序。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;
import java.util.*;

public class SortHashtable {
    public static void main(String[] args)
    {

        // create a hashtable
        Hashtable<Integer, String> ht
            = new Hashtable<Integer, String>();

        // insert data into hashtable
        ht.put(2, "mango");
        ht.put(3, "orange");
        ht.put(1, "apple");

        Set<Integer> keys = ht.keySet();
        Iterator<Integer> itr = keys.iterator();

        // traverse the TreeMap using iterator
        while (itr.hasNext()) {
            Integer i = itr.next();
            System.out.println(i + " " + ht.get(i));
        }
    }
}
```

**Output**

```
3 orange
2 mango
1 apple

```

哈希表映射可以通过以下两种方式进行排序:

1.  **使用树形图**
2.  **使用链接哈希表**

**示例:**

> **输入:**哈希表:{2:“芒果”，1:“苹果”，3:“橘子”}
> 
> **产量:** 1 个苹果
> 
> 2 个芒果
> 
> 3 个橙色
> 
> **输入:**哈希表:{3:“三”，2:“第二”，1:“第一”}
> 
> **输出:** 1 第一
> 
> 2 秒
> 
> 3 第三

**方法 1:**

[树形图](https://www.geeksforgeeks.org/treemap-in-java/)按照排序顺序存储数据。我们可以使用树形图构造器，将哈希表对象转换成树形图对象。现在，生成的树形图对象是按排序顺序排列的。

**语法:**

```
TreeMap<K, V> tm = new TreeMap<K, V>(Map m);
```

**参数:** **m** 是我们程序中的哈希表。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;
import java.util.*;

public class SortHashtable {
    public static void main(String[] args)
    {

        // create a hashtable
        Hashtable<Integer, String> ht
            = new Hashtable<Integer, String>();

        // insert data into hashtable
        ht.put(2, "mango");
        ht.put(3, "orange");
        ht.put(1, "apple");

        // create a TreeMap
        TreeMap<Integer, String> tm
            = new TreeMap<Integer, String>(ht);

        // create a keyset
        Set<Integer> keys = tm.keySet();
        Iterator<Integer> itr = keys.iterator();

        // traverse the TreeMap using iterator
        while (itr.hasNext()) {
            Integer i = itr.next();
            System.out.println(i + " " + tm.get(i));
        }
    }
}
```

**Output**

```
1 apple
2 mango
3 orange

```

**方法 2:**

[LinkedHashMap](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 按照插入的顺序存储数据。当数据到来时，将它插入到 LinkedHashMap 中，该 Map 具有保持插入顺序的属性。

**语法:**

```
LinkedHashMap<K, V> lhm = new LinkedHashMap<K, V>();
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;
import java.util.*;

public class SortHashTable {
    public static void main(String[] args)
    {

        // create a LinkedHashMap
        LinkedHashMap<Integer, String> lhm
            = new LinkedHashMap<Integer, String>();

        // insert data into LinkeHashMap
        lhm.put(2, "mango");
        lhm.put(3, "orange");
        lhm.put(1, "apple");

        // prepare a keyset
        Set<Integer> keys = lhm.keySet();
        Iterator<Integer> itr = keys.iterator();

        // traverse the LinkedHashMap using iterator
        while (itr.hasNext()) {
            Integer i = itr.next();
            System.out.println(i + " " + lhm.get(i));
        }
    }
}
```

**Output**

```
2 mango
3 orange
1 apple

```