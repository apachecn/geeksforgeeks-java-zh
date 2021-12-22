# 在 Java 中初始化 HashSet

> 原文:[https://www.geeksforgeeks.org/initializing-hashset-java/](https://www.geeksforgeeks.org/initializing-hashset-java/)

[用 Java 设置](https://www.geeksforgeeks.org/set-in-java/)是一个扩展 Collection 的接口。它是一个无序的对象集合，其中不能存储重复的值。
基本上，set 是由 [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 、 [LinkedHashSet](https://www.geeksforgeeks.org/linkedhashset-class-in-java-with-examples/) 或 [TreeSet](https://www.geeksforgeeks.org/treeset-class-java-examples/) 实现的(排序表示)。
Set 有各种添加、清除、大小等方法来增强这个界面的使用。

**方法 1:使用构造函数:**
在这个方法中，我们首先创建一个数组，然后将其转换为一个列表，然后将其传递给接受另一个集合的 HashSet 构造函数。
集合的整数元素按排序顺序打印。

```java
// Java code for initializing a Set
import java.util.*;
public class Set_example {
    public static void main(String[] args)
    {
        // creating and initializing an array (of non
        // primitive type)
        Integer arr[] = { 5, 6, 7, 8, 1, 2, 3, 4, 3 };

        // Set demonstration using HashSet Constructor
        Set<Integer> set = new HashSet<>(Arrays.asList(arr));

        // Duplicate elements are not printed in a set.
        System.out.println(set);
    }
}
```

**使用集合的方法 2:**
集合类由几个对集合进行操作的方法组成。
a)**collection . addall()**:将所有指定的元素添加到指定类型的指定集合中。
b)**collections . unmodifielableset()**:添加元素并返回指定集合的不可修改视图。

```java
// Java code for initializing a Set
import java.util.*;
public class Set_example {
    public static void main(String[] args)
    {
        // creating and initializing an array (of non 
        // primitive type)
        Integer arr[] = { 5, 6, 7, 8, 1, 2, 3, 4, 3 };

        // Set deonstration using Collections.addAll
        Set<Integer> set = Collections.<Integer> emptySet();
        Collections.addAll(set =
                    new HashSet<Integer>(Arrays.asList(arr)));

        // initializing set using Collections.unmodifiable set
        Set<Integer> set2 = 
             Collections.unmodifiableSet(new HashSet<Integer>
                                         (Arrays.asList(arr)));

        // Duplicate elements are not printed in a set.
        System.out.println(set);
    }
}
```

**方法三:使用。添加()每次**
创建一个集合并使用。add()方法我们将元素添加到集合中

```java
// Java code for initializing a Set
import java.util.*;
public class Set_example {

    public static void main(String[] args)
    {
        // Create a set
        Set<Integer> set = new HashSet<Integer>();

        // Add some elements to the set
        set.add(1);
        set.add(2);
        set.add(3);
        set.add(4);
        set.add(5);
        set.add(6);
        set.add(7);
        set.add(8);

        // Adding a duplicate element has no effect
        set.add(3);
        System.out.println(set);
    }
}
```

输出:

```java
[1, 2, 3, 4, 5, 6, 7, 8]

```

本文由**尼基塔·蒂瓦里**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。