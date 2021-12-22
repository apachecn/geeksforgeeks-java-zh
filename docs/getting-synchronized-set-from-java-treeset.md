# 从 Java 树集中获取同步集

> 原文:[https://www . geeksforgeeks . org/get-synchronized-set-from-Java-treeset/](https://www.geeksforgeeks.org/getting-synchronized-set-from-java-treeset/)

在[**Java . util . collections**](https://www.geeksforgeeks.org/collections-in-java-2/)类中， **synchronizedSet()** 方法用于返回由指定集合支持的同步(线程安全)集合。此方法将 TreeSet 作为参数。为了保证串行访问，通过返回的集合完成对支持集合的所有访问是非常关键的。我们有 Java TreeSet，我们的任务是从中获取一个同步集。为此，请使用 Collections 类的 synchronizedSet 方法。

**例:**

```
Input : HashSet = [3, 4, 5]
Output: synchronizedSet = [3, 4, 5]

Input : HashSet = ['A', 'B', 'C']
Output: synchronizedSet = ['A', 'B', 'C']
```

**语法:**

```
public static <T> Set<T> synchronizedSet(Set<T> s)
```

**参数:** TreeSet 作为一个要“包装”在同步集中的参数。

**返回值:**

```
Synchronized view of the specified set.
```

**方法:**

1.  Create [tree set](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) .
2.  Add some elements to the tree set.
3.  Create a collection variable and assign it using the Collections.synchronizedSet () method.
4.  Print a new synchronization set.

下面是上述方法的实现:

T3】JavaT5

```
// Java program to get synchronized
// set from given tree set
import java.util.Collections;
import java.util.Set;
import java.util.TreeSet;

class GFG {
    public static void main(String[] args)
    {
        TreeSet<Integer> treeSet = new TreeSet<Integer>();

        // Elements are added using add() method
        treeSet.add(48);
        treeSet.add(49);
        treeSet.add(59);
        treeSet.add(38);
        System.out.println("TreeSet : "+treeSet);

        // converting tree set to synchronized set
        Set set = Collections.synchronizedSet(treeSet);
        System.out.println("SynchronizedSet : "+set);
    }
}
```

T6T8**输出**T1