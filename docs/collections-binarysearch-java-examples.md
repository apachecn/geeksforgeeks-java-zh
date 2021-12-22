# Java 中的 Collections.binarySearch()带示例

> 原文:[https://www . geesforgeks . org/collections-binary search-Java-examples/](https://www.geeksforgeeks.org/collections-binarysearch-java-examples/)

java.util.Collections . BinarySearch()方法是一个 Java . util . collections 类方法，返回对象在排序列表中的位置。

```
// Returns index of key in sorted list sorted in
// ascending order
public static int binarySearch(List slist, T key)

// Returns index of key in sorted list sorted in
// order defined by Comparator c.
public static int binarySearch(List slist, T key, Comparator c)

If key is not present, the it returns "(-(insertion point) - 1)". 
The insertion point is defined as the point at which the key 
would be inserted into the list.
```

如果使用指定的比较器无法比较列表的元素，或者搜索关键字无法与元素进行比较，则该方法将引发 **ClassCastException** 。
**在按升序排序的列表中搜索 int 键:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate working of Collections.
// binarySearch()
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class GFG {
    public static void main(String[] args)
    {
        List<Integer> al = new ArrayList<Integer>();
        al.add(1);
        al.add(2);
        al.add(3);
        al.add(10);
        al.add(20);

        // 10 is present at index 3.
        int index = Collections.binarySearch(al, 10);
        System.out.println(index);

        // 13 is not present. 13 would have been inserted
        // at position 4\. So the function returns (-4-1)
        // which is -5.
        index = Collections.binarySearch(al, 13);
        System.out.println(index);
    }
}
```

输出:

```
3
-5
```

**在降序排列的列表中搜索 int 键。**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate working of Collections.
// binarySearch() in an array sorted in descending order.
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public class GFG {
    public static void main(String[] args)
    {
        List<Integer> al = new ArrayList<Integer>();
        al.add(100);
        al.add(50);
        al.add(30);
        al.add(10);
        al.add(2);

        // The last parameter specifies the comparator
        // method used for sorting.
        int index = Collections.binarySearch(
            al, 50, Collections.reverseOrder());

        System.out.println("Found at index " + index);
    }
}
```

输出:

```
Found at index 1
```

**在用户定义的类对象列表中搜索:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate working of Collections.
// binarySearch() in a list of user defined objects
import java.util.*;

class Binarysearch {
    public static void main(String[] args)
    {
        // Create a list
        List<Domain> l = new ArrayList<Domain>();
        l.add(new Domain(10, "quiz.geeksforgeeks.org"));
        l.add(new Domain(20, "practice.geeksforgeeks.org"));
        l.add(new Domain(30, "code.geeksforgeeks.org"));
        l.add(new Domain(40, "www.geeksforgeeks.org"));

        Comparator<Domain> c = new Comparator<Domain>() {
            public int compare(Domain u1, Domain u2)
            {
                return u1.getId().compareTo(u2.getId());
            }
        };

        // Searching a domain with key value 10\. To search
        // we create an object of domain with key 10.
        int index = Collections.binarySearch(
            l, new Domain(10, null), c);
        System.out.println("Found at index  " + index);

        // Searching an item with key 5
        index = Collections.binarySearch(
            l, new Domain(5, null), c);
        System.out.println(index);
    }
}

// A user-defined class to store domains with id and url
class Domain {
    private int id;
    private String url;

    // Constructor
    public Domain(int id, String url)
    {
        this.id = id;
        this.url = url;
    }

    public Integer getId() { return Integer.valueOf(id); }
}
```

输出:

```
0
-1
```

[**阵**](https://www.geeksforgeeks.org/array-class-in-java/) **。binary search()vs collections . binary search()**
arrays . binary search()适用于也可以是原始数据类型的数组。[收藏](https://www.geeksforgeeks.org/collections-in-java-2/)。binarysearch()适用于对象集合，如[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)和[链接列表](http://geeksquiz.com/linked-list-in-java/)。
**要点:**

*   如果输入列表没有排序，结果是未定义的。
*   如果有重复，不能保证会找到哪一个。
*   对于像 ArrayList 这样的“随机访问”列表，该方法在 log(n)时间内运行。如果指定的列表没有实现 RandomAccess 接口并且很大，这个方法将执行一个基于迭代器的二分搜索法，执行 O(n)个链接遍历和 O(log n)个元素比较。

**参考:**
[https://docs . Oracle . com/javase/7/docs/API/Java/util/collections . html # binary search(Java . util . list，%20T)](https://docs.oracle.com/javase/7/docs/api/java/util/Collections.html#binarySearch(java.util.List,%20T))
本文由 **Mohit Gupta** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
发现有不正确的地方请写评论，或者想分享更多以上讨论话题的信息