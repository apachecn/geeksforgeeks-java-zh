# 在 Java 9 中创建不可变集的工厂方法

> 原文:[https://www . geeksforgeeks . org/factory-method-create-incremental-set-Java-9/](https://www.geeksforgeeks.org/factory-method-create-immutable-set-java-9/)

Java 9 发布于 2017 年 3 月左右，请安装 jdk 9，这将有助于理解本文中使用的代码。在 Java 9 中，Java 语言增加了一些特性，不可变集合的工厂方法就是其中之一。
那我们开始吧！

**不变集的特征:**

*   顾名思义，这些集合是不可变的。
*   如果尝试添加、删除和更新集合中的元素，我们将获得不支持操作例外。
*   不可变集也不允许空元素。
*   如果试图创建一个包含空元素的不可变集合，我们将会遇到空指针异常。如果试图在集合中添加空元素，我们将会遇到 UnsupportedOperationException。

**在 java 8 中创建不可变集** 

在 java 8 中，为了创建不可变集，我们使用了 Java . util . collections . unmodifielableset(Set Set Set)方法。此方法返回指定集合的不可修改视图。该方法允许模块向用户提供对内部集合的“只读”访问。

```java
Syntax: public static  Set unmodifiableSet(Set set)
Returns: an unmodifiable view of the specified set.
Exception: NA

```

java 8 中不可变空集和非空集的 Java 代码:

```java
// Java code illustrating immutable set in java 8
import java.util.*;
class GfG
{
    public static void main(String args[])
    {
        // creating empty set
        Set<String> s1 = new HashSet<String>();
        Set<String> us1 = Collections.unmodifiableSet(s1);

        // creating non-empty set
        Set<String> s2 = new HashSet<String>();
        s2.add("contribute.geeksforgeeks.org");
        Set us2 = Collections.unmodifiableSet(s2);

        System.out.println(us1);
        System.out.println(us2);
    }
}
```

输出:

```java
[]
[contribute.geeksforgeeks.org]

```

现在让我们尝试在这些不可变集合中添加元素:

```java
// Java code illustrating immutable set in java 8
import java.util.*;

class GfG
{
    public static void main(String args[])
    {
        // creating empty set and unmodifiable set
        HashSet<String> s1 = new HashSet<String>();
        Set<String> us1  = Collections.unmodifiableSet(s1);

        // creating non-empty set and unmodifiable set
        HashSet<String> s2 = new HashSet<String>();
        s2.add("contribute.geeksforgeeks.org");
        Set<String> us2 = Collections.unmodifiableSet(s2);

        // try adding new element
        us1.add("gfg");
        us2.add("ide.geeksforgeeks");
    }
}
```

上面的代码会产生异常，因为我们试图在不可变集合中添加元素。

```java
Runtime Error : Exception in thread "main" 
java.lang.UnsupportedOperationException
at java.util.Collections$UnmodifiableCollection.add(Collections.java:1055)
at ImmutableListDemo.main(File.java:16)

```

**在 java 9 中创建不可变集** 

为了在 java 9 中创建不可变集，我们使用了()方法的**。
用 java 9 创建不可变集的 Java 代码:**

```java
// Java code illustrating of() method
import java.util.Set;

class GfG
{
    public static void main(String args[])
    {
        // empty immutable set
        Set<String> is1 = Set.of("ide", "code", "practice");

        System.out.println(is1);
    }
}
```

输出:

```java
[ide.code.practice]

```

现在让我们尝试在这些不可变集合中添加元素:

```java
// Java code illustrating of() method
import java.util.*;

import com.google.common.collect.ImmutableSet;
class GfG
{
    public static void main(String args[])
    {
        // empty immutable set
        Set<>String is1 = Set.of();

        // non-empty immuttable set
        Set<String> is2 = Set.of("ide", "contribute", "support");

        // Adding an element throws exception
        is1.add(null);
        is2.add("set");             
    }
}
```

```java
Exception in thread "main" java.lang.UnsupportedOperationException
    at com.google.common.collect.ImmutableCollection.add(ImmutableCollection.java:218)
    at ImmutableListDemo.main(Main.java:16)
```

本文由**阿比舍克·维尔马**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。