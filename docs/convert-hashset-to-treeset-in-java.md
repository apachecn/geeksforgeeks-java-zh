# 将 HashSet 转换为 Java 中的 TreeSet

> 原文:[https://www . geesforgeks . org/convert-hashset-to-treeset-in-Java/](https://www.geeksforgeeks.org/convert-hashset-to-treeset-in-java/)

**[Hashset](https://www.geeksforgeeks.org/hashset-in-java/):**[Hashset 在 Java 中](https://www.geeksforgeeks.org/hashset-in-java/)一般用于搜索、插入、删除等操作。这些操作平均需要恒定的时间。HashSet 比 TreeSet 快。HashSet 是使用哈希表实现的。

**[TreeSet](https://www.geeksforgeeks.org/treeset-in-java-with-examples/):**[Java 中的 TreeSet](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)取 O(log n)进行搜索、插入、删除，比 HashSet 高。但是 TreeSet 会保留已排序的数据。此外，它还支持更高的()(返回最少更高的元素)、地板()、天花板()等操作。这些操作在 TreeSet 中也是 O(log n)，在 HashSet 中不支持。使用自平衡二叉查找树(红黑树)实现树集。TreeSet 由 Java 中的 TreeMap 支持。

一般来说，如果你想要一个**排序的集合**，那么最好将元素添加到 HashSet 中，然后将其转换为 TreeSet，而不是创建一个 TreeSet 并向其中添加元素。

**给定一个 HashSet，任务是将其转换为 Java 中的 TreeSet。**

**示例:**

```
HashSet: [Geeks, For, Welcome, To]
TreeSet: [For, Geeks, To, Welcome]

HashSet: [1, 2, 3, 4, 5]
TreeSet: [1, 2, 3, 4, 5]

```

我们可以通过以下方式将 **HashSet 转换为**TreeSet:

*   **By invoking the parameterized constructor and sending object of Hash set as a parameter to it.**
    1.  首先，我们必须为哈希集创建一个对象。
    2.  然后我们必须将所有元素添加到哈希集中。
    3.  最后，为树集创建一个对象，并将哈希集对象发送给树集。

    下面是上述方法的实现:

    **程序:**

    ```
    import java.util.HashSet;
    import java.util.Set;
    import java.util.TreeSet;

    public class GFG {

        public static void main(String[] args)
        {

            // Get the HashSet
            Set<String> setobj = new HashSet<>();
            setobj.add("Welcome");
            setobj.add("To");
            setobj.add("Geeks");
            setobj.add("For");
            setobj.add("Geeks");

            System.out.println("HashSet: "
                               + setobj);

            // Convert the HashSet to TreeSet
            Set<String> hashSetToTreeSet
                = new TreeSet<>(setobj);

            // Print the TreeSet
            System.out.println("TreeSet: "
                               + hashSetToTreeSet);
        }
    }
    ```

    **Output:**

    ```
    HashSet: [Geeks, For, Welcome, To]
    TreeSet: [For, Geeks, To, Welcome]

    ```

    *   **By constructing a tree set containing the same elements present in the hash set by using addAll method.**
    1.  首先，我们必须为哈希集创建一个对象。
    2.  然后我们必须将所有元素添加到哈希集中。
    3.  现在为树集创建一个对象。
    4.  使用 addAll 方法向其中添加哈希集的所有元素。

    下面是上述方法的实现:

    **程序:**

    ```
    import java.util.HashSet;
    import java.util.Set;
    import java.util.TreeSet;

    public class GFG {

        public static void main(String[] args)
        {

            // Get the HashSet
            Set<String> setobj = new HashSet<>();
            setobj.add("Welcome");
            setobj.add("To");
            setobj.add("Geeks");
            setobj.add("For");
            setobj.add("Geeks");

            System.out.println("HashSet: "
                               + setobj);

            // Convert the HashSet to TreeSet
            Set<String> hashSetToTreeSet
                = new TreeSet<>();
            hashSetToTreeSet.addAll(setobj);

            // Print the TreeSet
            System.out.println("TreeSet: "
                               + hashSetToTreeSet);
        }
    }
    ```

    **Output:**

    ```
    HashSet: [Geeks, For, Welcome, To]
    TreeSet: [For, Geeks, To, Welcome]

    ```

    *   **By using a for each loop.**( This method is commonly used for conversion between two incompatible types.)
    1.  首先，我们必须为哈希集创建一个对象。
    2.  然后我们必须将所有元素添加到哈希集中。
    3.  现在为树集创建一个对象。
    4.  最后，通过对每个循环使用，将哈希集的所有元素添加到树集中。

    下面是上述方法的实现:

    **程序:**

    ```
    import java.util.HashSet;
    import java.util.Set;
    import java.util.TreeSet;

    public class GFG {

        public static void main(String[] args)
        {

            // Get the HashSet
            Set<String> setobj = new HashSet<>();
            setobj.add("Welcome");
            setobj.add("To");
            setobj.add("Geeks");
            setobj.add("For");
            setobj.add("Geeks");

            System.out.println("HashSet: "
                               + setobj);

            // Convert the HashSet to TreeSet
            Set<String> hashSetToTreeSet
                = new TreeSet<>();
            for (String i : setobj)
                hashSetToTreeSet
                    .add(i);

            // Print the TreeSet
            System.out.println("TreeSet: "
                               + hashSetToTreeSet);
        }
    }
    ```

    **Output:**

    ```
    HashSet: [Geeks, For, Welcome, To]
    TreeSet: [For, Geeks, To, Welcome]

    ```