# Java 中的 HashMap 类方法，示例| Set 1 (put()、get()、isEmpty()和 size())

> 原文:[https://www . geesforgeks . org/hashmap-class-methods-Java-examples-set-1-put-get-isempty-size/](https://www.geeksforgeeks.org/hashmap-class-methods-java-examples-set-1-put-get-isempty-size/)

HashMap 是一种数据结构，它使用哈希函数将标识值(称为键)映射到它们的关联值。它包含“键值”对，允许按键检索值。

最令人印象深刻的特性是它的元素快速查找，尤其是对于大数量的元素。默认情况下它是不同步的，但是我们可以通过调用

```java
 Map myhash = Collections.synchronizedMap(hashMap);
```

在创建时，防止对地图的意外非同步访问。

这些是各种重要的 hashmap 类方法。这篇文章解释了:put()，get()，isEmpty()和 size()

1.  **put():** java.util.HashMap.put() plays role in associating the specified value with the specified key in this map. If the map previously contained a mapping for the key, the old value is replaced.

    **语法:**

    ```java
    public V put(K key,V value)
    Parameters:
    key - key with which the specified value is to be associated
    value - value to be associated with the specified key
    Return: the previous value associated with
    key, or null if there was no mapping for key. 

    ```

2.  **get():** java.util.HashMap.get()method returns the value to which the specified key is mapped, or null if this map contains no mapping for the key.

    **语法:**

    ```java
    public V get(Object key)
    Parameters:
    key - the key whose associated value is to be returned
    Return: the value to which the specified 
    key is mapped, or null if this map contains no mapping for
    the key.

    ```

3.  **isEmpty():** java.util.HashMap.isEmpty() method returns true if the map contains no key-value mappings.

    **语法:**

    ```java
    public boolean isEmpty()
    Return: true if this map contains no key-value mappings

    ```

4.  **size():** java.util.HashMap.size() returns the number of key-value mappings in this map.

    **语法:**

    ```java
    public int size()
    Return: the number of key-value mappings in this map.

    ```

**实现说明上述方法**

```java
// Java program illustrating use of HashMap methods -
// put(), get(), isEmpty() and size()
import java.util.*;
public class NewClass
{
    public static void main(String args[])
    {
        // Creation of HashMap
        HashMap<String, String> Geeks = new HashMap<>();

        // Adding values to HashMap as ("keys", "values")
        Geeks.put("Language", "Java");
        Geeks.put("Platform", "Geeks For geeks");
        Geeks.put("Code", "HashMap");
        Geeks.put("Learn", "More");

        System.out.println("Testing .isEmpty() method");

        // Checks whether the HashMap is empty or not
        // Not empty so printing the values
        if (!Geeks.isEmpty())
        {
            System.out.println("HashMap Geeks is notempty");

            // Accessing the contents of HashMap through Keys
            System.out.println("GEEKS : " + Geeks.get("Language"));
            System.out.println("GEEKS : " + Geeks.get("Platform"));
            System.out.println("GEEKS : " + Geeks.get("Code"));
            System.out.println("GEEKS : " + Geeks.get("Learn"));

            // size() method prints the size of HashMap.
            System.out.println("Size Of HashMap : " + Geeks.size());
        }
    }
}
```

**输出**

```java
Testing .isEmpty() method
HashMap Geeks is notempty
GEEKS : Java
GEEKS : Geeks For geeks
GEEKS : HashMap
GEEKS : More
Size Of HashMap : 4

```

【HashMap 和 TreeMap 有什么区别？

1.  HashMap 实现 Map 接口，而 TreeMap 实现 SortedMap 接口。排序地图界面是地图的子界面。
2.  哈希映射实现哈希，而树映射实现红黑树(一个自平衡二叉查找树)。因此，哈希和平衡二叉查找树之间的所有差异都适用于此。
3.  HashMap 和 TreeMap 都有它们的对应物 HashSet 和 TreeSet。HashSet 和 TreeSet 实现[设置界面](http://geeksquiz.com/set-in-java/)。在 HashSet 和 TreeSet 中，我们只有键，没有值，这些主要用来查看一个集合中的有无。对于上述问题，我们不能使用 HashSet(或 TreeSet)，因为我们不能存储计数。我们更喜欢 HashSet(或 TreeSet)而不是 HashMap(或 TreeMap)的一个问题是打印数组中所有不同的元素。

详见 [HashMap 和](https://www.geeksforgeeks.org/hashmap-treemap-java/)tree map。

**在 Java 中 HashMap 和 HashTable 有什么区别？**

*   HashMap 是非同步的。它不是线程安全的，没有适当的同步代码就不能在许多线程之间共享，而哈希表是同步的。它是线程安全的，可以与许多线程共享。
*   HashMap 允许一个空键和多个空值，而 Hashtable 不允许任何空键或空值。
*   如果不需要线程同步，HashMap 通常比 HashTable 更受欢迎
*   HashMap 是 Hashtable 的高级版本和改进。HashMap 是后来创建的。

详见[Java 中 HashMap 和 HashTable 的区别](https://www.geeksforgeeks.org/differences-between-hashmap-and-hashtable-in-java/)。

【HashMap 和 HashSet 有什么区别？

*   HashMap 存储键值对(例如，将学生的记录作为值，将卷号作为键)，而 HashSet 只存储键(例如，如果是整数，则存储一组键)。
*   HashSet 在内部使用 HashMap 来存储密钥

详见 Java 中 [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 。

 **[Java 中的 Hashmap 方法示例| Set 2 (keySet()，values()，containsKey())](https://www.geeksforgeeks.org/hashmap-methods-java-examples-set-2-keyset-values-containskey/)**

**参考:**
[https://docs . Oracle . com/javase/7/docs/API/Java/util/hashmap . html](https://docs.oracle.com/javase/7/docs/api/java/util/HashMap.html)

本文由**莫希特·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。