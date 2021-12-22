# 如何在 Java 中逆序迭代 LinkedHashMap？

> 原文:[https://www . geesforgeks . org/how-iterate-link edhashmap-in-reverse-in-Java/](https://www.geeksforgeeks.org/how-to-iterate-linkedhashmap-in-reverse-order-in-java/)

[链接哈希表](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/)用于维护插入其中的元素的顺序。它提供了可以按插入顺序访问元素的位置。LinkedHashMap 包含基于键的值。实现了[地图](https://www.geeksforgeeks.org/map-interface-java-examples/)界面，扩展了 [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) 类。它只包含唯一的元素或映射。

**linked hashmap 的语法**

```
public class LinkedHashMap<K,​V> extends HashMap<K,​V> implements Map<K,​V>
```

其中 **K** 为关键， **V** 为数值。

我们可以将键和值作为自己的数据类型，如字符串、浮点、整数等。我们可以通过首先反转元素来反转链接哈希映射中的元素。反转后，我们可以迭代。

**方法 1:(使用反向()方法)**

此方法用于反转 LinkedHashMap 中的元素或映射顺序。

**语法:**

```
public static void reverse(List myList)
```

**参数:** myList 是提供给[collections . reverse(my List)](https://www.geeksforgeeks.org/collections-reverse-java-examples/)方法的列表。

**返回:**它不返回任何东西，但在内部修改列表。

**异常:**如果指定的列表或其列表迭代器不支持设置操作，则抛出**不支持操作异常**。

**步骤:**

*   导入必要的包
*   用键和值创建一个链接哈希表
*   反向链接哈希表
*   迭代它。

**例 1:**

学生详细信息显示升序和降序，整数作为键，值作为字符串。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to iterate 
// LinkedHashMap in reverse order

import java.util.ArrayList;
import java.util.Collections;
import java.util.Iterator;
import java.util.LinkedHashMap;
import java.util.List;
import java.util.Set;

public class Main {

    public static void main(String[] args)
    {
        System.out.println("Student Details:");

        // creating HashMap object of type <String, String>
        LinkedHashMap<Integer, String> lhm
            = new LinkedHashMap<Integer, String>();

        // adding key-value pairs to HashMap object
        lhm.put(1, "Sravan Kumar");
        lhm.put(2, "Ishitha");
        lhm.put(3, "Harsha");
        lhm.put(4, "Vamsi");
        lhm.put(5, "Jyothika");

        // Insertion Order iterating
        System.out.println(
            "Insertion Order of LinkedHashMap:"
            + " iterating \n");

        // getting keySet() into Set
        Set<Integer> set = lhm.keySet();

        // get Iterator from key set
        Iterator<Integer> itr = set.iterator();

        // iterating as per Insertion Order
        while (itr.hasNext()) {
            Integer key = itr.next();
            System.out.println("Key : " + key + "\t\t"
                               + "Value : " + lhm.get(key));
        }

        // Reverse of Insertion Order iterating
        System.out.println("\n\nReverse of Insertion Order:"
                           + " iterating \n");

        // convert to ArrayList of key set
        List<Integer> alKeys
            = new ArrayList<Integer>(lhm.keySet());

        // reverse order of keys
        Collections.reverse(alKeys);

        // iterate LHM using reverse order of keys
        for (Integer strKey : alKeys) {
            System.out.println("Key : " + strKey + "\t\t"
                               + "Value : "
                               + lhm.get(strKey));
        }
    }
}
```

**Output**

```
Student Details:
Insertion Order of LinkedHashMap: iterating 

Key : 1        Value : Sravan Kumar
Key : 2        Value : Ishitha
Key : 3        Value : Harsha
Key : 4        Value : Vamsi
Key : 5        Value : Jyothika

Reverse of Insertion Order: iterating 

Key : 5        Value : Jyothika
Key : 4        Value : Vamsi
Key : 3        Value : Harsha
Key : 2        Value : Ishitha
Key : 1        Value : Sravan Kumar
```

**示例 2:** 键和值都是字符串类型。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to iterate 
// LinkedHashMap in reverse order

import java.util.ArrayList;
import java.util.Collections;
import java.util.Iterator;
import java.util.LinkedHashMap;
import java.util.List;
import java.util.Set;

public class Main {

    public static void main(String[] args)
    {

        // creating HashMap object of type <String, String>
        LinkedHashMap<String, String> lhm
            = new LinkedHashMap<String, String>();

        System.out.println("Staff DataBase");

        // adding key-value pairs to HashMap object
        lhm.put("CSE", "Subba Rao");
        lhm.put("IT", "Maruti");
        lhm.put("Civil", "Sundari Devi");

        // Insertion Order iterating
        System.out.println(
            "Insertion Order of LinkedHashMap:"
            + " iterating \n");

        // getting keySet() into Set
        Set<String> set = lhm.keySet();

        // get Iterator from key set
        Iterator<String> itr = set.iterator();

        // iterating as per Insertion Order
        while (itr.hasNext()) {
            String key = itr.next();
            System.out.println("Key : " + key + "\t\t"
                               + "Value : " + lhm.get(key));
        }

        // Reverse of Insertion Order iterating
        System.out.println("\n\nReverse of Insertion Order:"
                           + " iterating \n");

        // convert to ArrayList of key set
        List<String> alKeys
            = new ArrayList<String>(lhm.keySet());

        // reverse order of keys
        Collections.reverse(alKeys);

        // iterate LHM using reverse order of keys
        for (String strKey : alKeys) {
            System.out.println("Key : " + strKey + "\t\t"
                               + "Value : "
                               + lhm.get(strKey));
        }
    }
}
```

**Output**

```
Staff DataBase
Insertion Order of LinkedHashMap: iterating 

Key : CSE        Value : Subba Rao
Key : IT        Value : Maruti
Key : Civil        Value : Sundari Devi

Reverse of Insertion Order: iterating 

Key : Civil        Value : Sundari Devi
Key : IT        Value : Maruti
Key : CSE        Value : Subba Rao
```

**方法 2:(使用**T2 列表迭代器**方法)**

**语法:**

```
ListIterator listIterator(int index)
```

**参数:**这个方法只有一个参数，即 index–从列表迭代器返回的第一个元素的索引(通过调用 next)。

**返回:**这个方法从列表中的指定位置开始，返回列表迭代器，遍历列表中的元素(按照正确的顺序)。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to iterate 
// LinkedHashMap in reverse order

import java.util.ArrayList;
import java.util.LinkedHashMap;
import java.util.List;
import java.util.ListIterator;
import java.util.Set;

public class LinkedHashMapIterateReverseExample {

    public static void main(String[] args)
    {

        // create an instance of linked hashmap
        LinkedHashMap<String, String> lhmap
            = new LinkedHashMap<String, String>();

        // Add mappings
        lhmap.put("one", "Geeks");
        lhmap.put("two", "For");
        lhmap.put("three", "Geeks");

        // get all keys from the LinkedHashMap
        Set<String> setKeys = lhmap.keySet();

        // convert set to list
        List<String> listKeys
            = new ArrayList<String>(setKeys);

        // get a ListIterator for the ArrayList and
        // position it at the end to iterate backwards
        ListIterator<String> iterator
            = listKeys.listIterator(listKeys.size());

        // Iterate in reverse order using the hasPrevious
        // and previous methods
        while (iterator.hasPrevious()) {

            String key = iterator.previous();

            // get value mapped to the key
            System.out.println(key + " " + lhmap.get(key));
        }
    }
}
```

**Output**

```
three Geeks
two For
one Geeks
```

**方法 3:(使用**T2T4 法)

**语法:**

```
public Iterator descendingIterator()
```

**返回值:**这个方法返回一个**迭代器**在这个链表中的元素上以相反的顺序。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to iterate 
// LinkedHashMap in reverse order

import java.util.Iterator;
import java.util.LinkedHashMap;
import java.util.LinkedList;
import java.util.Set;

public class LinkedHashMapIterateReverseExample {

    public static void main(String[] args)
    {

        // create an instance of linked hashmap
        LinkedHashMap<String, String> lhmap
            = new LinkedHashMap<String, String>();

        // Add mappings
        lhmap.put("one", "Geeks");
        lhmap.put("two", "For");
        lhmap.put("three", "Geeks");

        // get all keys from the LinkedHashMap
        Set<String> setKeys = lhmap.keySet();

        // convert set to LinkedList
        LinkedList<String> listKeys
            = new LinkedList<String>(setKeys);

        // get descending iterator
        Iterator<String> iterator
            = listKeys.descendingIterator();

        // iterate the keys and get the values from the
        // map
        while (iterator.hasNext()) {

            String key = iterator.next();

            // get the value
            System.out.println(key + " " + lhmap.get(key));
        }
    }
}
```

**Output**

```
three Geeks
two For
one Geeks
```