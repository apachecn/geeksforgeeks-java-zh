# 如何在 Java 中移除向量中的重复元素？

> 原文:[https://www . geesforgeks . org/如何从 java 矢量中删除重复元素/](https://www.geeksforgeeks.org/how-to-remove-duplicate-elements-from-the-vector-in-java/)

使用[链接的哈希集](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/)和[树集](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)，删除重复的元素。因为 LinkedHashSet 和 TreeSet 不接受重复的元素。

**例:**

```
Input : vector = [1, 2, 3, 4, 2, 4]
Output: vector = [1, 2, 3, 4]

Input : vector = [a, b, a, c, d, a]
Output: vector = [a, b, c, d]
```

**方法 1:使用 LinkedHashSet**

LinkedHashSet 不接受重复元素，也不维护排序顺序。

1.  创建矢量并在矢量中添加元素。
2.  创建 LinkedHashSet，并将向量对象传递给 LinkedHashSet 的构造函数。
3.  清除向量的所有元素。
4.  将向量中 LinkedHashSet 的所有元素相加。

下面是上述方法的实现:

T3】JavaT5

```
// Java Program to remove duplicate 
// elements from Vector
import java.util.LinkedHashSet;
import java.util.Vector;

public class GFG {

    public static void main(String[] args)
    {

        Vector<Integer> vector = new Vector<Integer>();

        vector.add(2);
        vector.add(2);
        vector.add(4);
        vector.add(2);
        vector.add(3);
        vector.add(2);
        vector.add(1);

        // display original elements
        System.out.println("Display original Vector - "
                           + vector);

        // convert Vector to a LinkedHashSet object.
        LinkedHashSet<Integer> hashSet
            = new LinkedHashSet<Integer>(vector);

        // clear all elements of vector
        vector.clear();

        // add all unique elements LinkedHashSet to the
        // vector
        vector.addAll(hashSet);

        // display vector after removing duplicate elements
        System.out.println(
            "After removing duplicate elements - "
            + vector);
    }
}
```

T6T8**输出**T1

**时间复杂度:** O(N)，其中 N 为原始向量的长度。

**方法 2:树集合**

TreeSet 不接受重复的元素，TreeSet 保持排序顺序。

1.  Create a vector and add elements to the vector.
2.  Create a tree set, and pass the vector object to the constructor of the tree set.
3.  Clear all elements of the vector.
4.  Add all elements of TreeSet in the vector.

下面是上述方法的实现:

T3】JavaT5

```
// Java Program to remove duplicate 
// elements from Vector
import java.util.TreeSet;
import java.util.Vector;

public class GFG {

    public static void main(String[] args)
    {

        // create vector
        Vector<Integer> vector = new Vector<Integer>();

        // add elements in vector
        vector.add(4);
        vector.add(2);
        vector.add(3);
        vector.add(1);
        vector.add(3);
        vector.add(2);
        vector.add(4);

        // display original vector
        System.out.println("Display original Vector - "
                           + vector);

        // convert Vector to a TreeSet object.
        TreeSet<Integer> treeSet
            = new TreeSet<Integer>(vector);

        // clear all elements of vector
        vector.clear();

        // add all unique elements of TreeSet to the vector
        vector.addAll(treeSet);

        // display vector after removing duplicate elements
        System.out.println(
            "After removing duplicate elements - "
            + vector);
    }
}
```

T6T8**输出**T1

**时间复杂度:** O(n log n)，因为 TreeSet 使用红黑树实现。