# 实现 HashMap API 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-hashmap-api/](https://www.geeksforgeeks.org/java-program-to-implement-hashmap-api/)

[**HashMap < K，V >**](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) 是 Java 1.2 以来 Java 的集合的一部分。这个类可以在[**java.util 包**](https://www.geeksforgeeks.org/java-util-package-java/) 中找到。它提供了 Java 的 Map 接口的基本实现。它将数据存储在(键、值)对中，您可以通过另一种类型的索引(例如整数)来访问它们。一个对象用作另一个对象(值)的键(索引)。如果您尝试插入重复的键，它将替换相应键的元素。

HashMap 类似于 [HashTable](https://www.geeksforgeeks.org/hashtable-in-java/) ，但不同步。它也允许存储空键，但是应该只有一个空键对象，并且可以有任意数量的空值。这个类不保证地图的顺序。要使用这个类及其方法，需要导入 java.util.HashMap 包或其超类。

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to implement HashMap API

import java.util.Collection;
import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;
import java.util.Map.Entry;
import java.util.Set;

public class HashMapImplementation<K, V> {
    private HashMap<K, V> hashMap;

    // Constructs an empty HashMap with the default initial
    // capacity (16) and the default load factor (0.75).

    public HashMapImplementation()
    {
        hashMap = new HashMap<K, V>();
    }

    // Constructs an empty HashMap with the specified
    // initial capacity and the default load factor (0.75).

    public HashMapImplementation(int initialCapacity)
    {
        hashMap = new HashMap<K, V>(initialCapacity);
    }

    // Constructs an empty HashMap with the specified
    // initial capacity and load factor.

    public HashMapImplementation(int initialCapacity,
                                 float loadFactor)
    {
        hashMap = new HashMap<K, V>(initialCapacity,
                                    loadFactor);
    }

    // Constructs a new HashMap with the same mappings as
    // the specified Map.
    public HashMapImplementation(Map<? extends K, ? extends V> m)
    {
        hashMap = new HashMap<K, V>(m);
    }

    // Removes all of the mappings from this map.
    public void clear() { hashMap.clear(); }

    // Returns a shallow copy of this HashMap instance: the
    // keys and values
    // themselves are not cloned.

    public Object clone() { return hashMap.clone(); }

    // return true if map contains given key
    public boolean containsKey(Object key)
    {
        return hashMap.containsKey(key);
    }

    // Returns true if this map maps one or more keys to the
    // specified value.
    public boolean containsValue(Object value)
    {
        return hashMap.containsValue(value);
    }

    // Returns a Set view of the mappings contained in this
    // map.
    public Set<Map.Entry<K, V> > entrySet()
    {
        return hashMap.entrySet();
    }

    // return the value for which the key is mapped , if key
    // is not mapped with any value then it will return null
    public V get(Object key) { return hashMap.get(key); }

    // return true if hashmap is empty else false
    public boolean isEmpty() { return hashMap.isEmpty(); }

    // Returns a Set view of the keys contained in this map.
    public Set<K> keySet() { return hashMap.keySet(); }

    // map the key with value
    public V put(K key, V value)
    {
        return hashMap.put(key, value);
    }

    // copy all the mapping to this map
    public void putAll(Map<? extends K, ? extends V> m)
    {
        hashMap.putAll(m);
    }

    // remove the mapping of given key
    public V remove(Object key)
    {
        return hashMap.remove(key);
    }

    // returns the size of map(number of key )
    public int size() { return hashMap.size(); }

    // Returns a Collection view of the values contained in
    // this map.
    public Collection<V> values()
    {
        return hashMap.values();
    }
}

class GFG {

    public static void main(String arg[])
    {
        HashMapImplementation<Integer, String> hashMap
            = new HashMapImplementation<Integer, String>();

        hashMap.put(1, "Kapil");
        hashMap.put(2, "Nikhil");
        hashMap.put(3, "Sachin");

        Map<Integer, String> secondMap = new HashMap<Integer, String>();

        secondMap.put(4, "Aakash");
        secondMap.put(5, "Ravi");

        hashMap.putAll(secondMap);

        System.out.println("the key set of the map is ");

        Set<Integer> keySet = hashMap.keySet();

        Iterator<Integer> itr = keySet.iterator();

        while (itr.hasNext())
        {
            System.out.print(itr.next() + "\t");
        }
        System.out.println();

        System.out.println("the values of the map is ");

        Iterator<String> itr1;

        Collection<String> collectionValues = hashMap.values();

        itr1 = collectionValues.iterator();

        while (itr1.hasNext())
        {
            System.out.print(itr1.next() + "\t");
        }
        System.out.println();

        System.out.println("the entry set of the map is ");

        Iterator<Entry<Integer, String> > eitr;

        Set<Entry<Integer, String> > entrySet = hashMap.entrySet();
        eitr = entrySet.iterator();

        while (eitr.hasNext()) 
        {
            System.out.println(eitr.next() + "\t");
        }

        System.out.println("the hash Map contains Key 3 :"
                           + hashMap.containsKey(3));

        System.out.println("the hash Map contains Value Mohan :"
            + hashMap.containsValue("Mohan"));

        System.out.println("the size of the hash Map is "
                           + hashMap.size());
        hashMap.clear();

        if (hashMap.isEmpty())
            System.out.println("the hash Map is empty");
        else
            System.out.println("the hash Map is not empty");
    }
}
```

**Output**

```
the key set of the map is 
1    2    3    4    5    
the values of the map is 
Kapil    Nikhil    Sachin    Aakash    Ravi    
the entry set of the map is 
1=Kapil    
2=Nikhil    
3=Sachin    
4=Aakash    
5=Ravi    
the hash Map contains Key 3 :true
the hash Map contains Value Mohan :false
the size of the hash Map is 5
the hash Map is empty

```