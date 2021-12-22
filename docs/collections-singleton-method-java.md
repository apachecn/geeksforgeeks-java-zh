# Java 中的 Collections.singleton()方法，示例

> 原文:[https://www . geesforgeks . org/collections-singleton-method-Java/](https://www.geeksforgeeks.org/collections-singleton-method-java/)

**Java . util . collections . singleton()**方法是一个 [java.util.Collections 类](https://www.geeksforgeeks.org/java/#CollectionsClass)方法。它在单个指定的元素上创建一个不可变的集合。此方法的一个应用是从集合中移除一个元素，如列表和集合。

**语法:**

```
public static  Set singleton(T obj)
and
public static  List singletonList(T obj)
Parameters: obj : the sole object to be stored in
                  the returned list or set.
Return: an immutable list/set containing only the 
       specified object.
```

```
Example:
myList : {"Geeks", "code", "Practice", " Error",  "Java", 
          "Class", "Error", "Practice", "Java" }

To remove all "Error" elements from our list at once, we use 
singleton() method 
myList.removeAll(Collections.singleton("Error"));

After using singleton() and removeAll, we get following.
{"Geeks", "code", "Practice", "Java", "Class", "Practice", "Java" }
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// working of singleton()
import java.util.*;

class GFG {
    public static void main(String args[])
    {
        String[] geekslist = { "1", "2", "4", "2", "1", "2",
                               "3", "1", "3", "4", "3", "3" };

        // Creating a list and removing
        // elements without use of singleton()
        List geekslist1 = new ArrayList(Arrays.asList(geekslist));
        System.out.println("Original geeklist1: " + geekslist1);

        geekslist1.remove("1");
        System.out.println("geekslist1 after removal of 1 without"
                           + " singleton " + geekslist1);
        geekslist1.remove("1");
        System.out.println("geekslist1 after removal of 1 without"
                           + " singleton " + geekslist1);
        geekslist1.remove("2");
        System.out.println("geekslist1 after removal of 2 without"
                           + " singleton " + geekslist1);

        /* Creating another list and removing
    its elements using singleton() method */
        List geekslist2 = new ArrayList(Arrays.asList(geekslist));
        System.out.println("\nOriginal geeklist2: " + geekslist2);

        // Selectively delete "1" from
        // all it's occurrences
        geekslist2.removeAll(Collections.singleton("1"));
        System.out.println("geekslist2 after removal of 1 with "
                           + "singleton:" + geekslist2);

        // Selectively delete "4" from
        // all it's occurrences
        geekslist2.removeAll(Collections.singleton("4"));
        System.out.println("geekslist2 after removal of 4 with "
                           + "singleton:" + geekslist2);

        // Selectively delete "3" from
        // all it's occurrences
        geekslist2.removeAll(Collections.singleton("3"));
        System.out.println("geekslist2 after removal of 3 with"
                           + " singleton: " + geekslist2);
    }
}
```

**输出:**

```
Original geeklist1                 [1, 2, 4, 2, 1, 2, 3, 1, 3, 4, 3, 3]
geekslist1 after removal of 1 without singleton [2, 4, 2, 1, 2, 3, 1, 3, 4, 3, 3]
geekslist1 after removal of 1 without singleton [2, 4, 2, 2, 3, 1, 3, 4, 3, 3]
geekslist1 after removal of 2 without singleton [4, 2, 2, 3, 1, 3, 4, 3, 3]

Original geeklist2                 [1, 2, 4, 2, 1, 2, 3, 1, 3, 4, 3, 3]
geekslist2 after removal of 1 with singleton     [2, 4, 2, 2, 3, 3, 4, 3, 3]
geekslist2 after removal of 4 with singleton     [2, 2, 2, 3, 3, 3, 3]
geekslist2 after removal of 3 with singleton     [2, 2, 2]
```

本文由**莫希特·古普塔**供稿。如果你喜欢极客博客并想投稿，你也可以用 write.geeksforgeeks.org 写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如发现任何不正确的地方，请写评论，或者您想分享更多关于上述话题的信息