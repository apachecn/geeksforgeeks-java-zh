# 实现 ConcurrentSkipListMap API 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-concurrentskiplistmap-api/](https://www.geeksforgeeks.org/java-program-to-implement-concurrentskiplistmap-api/)

ConcurrentSkipListMap API 是基于 ConcurrentNavigableMap 的实现的。此地图根据其关键字的自然顺序进行排序，或者在创建时通过地图上提供的比较器进行排序。这个类实现了 SkipLists 的一个并发变体，它使其预期的平均日志时间成本(n)为 containsKey、get、put、remove 操作及其变体。

这个类及其视图和迭代器实现了映射和迭代器接口的所有可选方法。像大多数其他并发集合一样，这个 API 不允许使用**空键**或**值。**是 Java 集合框架的成员。

**所有实现的接口:**

```java
Serializable, Cloneable, ConcurrentMap<K,V>, ConcurrentNavigableMap<K,V>, Map<K,V>, 
NavigableMap<K,V>, SortedMap<K,V>
```

**语法:**

```java
public class ConcurrentSkipListMap<K,V>
 extends AbstractMap<K,V>
implements ConcurrentNavigableMap<K,V>, Cloneable, Serializable
```

**施工人员:**

*   **ConcurrentSkipListMap()**–创建一个新的空地图，根据按键的自然顺序进行排序。
*   **ConcurrentSkipListMap(比较者<？超级 K>c)**–根据给定的比较器创建一个新的空地图。
*   **ConcurrentSkipListMap(地图<？延伸 K，？扩展 V>MP)**–创建与给定地图具有相同映射的新地图，根据按键的自然顺序进行排序。
*   **concurrentSkiplistmap(sorted map<K，？扩展 V>MP)–**创建一个新地图，该地图具有与给定地图相同的映射，并且根据给定的排序地图进行排序。

**方法:**

<figure class="table">

| **方法** | **描述** |
| --- | --- |
| ceilingEntry(K 键) | 此方法返回与最小键相关联的键值对，大于或等于指定键，否则为 null。 |
| 钥匙 | 此方法返回大于或等于指定键的最小键，否则为 null。 |
| 清除() | 此方法从映射中移除所有键值对 |
| 克隆() | 此方法返回 ConcurrentSkipListMap 实例的副本。 |
| 比较器() | 此方法返回用于映射中键排序的比较器，否则如果使用键的自然排序，则返回 null。 |
| 包含密钥(对象密钥) | 如果映射包含给定键的键值对，则此方法返回 true。 |
| 包含值(对象值) | 如果映射为指定值映射了一个或多个键，则此方法返回 true。 |
| 下行键集() | 此方法返回地图关键点的反向导航集合视图 |
| 下行映射() | 此方法返回映射中包含的键值对的逆序视图。 |
| entrySet() | 此方法返回映射中包含的键值对的集合视图。 |
| 等于(对象 0) | 此方法将给定对象与映射进行比较，以确定是否相等。 |
| firstEntry() | 此方法返回与映射中最小键相关联的键值对。 |
| firstKey() | 此方法返回地图中的第一个(最低的)键 |
| 洪水(k 键) | 此方法返回与小于或等于给定键的最大键相关联的键值映射，否则为 null |
| 获取(对象键) | 此方法返回指定键映射到的值，否则为 null |
| isEmpty() | 如果映射中不包含键值对，则此方法返回 true |
| 密钥集() | 此方法返回此地图中包含的键的导航集合视图。 |
| lastEntry() | 此方法返回与映射中最大键相关联的键值对，如果映射为空，则返回 null |
| lastKey() | 此方法返回当前地图中的最后一个(最高)键。 |
| 校长 | 此方法返回键小于 toKey 的地图部分的视图。 |
| 下钥匙 | 此方法返回严格小于给定键的最大键，如果没有这样的键，则返回 null。 |
| 大小() | 此方法返回映射中键值对的数量 |
| 大小映射(K fromKey) | 此方法返回键大于或等于 fromKey 的地图部分的视图。 |
| 值() | 此方法返回地图中值的集合视图 |
| 移除(对象键) | 此方法从映射中移除指定键的映射。 |
| 放(K 键，V 值) | 此方法将给定值与映射中的给定键相关联。 |
| 更换(K 键，V 值) | 如果给定键的值与其他值进行了映射，则此方法会用指定的值替换它。 |

</figure>

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.util.Collection;
import java.util.Comparator;
import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;
import java.util.Map.Entry;
import java.util.NavigableSet;
import java.util.Set;
import java.util.SortedMap;
import java.util.concurrent.ConcurrentNavigableMap;
import java.util.concurrent.ConcurrentSkipListMap;

public class ConcurrentSkipList<K, V> {
    private ConcurrentSkipListMap<K, V> cmp;

    // Creates a new empty map sorted according to the
    // natural ordering of the keys
    public ConcurrentSkipList()
    {
        cmp = new ConcurrentSkipListMap<K, V>();
    }

    // Creates a new empty map sorted according to the gievn
    // comparator
    public ConcurrentSkipList(Comparator<? super K> comp)
    {
        cmp = new ConcurrentSkipListMap<K, V>(comp);
    }

    // Creates a new map with the same key-value pairs as
    // the specified map and sorted according to the natural
    // ordering of the keys.
    public ConcurrentSkipList(
        Map<? extends K, ? extends V> mp)
    {
        cmp = new ConcurrentSkipListMap<K, V>(mp);
    }

    // Creates a new map containing the same key-value pairs
    // and same ordering as the specified map.
    public ConcurrentSkipList(SortedMap<K, ? extends V> mp)
    {
        cmp = new ConcurrentSkipListMap<K, V>(mp);
    }

    // Returns a mapping associated with the least key
    // greater than or equal to the specified key or
    // otherwise null
    public Map.Entry<K, V> ceilingEntry(K k)
    {
        return cmp.ceilingEntry(k);
    }

    // Returns the least key greater than or equal to the
    // specified key or otherwise null
    public K ceilingKey(K k) { return cmp.ceilingKey(k); }

    // Removes all the key-value pairs of the map
    public void clear() { cmp.clear(); }

    // Returns a copy of the ConcurrentSkipListMap
    public ConcurrentSkipListMap<K, V> clone()
    {
        return cmp.clone();
    }

    // Returns the comparator used for ordering the keys in
    // the map
    public Comparator<? super K> comparator()
    {
        return cmp.comparator();
    }

    // Returns true if the map contains the specified key.
    public boolean containsKey(Object k)
    {
        return cmp.containsKey(k);
    }

    // Returns true if the map contains one or more keys
    // mapped to the given value
    public boolean containsValue(Object v)
    {
        return cmp.containsValue(v);
    }

    // Returns a reverse order NavigableSet view of the keys
    // in the map
    public NavigableSet<K> descendingKeySet()
    {
        return cmp.descendingKeySet();
    }

    // Returns a reverse order view of the key-value pairs
    // in the map.
    public ConcurrentNavigableMap<K, V> descendingMap()
    {
        return cmp.descendingMap();
    }

    // Returns a Set view of the key-value pairs in the map
    public Set<Map.Entry<K, V> > entrySet()
    {
        return cmp.entrySet();
    }

    // Returns the mapping that is associated with the least
    // key in the map or otherwise null
    public Map.Entry<K, V> firstEntry()
    {
        return cmp.firstEntry();
    }

    // Returns the first (lowest) key in the map.
    public K firstKey() { return cmp.firstKey(); }

    // Returns the greatest key less than or equal to the
    // specified key or otherwise null
    public K floorKey(K k) { return cmp.floorKey(k); }

    // Returns the value to which the given key is mapped
    public V get(Object k) { return cmp.get(k); }

    // Returns a portion of the map whose keys are strictly
    // less than k
    public ConcurrentNavigableMap<K, V> headMap(K k)
    {
        return cmp.headMap(k);
    }

    // Returns a portion of the map whose keys are strictly
    // less than or equal to k
    public ConcurrentNavigableMap<K, V> headMap(K k,
                                                boolean in)
    {
        return cmp.headMap(k, in);
    }

    // Returns a mapping that is associated with the least
    // key strictly greater than the specified key or
    // otherwise null
    public Map.Entry<K, V> higherEntry(K k)
    {
        return cmp.higherEntry(k);
    }

    // Returns the least key strictly greater than the given
    // key, or otherwise null.
    public K higherKey(K k) { return cmp.higherKey(k); }

    // Returs the set view of the keys in the map
    public Set<K> keySet() { return cmp.keySet(); }

    // Returns a mapping associated with the greatest key in
    // the map, or otherwise null.
    public Map.Entry<K, V> lastEntry()
    {
        return cmp.lastEntry();
    }

    // Returns the last(highest) key in the map.
    public K lastKey() { return cmp.lastKey(); }

    // Returns a mapping that is associated with the
    // greatest key strictly less than the specified key or
    // otherwise null
    public Map.Entry<K, V> lowerEntry(K k)
    {
        return cmp.lowerEntry(k);
    }

    // Returns the greatest key strictly less than the given
    // key or otherwise null
    public K lowerKey(K k) { return cmp.lowerKey(k); }

    // Returns a NavigableSet view of the keys in the map.
    public NavigableSet<K> navigableKeySet()
    {
        return cmp.navigableKeySet();
    }

    // Removes and returns a mapping associated with the
    // least key in the map, or otherwise null
    public Map.Entry<K, V> pollFirstEntry()
    {
        return cmp.pollFirstEntry();
    }

    // Removes and returns a  mapping associated with the
    // greatest key
    // in the map, or otherwise null
    public Map.Entry<K, V> pollLastEntry()
    {
        return cmp.pollLastEntry();
    }

    // Maps the given value to the given key in the map
    public V put(K k, V v) { return cmp.put(k, v); }

    // Copies all the key-value pairs of the given map to
    // the ConcurrentSkipListMap
    public void putAll(Map<? extends K, ? extends V> mp)
    {
        cmp.putAll(mp);
    }

    // Removes the mapping of the given key from the map
    public V remove(Object k) { return cmp.remove(k); }

    // Replaces the given key with the given value if the
    // key is already mapped
    public V replace(K k, V v) { return cmp.replace(k, v); }

    // Replaces the given key with the given value if the
    // key is already mapped
    public boolean replace(K k, V oValue, V nValue)
    {
        return cmp.replace(k, oValue, nValue);
    }

    // Returns the number of mapping in the map
    public int size() { return cmp.size(); }

    // Return a portion of the map whose keys are from k1 to
    // k2
    public ConcurrentNavigableMap<K, V>
    subMap(K k1, boolean f, K k2, boolean t)
    {
        return cmp.subMap(k1, f, k2, t);
    }

    // Returns a portion of the map whose keys are from
    // k1(inclusive) to k2(exclusive)
    public ConcurrentNavigableMap<K, V> subMap(K k1, K k2)
    {
        return cmp.subMap(k1, k2);
    }

    // Returns a Collection view of the values of the map
    public Collection<V> values() { return cmp.values(); }

    public static void main(String[] arg)
    {
        ConcurrentSkipList<Integer, String> cmp
            = new ConcurrentSkipList<Integer, String>();
        cmp.put(1, "Sahil");
        cmp.put(2, "Kahish");
        cmp.put(3, "Tarun");
        cmp.put(4, "Karan");
        Map<Integer, String> mp
            = new HashMap<Integer, String>();
        mp.put(5, "Shweta");
        mp.put(6, "Aditya");
        cmp.putAll(mp);

        System.out.println("The key set of the map is ");
        Set<Integer> kSet = cmp.keySet();
        Iterator<Integer> i = kSet.iterator();
        while (i.hasNext()) {
            System.out.print(i.next() + " ");
        }
        System.out.println();
        System.out.println("The values of the Map is ");
        Collection<String> values = cmp.values();
        Iterator<String> it = values.iterator();
        it = values.iterator();
        while (it.hasNext()) {
            System.out.print(it.next() + " ");
        }
        System.out.println();
        System.out.println(
            "Poll first entry of the ConcurrentSkipListMap ");
        Map.Entry<Integer, String> pfe
            = cmp.pollFirstEntry();
        System.out.println("Key = " + pfe.getKey()
                           + " Value = " + pfe.getValue());
        System.out.println(
            "Poll last entry of the ConcurrentSkipListMap ");
        Map.Entry<Integer, String> ple
            = cmp.pollLastEntry();
        System.out.println("key = " + ple.getKey()
                           + " value = " + ple.getValue());
        System.out.println("The entry set of the map is ");
        Iterator<Entry<Integer, String> > itr;
        Set<Entry<Integer, String> > eSet = cmp.entrySet();
        itr = eSet.iterator();
        while (itr.hasNext()) {
            System.out.println(itr.next() + " ");
        }
        System.out.println(
            "The concurrentSkipListMap contains Key 4 :"
            + cmp.containsKey(4));
        System.out.println(
            "The  concurrentSkipListMap contains Value 9 :"
            + cmp.containsValue(9));
        System.out.println(
            "The size of the concurrentSkipListMap is "
            + cmp.size());
        cmp.clear();
    }
}
```

**输出:**

```java
The key set of the map is 
1    2    3    4    5    6    
The values of the concurrentSkipListMap is 
Sahil    Kashish    Tarun    Karan    Shweta    Aditya    
Poll first entry of the ConcurrentSkipListMap 
key = 1 value = Sahil
Poll last entry of the ConcurrentSkipListMap
key = 6 value = Aditya
The entry set of the Map is 
2=Kashish    
3=Tarun    
4=Karan    
5=Shweta
The concurrentSkipListMap contains Key 4 :true
The  concurrentSkipListMap contains Value 9 :false
The size of the concurrentSkipListMap is 6
```