# 实现 ConcurrentHashMap API 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-concurrenthashmap-api/](https://www.geeksforgeeks.org/java-program-to-implement-concurrenthashmap-api/)

[**【ConcurrentHashMap】**](https://www.geeksforgeeks.org/concurrenthashmap-in-java/)类遵循与 HashTable 相同的功能规范，包含了 HashTable 中每个方法对应的所有版本的方法。哈希表支持检索的完全并发和更新的可调并发。ConcurrentHashMap 的所有操作都是线程安全的，但是检索操作不需要锁定，即它不支持以阻止所有访问的方式锁定整个表。这个应用编程接口对于程序中的哈希表是完全可互操作的。它存在于[**Java . util . concurrent package**](https://www.geeksforgeeks.org/java-util-concurrent-package/)**中。**

ConcurrentHashMap 扩展了抽象映射<k>和对象类。此应用编程接口不允许将空值用作键或值，并且它是 Java 集合框架的成员。</k>

**类型参数:**

*   k–地图维护的按键类型
*   v–映射到它的值的类型。

**所有实现的接口:**

```java
Serializable, ConcurrentMap<K,V>, Map<K,V>
```

**语法:**

```java
public class ConcurrentHashMap<K,V>
extends AbstractMap<K,V>
implements ConcurrentMap<K,V>, Serializable
```

**施工人员:**

*   **ConcurrentHashMap()–**创建一个初始容量为 16、负载系数为 0.75、并发级别为 16 的空映射。
*   **ConcurrentHashMap(int initial capacity)–**使用给定的初始容量以及负载系数和并发级别的默认值创建一个空映射。
*   **ConcurrentHashMap(int initial capacity，float load factor)–**使用给定的初始容量和给定的负载系数以及默认的 concurrencyLevel 创建一个空映射。
*   **ConcurrentHashMap(int initial capacity，float loadFactor，int concurrencyLevel)–**用给定的初始容量、加载因子和 concurrency level 创建一个空映射。
*   **ConcurrentHashMap(地图<？延伸 K，？扩展 V>m)–**使用地图中给出的相同映射创建新地图。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Implement ConcurrentHashMap API

import java.util.Collection;
import java.util.Enumeration;
import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;
import java.util.Map.Entry;
import java.util.Set;
import java.util.concurrent.ConcurrentHashMap;

public class ConcurrentMap<K, V> {
    private ConcurrentHashMap<K, V> hm;

    // creates an empty ConcurrentHashMap with initial
    // capacity 16 and load factor 0.75
    public ConcurrentMap()
    {
        hm = new ConcurrentHashMap<K, V>();
    }

    // creates an empty ConcurrentHashMap with given initial
    // capacity and load factor 0.75
    public ConcurrentMap(int incap)
    {
        hm = new ConcurrentHashMap<K, V>(incap);
    }

    // creates an empty ConcurrentHashMap with given initial
    // capacity and load factor
    public ConcurrentMap(int incap, float lf)
    {
        hm = new ConcurrentHashMap<K, V>(incap, lf);
    }

    // creates an empty ConcurrentHashMap with given initial
    // capacity, load factor and concurrency level
    public ConcurrentMap(int incap, float lf,
                         int concurrLevel)
    {
        hm = new ConcurrentHashMap<K, V>(incap, lf,
                                         concurrLevel);
    }

    // Creates an hashMap with the same values as the given
    // hashMap
    public ConcurrentMap(Map<? extends K, ? extends V> m)
    {
        hm = new ConcurrentHashMap<K, V>(m);
    }

    // Removes all the keys and values from the Map
    public void clear() { hm.clear(); }

    // Return true if the Map contains the given Key
    public boolean containsKey(Object k)
    {
        return hm.containsKey(k);
    }

    // Return true if the map contains keys that maps to the
    // given value
    public boolean containsValue(Object v)
    {
        return hm.containsValue(v);
    }

    // Returns a set view of the key-value pairs of the map
    public Set<Map.Entry<K, V> > entrySet()
    {
        return hm.entrySet();
    }

    // Return the value to which the given key is mapped
    public V get(Object k) { return hm.get(k); }

    // Return true if the map does not contains any
    // key-value pairs
    public boolean isEmpty() { return hm.isEmpty(); }

    // Returns a set view of the key-value pairs of the map
    public Set<K> keySet() { return hm.keySet(); }

    // Maps the given value to the given key in the map
    public V put(K k, V v) { return hm.put(k, v); }

    // Copies all the key-value pairs from one map to
    // another
    public void putAll(Map<? extends K, ? extends V> mp)
    {
        hm.putAll(mp);
    }

    // Removes the mapping of the given key from its value
    public V remove(Object k) { return hm.remove(k); }

    // Returns the size of the map
    public int size() { return hm.size(); }

    // Returns the collection view of the values of the map
    public Collection<V> values() { return hm.values(); }

    // Returns an enumeration of the given values of the map
    public Enumeration<V> elements()
    {
        return hm.elements();
    }

    // If the given key is not associated with the given
    // value then associate it.
    public V putIfAbsent(K k, V v)
    {
        return hm.putIfAbsent(k, v);
    }

    // Replaces the value for a key only if it is currently
    // mapped to some value.
    public V replace(K key, V value)
    {
        return hm.replace(key, value);
    }

    // Replaces the oldValue for a key only if it is
    // currently mapped to a given value. *
    public boolean replace(K key, V oValue, V nValue)
    {
        return hm.replace(key, oValue, nValue);
    }

    public static void main(String[] arg)
    {
        // Creating an object of the class
        ConcurrentMap<Integer, String> hm
            = new ConcurrentMap<Integer, String>();

        hm.put(1, "Amit");
        hm.put(2, "Ankush");
        hm.put(3, "Akshat");
        hm.put(4, "Tarun");

        // Creating another Map
        Map<Integer, String> hm2
            = new HashMap<Integer, String>();
        hm.putAll(hm2);

        System.out.println(
            "The Keys of the ConcurrentHashMap is ");

        Set<Integer> k = hm.keySet();
        Iterator<Integer> i = k.iterator();

        while (i.hasNext()) {
            System.out.print(i.next() + " ");
        }
        System.out.println();

        System.out.println(
            "The values of the ConcurrentHashMap is ");

        Collection<String> values = hm.values();
        Iterator<String> s = values.iterator();

        while (s.hasNext()) {
            System.out.print(s.next() + " ");
        }
        System.out.println();

        System.out.println(
            "The entry set of the ConcurrentHashMap is ");

        Iterator<Entry<Integer, String> > er;
        Set<Entry<Integer, String> > ent = hm.entrySet();

        er = ent.iterator();

        while (er.hasNext()) {
            System.out.println(er.next() + " ");
        }

        System.out.println(
            "The ConcurrentHashMap contains Key 3 :"
            + hm.containsKey(3));

        System.out.println(
            "The ConcurrentHashMap contains Tarun:"
            + hm.containsValue("Tarun"));

        System.out.println(
            "Put the key 10 with value Shikha  if not asscociated : "
            + hm.putIfAbsent(10, "Shikha"));

        System.out.println(
            "Replace key 3 oldvalue of Akshat and newvalue Pari :"
            + hm.replace(3, "Akshat", "Pari"));

        System.out.println(
            "The Size of the ConcurrentHashMap is "
            + hm.size());

        // Clearing the Concurrent map
        hm.clear();

        if (hm.isEmpty())
            System.out.println(
                "The ConcurrentHashMap is empty");
        else
            System.out.println(
                "The ConcurrentHashMap is not empty");
    }
}
```

**Output**

```java
The Keys of the ConcurrentHashMap is 
1 2 3 4 
The values of the ConcurrentHashMap is 
Amit Ankush Akshat Tarun 
The entry set of the ConcurrentHashMap is 
1=Amit 
2=Ankush 
3=Akshat 
4=Tarun 
The ConcurrentHashMap contains Key 3 :true
The ConcurrentHashMap contains Tarun:true
Put the key 10 with value Shikha  if not asscociated : null
Replace key 3 oldvalue of Akshat and newvalue Pari :true
The Size of the ConcurrentHashMap is 5
The ConcurrentHashMap is empty
```