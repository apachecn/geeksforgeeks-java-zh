# 在 Java 9 中创建不可变映射的工厂方法

> 原文:[https://www . geesforgeks . org/factory-method-create-improved-map-Java-9/](https://www.geeksforgeeks.org/factory-method-create-immutable-map-java-9/)

在 Java 9 中，有一些特性是用 Java 语言添加的，不可变映射的工厂方法就是其中之一。
**不变地图的特点:**

*   顾名思义，这些地图是不可变的。
*   如果尝试在地图中添加、删除和更新元素，我们将获得不支持的操作例外。
*   不可变映射也不允许空元素。
*   如果试图创建一个包含空元素的不可变映射，我们将会遇到空指针异常。如果试图在映射中添加空元素，我们将会遇到 UnsupportedOperationException。

**在 Java 8 中创建不可变地图**

为了在 java 8 中创建不可变的映射，我们使用了 Java . util . unmodifielemap(Map Map)方法。**不可修改地图(Map map):** 此方法返回指定地图的不可修改视图。该方法允许模块向用户提供对内部地图的“只读”访问。

```
Syntax: public static  Map unmodifiableMap(Map map)
Returns: an unmodifiable view of the specified map.
Exception: NA

```

不可变空和非空映射的 Java 代码:

```
// Java code illustrating immutable map in java 8
import java.util.*;
class ImmutableListDemo
{
    public static void main(String args[])
    {
        // empty map
        Map<Integer, String> empty = new HashMap();
        Map immutable1 = Collections.unmodifiableMap(empty);

        // non-empty map
        Map<Integer, String> non_empty = new HashMap();
        non_empty.put(1, "ide");

        Map immutable2 = Collections.unmodifiableMap(non_empty);

        // adding key-value pair in these immutable map
        immutable1.put(1,"gfg");
        immutable2.put(2,"quiz");

    }
}
```

上面的代码将生成异常，因为我们试图在不可变映射中添加键值对。

```
Runtime Error : Exception in thread "main" 
java.lang.UnsupportedOperationException
at java.util.Collections$UnmodifiableMap.put(Collections.java:1457)
at ImmutableListDemo.main(File.java:17)

```

**在 java 9 中创建不可变地图**

为了在 java 9 中创建不可变的地图，我们使用了()的**和**的**方法。
用 java 9 创建不可变映射的 Java 代码:**

```
// Java code illustrating of() method
import java.util.*;
class ImmutableListDemo
{
    public static void main(String args[])
    {
        // empty immutable map
        Map<Integer, String> immutable1 = Map.of();

        // non-empty immutable map
        Map<Integer, String> immutable2 = Map.of(1, "ide",2, "quiz");

        // adding key-value pair in these immutable map
        immutable1.put(1,"gfg");
        immutable2.put(3,"contribute");

    }
}
```

运行上述代码后，我们将出现 UnsupportedOperationException。
Java 9 中使用 Map.ofEntries()方法创建不可变映射的 Java 代码:

```
// Java code illustrating ofEntries method
import java.util.*;
import java.util.Map.Entry;
class ImmutableListDemo
{
    public static void main(String args[])
    {
        // empty immutable map
        Map<Integer, String> immutable = Map.ofEntries();

        // non-empty immutable map
        Map.Entry<Integer, String> entry1 = Map.entry(1, "gfg");
        Map.Entry<Integer, String> entry2 = Map.entry(2, "contribute");

        Map<Integer, String> immubatleMap = Map.ofEntries(entry1,
                         entry2);     
    }
}
```

所以 of()和 ofEntries()是 java 9 中用来创建不可变映射的方法。

本文由**阿比舍克·维尔马**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。