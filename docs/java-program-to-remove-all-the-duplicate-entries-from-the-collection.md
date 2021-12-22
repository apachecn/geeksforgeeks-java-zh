# 从集合中移除所有重复条目的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-remove-all-replicate-entries-from-collection/](https://www.geeksforgeeks.org/java-program-to-remove-all-the-duplicate-entries-from-the-collection/)

我们知道 [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 只包含唯一的元素，即不允许重复的条目，由于我们的目标是从[集合](https://www.geeksforgeeks.org/collections-in-java-2/)中移除重复的条目，因此为了从集合中移除所有重复的条目，我们将使用 HashSet **。**HashSet 类实现了 Set 接口，由哈希表支持，哈希表实际上是一个 [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java/) 实例。该类还为基本操作(如添加、移除、包含和大小)提供了恒定的时间性能，假设哈希函数将元素适当地分散在桶中。HashSet 通常用于检查列表中是否存在元素。

**注意:**由于我们使用的是 HashSet，所以插入顺序不会被保留，每次运行代码时，我们都会得到一些不同的输出(元素的顺序会有所不同)。所以如果我们想在插入时保持元素的顺序，那么我们应该使用[链接 HashSet。](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/)

基本上有两种方法从集合中移除重复条目:

1.  使用 HashSet
2.  使用 linkedhashset

现在让我们来看看使用 java 程序通过逐个使用这两种方法来删除重复条目的实现:-

### 1.使用 HashSet

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to remove the duplicate entries from
// collection using HashSet

import java.util.ArrayList;
import java.util.Collection;
import java.util.HashSet;

class GFG {
    public static void main(String[] args)
    {
        // making the collection object
        Collection<String> collection = new ArrayList<>();

        // adding the elements to the collection
        collection.add("Geeks");
        collection.add("For");
        collection.add("Geeks");
        collection.add("Internship");
        collection.add("Internship");
        collection.add("2021");
        collection.add("2021");

        // Displaying the collection elements
        System.out.println(
            "Displaying the initial collection\n");
        System.out.println(collection);

        // HashSEt for deleting duplicate entries
        // in the collection by passing collection
        // in the constructor of the HashSet
        HashSet<String> hashSet = new HashSet<>(collection);

        // Displaying the HashSet
        System.out.println("\nDisplaying the HashSet\n");
        System.out.println(hashSet);

        // clearing all the elements of the collection
        collection.clear();

        // adding all the elements back
        // to the collection from HashSet
        collection.addAll(hashSet);

        // Displaying the collection
        System.out.println(
            "\nDisplaying the collection after deleting duplicates entries\n");
        System.out.println(collection);
    }
}
```

**输出:**

> 显示初始集合
> 
> 【极客，为，极客，实习，实习，2021，2021】
> 
> 显示哈希集
> 
> [极客们，2021 年，实习]
> 
> 删除重复条目后显示集合
> 
> [极客们，2021 年，实习]

### **2。使用链接哈希集**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to remove the duplicate entries from
// collection using LinkedHashSet

import java.util.ArrayList;
import java.util.Collection;
import java.util.LinkedHashSet;

class GFG {
    public static void main(String[] args)
    {
        // making the collection object
        Collection<String> collection = new ArrayList<>();

        // adding the elements to the collection
        collection.add("Geeks");
        collection.add("For");
        collection.add("Geeks");
        collection.add("Internship");
        collection.add("Internship");
        collection.add("2021");
        collection.add("2021");

        // Displaying the collection elements
        System.out.println(
            "Displaying the initial collection\n");
        System.out.println(collection);

        // LinkedHashSet for deleting duplicate entries
        // in the collection by passing collection
        // in the constructor of the HashSet
        LinkedHashSet<String> hashSet
            = new LinkedHashSet<>(collection);

        // Displaying the HashSet
        System.out.println("\nDisplaying the HashSet\n");
        System.out.println(hashSet);

        // clearing all the elements of the collection
        collection.clear();

        // adding all the elements back
        // to the collection from HashSet
        collection.addAll(hashSet);

        // Displaying the collection
        System.out.println(
            "\nDisplaying the collection after deleting duplicates entries\n");
        System.out.println(collection);
    }
}
```

**输出:**

> 显示初始集合
> 
> 【极客，为，极客，实习，实习，2021，2021】
> 
> 显示哈希集
> 
> [极客，供，实习，2021]
> 
> 删除重复条目后显示集合
> 
> [极客，供，实习，2021]