# 实现链接哈希映射应用编程接口的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-linkedhashmap-api/](https://www.geeksforgeeks.org/java-program-to-implement-linkedhashmap-api/)

[**链接的哈希表**](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 就像 [**哈希表**](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) 一样，有一个额外的功能，即维护插入其中的元素的顺序。HashMap 提供了快速插入、搜索和删除的优势，但是它从来没有维护过 LinkedHashMap 提供的插入的轨迹和顺序，在那里元素可以按照它们的插入顺序被访问。

为了实现 LinkedHashMap API，我们首先创建一个类“LinkedHashMapImplmentation”，并在这个类中创建 LinkedHashMap 的所有方法。

**链接哈希映射应用编程接口的实现:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program demonstrate LinkedHashMap API

import java.util.Collection;
import java.util.HashMap;
import java.util.Iterator;
import java.util.LinkedHashMap;
import java.util.Map;
import java.util.Map.Entry;
import java.util.Set;

class LinkedHashMapImplementation<K, V> {
    private LinkedHashMap<K, V> map;

    // Constructor creates a new LinkedHashMap
    public LinkedHashMapImplementation()
    {
        map = new LinkedHashMap<K, V>();
    }

    // Constructor creates a new empty linkedhash map
    // according to the given map
    public LinkedHashMapImplementation(
        Map<? extends K, ? extends V> map1)
    {
        map = new LinkedHashMap<K, V>(map1);
    }

    // Delete all the key-value pair
    public void clear() { map.clear(); }

    // Returns a shallow copy of the LinkedHashMap instance
    public Object clone() { return map.clone(); }

    // Returns true if the map contains the specified key
    public boolean containsKey(Object key)
    {
        return map.containsKey(key);
    }

    // Returns true if map contains specified value
    public boolean containsValue(Object val)
    {
        return map.containsValue(val);
    }

    // Returns a Set view of the mappings
    public Set<Map.Entry<K, V> > entrySet()
    {
        return map.entrySet();
    }

    // Returns the value to which the specified key is
    // mapped, returns null if map does not contains given
    // key
    public V get(Object key) { return map.get(key); }

    // Returns a Set view of the keys
    public Set<K> keySet() { return map.keySet(); }

    // Associates the specified value with the specified key
    // in the map
    public V put(K key, V val) { return map.put(key, val); }

    // Copies all of the mappings from the specified map to
    // the map
    public void putAll(Map<? extends K, ? extends V> map1)
    {
        map.putAll(map1);
    }

    // Removes the mapping for the key from the
    // LinkedHashMap if present
    public V remove(Object key) { return map.remove(key); }

    // Returns the size of the map
    public int size() { return map.size(); }

    // Returns a Collection view of the values
    public Collection<V> values() { return map.values(); }
}

public class GFG {
    public static void main(String[] arg)
    {

        LinkedHashMapImplementation<String, Integer> student
            = new LinkedHashMapImplementation<>();

        // Add elements to the LinkedHashMap
        student.put("Anuj", 500);
        student.put("Ashok", 460);
        student.put("Aakansha", 495);

        // Print the size of the LinkedHashMap
        System.out.println("Size of the LinkedHashMap: "
                           + student.size());
        System.out.println();

        System.out.println(
            "The key value pairs of LinkedHashMap:");

        // Print the key value pairs of LinkedHashMap
        for (Map.Entry<String, Integer> entry :
             student.entrySet()) {
            System.out.println(entry.getKey() + " : "
                               + entry.getValue());
        }

        System.out.println();

        // Print LinkedHashMap contains key Aakansha or not
        System.out.println(
            "LinkedHashMap contains Aakansha: "
            + student.containsKey("Aakansha"));
        System.out.println();

        // Print LinkedHashMap contains value 450 or not
        System.out.println("LinkedHashMap contains 450: "
                           + student.containsValue(450));
        System.out.println();

        // Deletes all the entry
        student.clear();

        System.out.println("Size of the LinkedHashMap: "
                           + student.size());
    }
}
```

**Output**

```
Size of the LinkedHashMap: 3

The key value pairs of LinkedHashMap:
Anuj : 500
Ashok : 460
Aakansha : 495

LinkedHashMap contains Aakansha: true

LinkedHashMap contains 450: false

Size of the LinkedHashMap: 0
```