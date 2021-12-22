# 在 Java SE 9 中创建不可变列表的工厂方法

> 原文:[https://www . geeksforgeeks . org/factory-method-to-create-invoke-list-in-Java-se-9/](https://www.geeksforgeeks.org/factory-method-to-create-immutable-list-in-java-se-9/)

Java 9 大约在 2017 年 3 月发布，在 Java 9 中，有一些特性是用 Java 语言添加的，不可变列表的工厂方法就是其中之一。
**不变列表的特征:**

1.  顾名思义，这些列表是不可变的。
2.  如果试图添加、删除和更新列表中的元素，我们将会有一个不支持的操作例外。
3.  不可变列表也不允许空元素。
4.  如果试图创建一个包含空元素的不可变列表，我们将得到一个空指针异常。如果试图在列表中添加空元素，我们将会遇到 UnsupportedOperationException。

**在 Java 8 中创建不可变列表**

在 Java SE 8 中，为了在 java 8 中创建不可变列表，我们使用了 Java . util . collections . unmodifielablelist(List List List)方法. unmodifielablelist(List List List)。此方法返回指定列表的不可修改视图。该方法允许模块向用户提供对内部列表的“只读”访问。

```java
Syntax: public static  List unmodifiableList(List list)
Returns: an unmodifiable view of the specified list.
Exception: NA

```

java 8 中不可变空和非空列表的 Java 代码:

```java
// Java code illustrating
// creating of an 
// immutable list in Java 8
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;
class ImmutableListDemo
{
    public static void main(String args[])
    {
        // creating empty list
        List<String> gfg_empty = new ArrayList<String>();

        // making list immutable
        List empty_immutable1 
                = Collections.unmodifiableList(gfg_empty);

        // creating non-empty list
        List<String> gfg_non_empty = new ArrayList<String>();

        gfg_non_empty.add("write.geeksforgeeks.org");
        gfg_non_empty.add("www.geeksforgeeks.org");

        // making list immutable
        List empty_immutable2 
                = Collections.unmodifiableList(gfg_non_empty);

        System.out.println(empty_immutable1);
        System.out.println(empty_immutable2); 
    }
}
```

输出:

```java
[]
[write.geeksforgeeks.org, www.geeksforgeeks.org]

```

现在让我们尝试在不可变列表中添加元素

```java
// Java code illustrating
// an add operation 
// in immutable list in Java 8
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;
class ImmutableListDemo
{
    public static void main(String args[])
    {
        // creating empty list
        List<String> gfg_empty = new ArrayList<String>();

        // making list immutable
        List empty_immutable1 
                    = Collections.unmodifiableList(gfg_empty);

        // adding element in gfg_empty list
        empty_immutable1.add("ide.geeksforgeeks.org");

        // creating non-empty list
        List<String> gfg_non_empty = new ArrayList<String>();

        gfg_non_empty.add("write.geeksforgeeks.org");
        gfg_non_empty.add("www.geeksforgeeks.org");

        // making list immutable
        List empty_immutable2 
                    = Collections.unmodifiableList(gfg_non_empty);

        // adding element in gfg_non_empty list
        empty_immutable2.add("quiz.geeksforgeeks.org");

    }
}
```

例外:

```java
Runtime Error : Exception in thread "main" 
java.lang.UnsupportedOperationException
at java.util.Collections$UnmodifiableCollection.add(Collections.java:1055)
at ImmutableListDemo.main(File.java:15)

```

**在 Java 9 中创建不可变列表**

Java SE 9 在 List 接口中引入了几个方法来创建不可变列表。为了在 Java 9 中创建不可变列表，我们使用了()方法的**。
用 Java 9 创建不可变列表的 Java 代码:**

```java
// Java code illustrating
// creating immutable list
// using  of() method
import java.util.*;
class ImmutableListDemo
{
    public static void main(String args[])
    {
        // creating empty immutable list
        List<String> immutable = List.of();

        // creating non-empty immutable list
        List<String> immutable1 = List.of("contribute", "ide");

        System.out.println("empty immutable list: " + immutable);
        System.out.println("non-empty immutable list: " + immutable);

    }
}
```

输出:

```java
empty immutable list: []
non-empty immutable list: [contribute, ide]

```

让我们尝试在不可变列表中添加一些元素:

```java
// Java code illustrating add 
// operation on immutable list
import java.util.*;
class ImmutableListDemo
{
    public static void main(String args[])
    {
        // creating empty immutable list
        List<String> immutable = List.of();
        immutable.add(null);

        // creating non-empty immutable list
        List<String> immutable1 = List.of("contribute", "ide");
        immutable1.add("install jdk 9");

    }
}
```

运行上述代码后，您必须获得 UnsupportedOperationException。

本文由**阿比舍克·维尔马**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。