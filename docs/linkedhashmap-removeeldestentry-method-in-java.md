# Java 中的 LinkedHashMap removeEldestEntry()方法

> 原文:[https://www . geeksforgeeks . org/link edhashmap-removeelderstantry-method-in-Java/](https://www.geeksforgeeks.org/linkedhashmap-removeeldestentry-method-in-java/)

java 中的 Java . util . LinkedHashMap . removeelderstantry()方法用于跟踪地图是否从地图中删除了任何最早的条目。因此，每次向 LinkedHashMap 添加新元素时，最早的条目都会从地图中移除。此方法通常在通过使用 put()和 putall()方法将元素添加到映射中后调用。
该方法允许地图按照其返回值的指示修改自身。虽然该方法被允许直接修改地图，但如果它这样做了，它必须返回 false，这将表明地图不应该尝试任何进一步的修改导致模糊的事实。从该方法中修改地图后返回 true 的效果未指定。
当映射表示一个缓存时，这非常有用，它允许映射通过一个接一个地删除过时条目来减少内存消耗。
**语法:**

```java
private boolean removeEldestEntry(Map.Entry *eldest*)
```

**参数:**该方法接受一个参数*最早的*，该参数是指地图中最近插入最少的条目。如果地图是访问顺序，则*最早的*指最近最少访问的条目，如果该方法返回真，则该条目将被删除。如果在 put 或 putAll 调用之前映射是空的，这将是刚刚插入的条目；换句话说，如果地图包含一个条目，最早的条目也是最新的条目。
**返回值:**如果要从地图中移除最早的*条目，地图返回真，如果不移除或保留该条目，地图返回假。
下面的程序用来说明 Java . util . linkedhashmap . removeelderstantry()方法的工作原理:* 

## *Java 语言(一种计算机语言，尤用于创建网站)*

```java
*// Java program to illustrate removeEldestEntry()
import java.util.*;

public class Linked_Hash_Map_Demo {

    // Refers to the max size of the map following which
    // the removal takes place of the eldest entry
    private static final int MAX = 6;

    public static void main(String[] args)
    {

        // Creating the linked hashmap and implementing
        // removeEldestEntry() to MAX size
        LinkedHashMap<Integer, String> li_hash_map =
        new LinkedHashMap<Integer, String>() {
            protected boolean removeEldestEntry(Map.Entry<Integer, String> eldest)
            {
                return size() > MAX;
            }
        };
        // Adding elements using put()
        li_hash_map.put(0, "Welcome");
        li_hash_map.put(1, "To");
        li_hash_map.put(2, "The");
        li_hash_map.put(3, "World");
        li_hash_map.put(4, "Of");
        li_hash_map.put(5, "geeks");

        System.out.println("" + li_hash_map);

        // Adding more elements
        li_hash_map.put(6, "GeeksforGeeks");

        // Displaying the map after adding one more element
        System.out.println("" + li_hash_map);

        // Adding more elements
        li_hash_map.put(7, "Hello");

        // Displaying the map after adding one more element
        System.out.println("" + li_hash_map);
    }
}*
```

***Output:** 

```java
{0=Welcome, 1=To, 2=The, 3=World, 4=Of, 5=geeks}
{1=To, 2=The, 3=World, 4=Of, 5=geeks, 6=GeeksforGeeks}
{2=The, 3=World, 4=Of, 5=geeks, 6=GeeksforGeeks, 7=Hello}
```* 

***参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/linkedhashmap . html # removeelderstantry-Java . util . map . entry-](https://docs.oracle.com/javase/8/docs/api/java/util/LinkedHashMap.html#removeEldestEntry-java.util.Map.Entry-)*