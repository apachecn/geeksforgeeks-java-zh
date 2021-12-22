# 从 Java HashSet 获取同步集

> 原文:[https://www . geesforgeks . org/get-synchronized-set-from-Java-hashset/](https://www.geeksforgeeks.org/getting-synchronized-set-from-java-hashset/)

在[**Java . util . collections**](https://www.geeksforgeeks.org/collections-in-java-2/)类中， **synchronizedSet()** 方法用于返回由指定集合支持的同步(线程安全)集合。这个方法将 HashSet 作为一个参数。为了保证串行访问，通过返回的集合完成对支持集合的所有访问是非常关键的。任务是从给定的哈希集中获取同步集。

**例:**

```
Input : HashSet = [3, 4, 5]
Output: synchronizedSet = [3, 4, 5]

Input : HashSet = ['a', 'b', 'c']
Output: synchronizedSet = ['a', 'b', 'c']
```

**语法:**

```
public static <T> Set<T> synchronizedSet(Set<T> s)
```

**参数:** HashSet 作为一个参数被“包装”在一个同步的集合中。

**返回值:**指定集合的同步视图。

**方法:**

1.  哼哼哼哈希集。
2.  Add some elements to HashSet.
3.  Create a collection variable and assign it using the Collections.synchronizedSet () method.
4.  Print a new synchronization set.

下面是上述方法的实现**:**

## Java

```
// Java code to get synchronized
// set from hash set
import java.util.*;
public class GFG {
    public static void main(String args[])
    {
        // creating hash set
        Set<Integer> hash_set = new HashSet<Integer>();

        // adding the elements to hash set
        hash_set.add(1);
        hash_set.add(2);
        hash_set.add(3);
        hash_set.add(4);
        hash_set.add(5);

        // changing hash set to synchronized
        // set and storing in set
        Set synset = Collections.synchronizedSet(hash_set);
        System.out.println("Synchronized Set: " + synset);
    }
}
```

**输出**

```
Synchronized Set: [1, 2, 3, 4, 5]
```