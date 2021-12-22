# 用 Java 从其他地图创建哈希表

> 原文:[https://www . geesforgeks . org/creating-hashmap-from-other-map-in-Java/](https://www.geeksforgeeks.org/creating-hashmap-from-other-maps-in-java/)

[java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包中的 [**映射界面**](https://www.geeksforgeeks.org/map-interface-java-examples/) 表示键和值之间的映射。地图界面不是[采集界面](https://www.geeksforgeeks.org/collections-in-java-2/)的子类型。因此，它的行为与其他集合类型有点不同。地图包含唯一的键。

**Java 中的地图主要有三种类型**

1.  [哈希映射](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/#:~:text=HashMap%20is%20similar%20to%20the,you%20need%20to%20import%20java.)
2.  [LinkedHashMap](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/)
3.  [树图](https://www.geeksforgeeks.org/treemap-in-java/)

这些界面扩展了地图界面。

**将一张地图转换成另一张地图有多种方式:**

1.  使用迭代器/循环
2.  使用构造函数
3.  使用 putAll()方法

**方法 1:使用迭代器/a** **循环**

迭代映射的每个元素(在本例中是 LinkedHashMap)，并在新的 HashMap 中添加每个元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program for creating HashMap from Other Maps

import java.util.*;

public class to_hashmap {

    public static void main(String a[])
    {
        // create an instance of LinkedHashMap
        LinkedHashMap<String, String> lhm
               = new LinkedHashMap<String, String>();

        // Add mappings using put method
        lhm.put("Apurva", "Bhatt");
        lhm.put("James", "Bond");
        lhm.put("Scarlett ", "Johansson");

        // It prints the elements in same order
        // as they were inserted
        System.out.println(lhm);

        Map<String, String> gfg = new HashMap<String, String>();

        // Using entrySet() method create a set out of the same elements
        // contained in the hash map
        for (Map.Entry<String, String> entry : lhm.entrySet())
            gfg.put(entry.getKey(), entry.getValue());

        System.out.println(gfg);
    }
}
```

**Output**

```
{Apurva=Bhatt, James=Bond, Scarlett =Johansson}
{James=Bond, Apurva=Bhatt, Scarlett =Johansson}
```

**方法二:使用构造器**

将给定的映射(在本例中是树映射)传递给哈希映射构造器——它将自动负责将给定的映射转换为哈希映射。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program for creating HashMap from Other Maps
// using constructor

import java.util.*;

public class to_hashmap {

    public static void main(String a[])
    {
        // create an instance of TreeMap
        Map<String, String> tm = new TreeMap<String, String>();

        // Add mappings using put method
        tm.put("Apurva", "Bhatt");
        tm.put("James", "Bond");
        tm.put("Scarlett ", "Johansson");

        // It prints the elements in same order
        // as they were inserted
        System.out.println(tm);

        Map<String, String> gfg = new HashMap<String, String>(tm);

        System.out.println(gfg);
    }
}
```

**Output**

```
{Apurva=Bhatt, James=Bond, Scarlett =Johansson}
{Apurva=Bhatt, James=Bond, Scarlett =Johansson}
```

**方法三:使用** [**普塔尔()**](https://www.geeksforgeeks.org/hashmap-putall-method-in-java/#:~:text=putAll()%20is%20an%20inbuilt,from%20one%20map%20into%20another.&text=Parameters%3A%20The%20method%20takes%20one,we%20want%20to%20copy%20from.) **方法**

它类似于前面的方法，不是将给定的 Map 传递给 HashMap 构造函数，而是将其传递给 putAll()方法，它将自动将其转换为 HashMap。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program for creating HashMap from Other Maps
// using putAll() method

import java.util.*;

public class two_hashmap {

    public static void main(String a[])
    {
        // create an instance of TreeMap
        Map<String, String> tm = new TreeMap<String, String>();

        // Add mappings using put method
        tm.put("Apurva", "Bhatt");
        tm.put("James", "Bond");
        tm.put("Scarlett ", "Johansson");

        // It prints the elements in same order
        // as they were inserted
        System.out.println(tm);

        Map<String, String> gfg = new HashMap<String, String>();

        // using put all command
        gfg.putAll(tm);

        System.out.println(gfg);
    }
}
```

**Output**

```
{Apurva=Bhatt, James=Bond, Scarlett =Johansson}
{Apurva=Bhatt, James=Bond, Scarlett =Johansson}
```