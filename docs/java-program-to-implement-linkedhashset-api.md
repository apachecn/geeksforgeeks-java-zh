# 实现 LinkedHashSet API 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-linkedhashset-api/](https://www.geeksforgeeks.org/java-program-to-implement-linkedhashset-api/)

[**链接的 HashSet**](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 是 [**HashSet**](https://www.geeksforgeeks.org/hashset-in-java/) 的有序版本，它维护所有元素的双向链表。当需要维护迭代顺序时，使用这个类。当遍历 HashSet 时，顺序是不可预测的，而 LinkedHashSet 允许我们按照元素插入的顺序遍历元素。当使用迭代器循环遍历 LinkedHashSet 时，元素将返回到它们被插入的顺序。

为了首先实现 LinkedHashSet API，我们创建了一个类“LinkedHashSetImplmentation”，并在这个类中创建了 LinkedHashSet 的所有方法。

**链接哈希映射应用编程接口的实现:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to implement LinkedHashSet API

import java.util.*;

class LinkedHashSetImplementation<E> {
    private LinkedHashSet<E> set;

    // Constructor creates a new LinkedHashSet
    public LinkedHashSetImplementation()
    {
        set = new LinkedHashSet<E>();
    }

    // Constructor creates a new empty linkedhash set
    // according to the given set
    public LinkedHashSetImplementation(
        Collection<? extends E> set1)
    {
        set = new LinkedHashSet<E>(set1);
    }

    // Returns the size of the set
    public int size() { return set.size(); }

    // Returns true if set is empty otherwise return false
    public boolean isEmpty() { return set.isEmpty(); }

    // Returns true if set contains specified value
    public boolean contains(Object val)
    {
        return set.contains(val);
    }

    // Returns an iterator over set elements
    public Iterator<E> iterator() { return set.iterator(); }

    // Returns an array containing all of the elements of
    // the set
    public Object[] toArray() { return set.toArray(); }

    // Returns an array containing all of the elements of
    // the set
    public <T> T[] toArray(T[] a) { return set.toArray(a); }

    // Add element to the set
    public boolean add(E ele) { return set.add(ele); }

    // Removes the specified element from the set if it is
    // present
    public boolean remove(Object ele)
    {
        return set.remove(ele);
    }

    // Returns true if the set contains all of the elements
    // of the specified collection
    public boolean containsAll(Collection<?> c)
    {
        return set.containsAll(c);
    }

    // Adds all of the elements in the specified collection
    // to the set
    public boolean addAll(Collection<? extends E> col)
    {
        return set.addAll(col);
    }

    // Retains only the elements in this set that are
    // contained in the specified collection
    public boolean retainAll(Collection<?> col)
    {
        return set.retainAll(col);
    }

    // Removes from this set all of its elements that are
    // contained in the given collection
    public boolean removeAll(Collection<?> col)
    {
        return set.retainAll(col);
    }

    // Removes all of the elements from the set
    public void clear() { set.clear(); }

    // Compares the specified object with the set
    public boolean equals(Object obj)
    {
        return set.equals(obj);
    }

    // Returns the hash code value for the set
    public int hashCode() { return set.hashCode(); }
}
public class GFG {
    public static void main(String[] arg)
    {
        LinkedHashSetImplementation<Integer> set
            = new LinkedHashSetImplementation<>();

        // Add elements to set
        set.add(10);
        set.add(20);
        set.add(30);
        set.add(40);
        set.add(50);
        set.add(30);
        set.add(40);

        // Print the size of the set
        System.out.println("Size of the LinkedHashset: "
                           + set.size());

        // Iterate set elements
        System.out.println(
            "The LinkedHashSet elements are:");

        Iterator it = set.iterator();

        while (it.hasNext()) {
            // print set data
            System.out.println(it.next());
        }

        // Check whether set is empty or not
        System.out.println("The linkedHashSet is empty: "
                           + set.isEmpty());

        // Print true if set contains 60 else print false
        System.out.println("LinkedHashSet contains 60: "
                           + set.contains(60));

        // Print true if set contains 40 else print false
        System.out.println("LinkedHashSet contains 40: "
                           + set.contains(40));

        // Remove element from Set
        set.remove(40);

        // print size
        System.out.println("Size of the linkedHashSet:"
                           + set.size());

        // Delete all the elements of the set
        set.clear();

        System.out.println("Size of the set after clear:"
                           + set.size());
    }
}
```

**Output**

```
Size of the LinkedHashset: 5
The LinkedHashSet elements are:
10
20
30
40
50
The linkedHashSet is empty: false
LinkedHashSet contains 60: false
LinkedHashSet contains 40: true
Size of the linkedHashSet:4
Size of the set after clear:0
```