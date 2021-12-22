# 实现树形图应用编程接口的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-treemap-api/](https://www.geeksforgeeks.org/java-program-to-implement-treemap-api/)

[**树状图**](https://www.geeksforgeeks.org/treemap-in-java/) 用于在 java 中实现 [**地图界面**](https://www.geeksforgeeks.org/map-interface-java-examples/) 和 [**导航地图**](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/) 以及 [**抽象地图**](https://www.geeksforgeeks.org/abstractmap-in-java/) 类。地图根据其键的自然顺序进行排序，或者根据地图创建时提供的 [**比较器**](https://www.geeksforgeeks.org/comparator-interface-java/) 进行排序，具体取决于使用的构造函数。

现在，在实现 TreeMap API 时，任务分为两部分:

1.  创建一个类，包含它的树映射的所有方法都被命名为“树映射实现”
2.  实现上面的树形图应用编程接口

树图应用编程接口的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program demonstrate TreeMap API
import java.util.*;

class TreeMapImplementation<K, V> {
    private TreeMap<K, V> map;

    // Constructor creates a new empty tree map
    public TreeMapImplementation()
    {
        map = new TreeMap<K, V>();
    }

    // Constructor creates a new empty tree
    // map according to the given comparator.
    public TreeMapImplementation(
        Comparator<? super K> comparator)
    {
        map = new TreeMap<K, V>(comparator);
    }

    // Constructor creates a new empty tree
    // map according to the given map
    public TreeMapImplementation(
        Map<? extends K, ? extends V> map1)
    {
        map = new TreeMap<K, V>(map1);
    }

    // Constructor creates a new Treemap
    // according to given sortedMap
    public TreeMapImplementation(
        SortedMap<K, ? extends V> m)
    {
        map = new TreeMap<K, V>(m);
    }

    // Returns a key-value pair associated with
    // the least key greater than or equal to the
    // given key, if not present returns null
    public Map.Entry<K, V> ceilingEntry(K key)
    {
        return map.ceilingEntry(key);
    }

    // Returns the least key greater than or equal
    // to the given key,if not present returns null
    public K ceilingKey(K key)
    {
        return map.ceilingKey(key);
    }

    // Delete all the key-value pair
    public void clear() { map.clear(); }

    // Returns a shallow copy of the TreeMap instance
    public Object clone() { return map.clone(); }

    // Returns the comparator used to order
    // the keys in the map
    public Comparator<? super K> comparator()
    {
        return map.comparator();
    }

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

    // Returns a reverse order NavigableSet view of the keys
    public NavigableSet<K> descendingKeySet()
    {
        return map.descendingKeySet();
    }

    // Returns a reverse order view of the mappings
    public NavigableMap<K, V> descendingMap()
    {
        return map.descendingMap();
    }

    // Returns a Set view of the mappings
    public Set<Map.Entry<K, V> > entrySet()
    {
        return map.entrySet();
    }

    // Returns a key-value mapping associated with the
    // least key in the map, if map is empty returns null
    public Map.Entry<K, V> firstEntry()
    {
        return map.firstEntry();
    }

    // Returns the first(lowest) key
    public K firstKey() { return map.firstKey(); }

    // Returns the greatest key less than
    // or equal to the given key
    public K floorKey(K key) { return map.floorKey(key); }

    // Returns the value to which the specified
    // key is mapped, returns null if map does
    // not contains given key
    public V get(Object key) { return map.get(key); }

    // Returns a view of the portion of the map
    // whose keys are strictly less than the key
    public SortedMap<K, V> headMap(K key)
    {
        return map.headMap(key);
    }

    // Returns a view of the portion of the map
    // whose keys are less than or equal to, if
    // inclusive is true to key.
    public NavigableMap<K, V> headMap(K key,
                                      boolean include)
    {
        return map.headMap(key, include);
    }

    // Returns a key-value mapping associated with
    // the least key strictly greater than the given
    // key, returns null if there is no such key.
    public Map.Entry<K, V> higherEntry(K key)
    {
        return map.higherEntry(key);
    }

    // Returns the least key strictly greater than the
    // given key, returns null if there is no such key.
    public K higherKey(K key) { return map.higherKey(key); }

    // Returns a Set view of the keys
    public Set<K> keySet() { return map.keySet(); }

    // Returns a key-value mapping associated
    // with the greatest key in the map
    public Map.Entry<K, V> lastEntry()
    {
        return map.lastEntry();
    }

    // Returns the last (highest) key
    public K lastKey() { return map.lastKey(); }

    // Returns a key-value mapping associated with
    // the greatest key strictly less than the given
    // key, returns null if there is no such key.
    public Map.Entry<K, V> lowerEntry(K key)
    {
        return map.lowerEntry(key);
    }

    // Returns the greatest key strictly less than
    // the given key, or null if there is no such key
    public K lowerKey(K key) { return map.lowerKey(key); }

    // Returns a NavigableSet view of the keys
    public NavigableSet<K> navigableKeySet()
    {
        return map.navigableKeySet();
    }

    // Removes and returns a key-value mapping
    // associated with the least key in the map,
    // or null if the map is empty.
    public Map.Entry<K, V> pollFirstEntry()
    {
        return map.pollFirstEntry();
    }

    // Removes and returns a key-value mapping
    // associated with the greatest key in the map,
    // or null if the map is empty.
    public Map.Entry<K, V> pollLastEntry()
    {
        return map.pollLastEntry();
    }

    // Associates the specified value with
    // the specified key in the map
    public V put(K key, V val) { return map.put(key, val); }

    // Copies all of the mappings from
    // the specified map to the map
    public void putAll(Map<? extends K, ? extends V> map1)
    {
        map.putAll(map1);
    }

    // Removes the mapping for the key
    // from the TreeMap if present
    public V remove(Object key) { return map.remove(key); }

    // Returns the size of the map
    public int size() { return map.size(); }

    // Returns a view of the portion of the map whose keys
    // range from rKey, inclusive, to rKey, exclusive
    public NavigableMap<K, V> subMap(K lKey,
                                     boolean lInclude,
                                     K rKey,
                                     boolean rInclude)
    {
        return map.subMap(lKey, lInclude, rKey, rInclude);
    }

    // Returns a view of the portion of the map
    // whose keys range from lKey to rKey
    public SortedMap<K, V> subMap(K lKey, K rKey)
    {
        return map.subMap(lKey, rKey);
    }

    // Returns a Collection view of the values
    public Collection<V> values() { return map.values(); }
}
public class GFG {
    public static void main(String[] arg)
    {

        TreeMapImplementation<String, Integer> student
            = new TreeMapImplementation<>();

        // Add elements to the treemap
        student.put("Akshay", 500);
        student.put("Ashok", 460);
        student.put("Aakash", 495);

        System.out.println(
            "The key value pairs of TreeMap:");

        // Print the key value pairs of TreeMap
        for (Map.Entry<String, Integer> entry :
             student.entrySet()) {
            System.out.println(entry.getKey() + " : "
                               + entry.getValue());
        }

        // Print the size of the treemap
        System.out.println(
            "Size of the TreeMap after insertion: "
            + student.size());

        // Print first entry
        System.out.println("Poll first entry of the map: ");
        Map.Entry<String, Integer> firstEntry
            = student.pollFirstEntry();
        System.out.println();
        System.out.println(firstEntry.getKey() + " : "
                           + firstEntry.getValue());

        // Print treemap contains key akshay or not
        System.out.println("TreeMap contains Akshay: "
                           + student.containsKey("Akshay"));

        System.out.println("Deleting all the entries");

        // Deletes all the entry
        student.clear();

        System.out.println("Size of the treemap: "
                           + student.size());
    }
}
```

**Output**

```
The key value pairs of TreeMap:
Aakash : 495
Akshay : 500
Ashok : 460
Size of the TreeMap after insertion: 3
Poll first entry of the map: 

Aakash : 495
TreeMap contains Akshay: true
Deleting all the entries
Size of the treemap: 0

```