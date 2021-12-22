# Java 中的不可变集

> 原文:[https://www.geeksforgeeks.org/immutable-set-in-java/](https://www.geeksforgeeks.org/immutable-set-in-java/)

*   顾名思义，这些集合是不可变的。
*   如果尝试添加、删除和更新集合中的元素，我们将获得不支持操作例外。
*   不变集也不允许空元素。
*   如果试图用空元素创建一个不可替换的集合，我们将得到一个空指针异常。如果试图在集合中添加空元素，我们将会遇到 UnsupportedOperationException。
*   任何不可变集合(集合、映射、列表)的一个优点是线程安全。这些是自动线程安全的，因为它们是不可变的。
*   请注意，它是一个不可变的集合，而不是不可变对象的集合，因此可以修改其中的对象。

**在 Java 中创建一个不变的数据集**

*   **Using copyOf() method in [Guava](https://www.geeksforgeeks.org/guava-library-java/)** We use an existing [Set](https://www.geeksforgeeks.org/set-in-java/) to create an ImmutableSet.

    ```java
    // Creating an immutable set using copyOf()
    import java.util.*;
    import com.google.common.collect.ImmutableSet;
    import java.io.*;

    class GfG
    {
        public static void main(String args[])
        {
            // creating empty set
            Set<String> s = new HashSet<String>();
            s.add("GeeksforGeeks");
            s.add("Practice");

            // An immutable copy of s
            Set<String> is  = ImmutableSet.copyOf(s);

            System.out.println(is);
        }
    }
    ```

    输出:

    ```java
    [GeeksforGeeks, Practice]
    ```

*   **Using Of() method in Guava**

    ```java
    // Java code illustrating of() method to
    // create a ImmutableSet
    import java.util.*;
    import com.google.common.collect.ImmutableSet;

    class GfG
    {
        public static void main(String args[])
        {          
            // non-empty immutable set
            ImmutableSet<String> is = 
                     ImmutableSet.of("ide", "code");

            // Lets try adding element in these set
            System.out.println(is);             
        }
    }
    ```

    输出:

    ```java
    [ide, code]
    ```

*   **使用 [Java 9 Factory Of()方法](https://www.geeksforgeeks.org/factory-method-create-immutable-set-java-9/)**
    在 Java 中，如果我们使用 with Set、Map 或 List，则会创建一个不可变集。

```java
// Java code illustrating of() method to
// create a ImmutableSet
import java.util.*;
import com.google.common.collect.ImmutableSet;

class GfG
{
    public static void main(String args[])
    {          
        // non-empty immutable set
        Set<String> is = Set.of("ide", "code");

        // Let's print the set
        System.out.println(is);             
    }
}
```

输出:

```java
[ide, code]
```

**如果我们试图改变一个不变的集合呢？**
它抛出不支持操作异常

```java
// Java code illustrating of() method
import java.util.*;

class GfG
{
    public static void main(String args[])
    {
        // empty immutable set
        Set<String> is1 = Set.of();

        // non-empty immutable set
        Set is2 = Set.of("ide", "contribute", "support");

        // Lets try adding element in these set
        is1.add(null);
        is2.add("set");             
    }
}
```

输出:

```java
Exception in thread "main" java.lang.UnsupportedOperationException
    at com.google.common.collect.ImmutableCollection.add(ImmutableCollection.java:218)
    at ImmutableListDemo.main(Main.java:16)
```

**与 Collections.unmodifiableSet()有何不同？**
collections . unmodifielableset 在相同的现有集合周围创建一个包装，这样包装就不能用来修改它。然而，我们仍然可以改变原来的设置。

```java
// Java program to demonstrate that a set created using
// Collections.unmodifiableSet() can be modified indirectly.
import java.io.*;
import java.util.*;

class GFG {
public
    static void main(String[] args)
    {
        Set<String> s = new HashSet<String>();
        s.add("Geeks");
        Set<String> us = Collections.unmodifiableSet(s);

        // We change s and the changes reflect in us.
        s.add("Practice");
        s.add("Contribute");
        System.out.println(us);
    }
}
```

**Output:**

```java
[Geeks, Practice, Contribute]

```

如果我们从现有的集合中创建一个不可变集合并改变现有的集合，那么不可变集合不会改变，因为会创建一个副本。

```java
// Creating an immutable set using copyOf()
// and modifying original set.
import java.util.*;
import com.google.common.collect.ImmutableSet;
import java.io.*;

class GfG
{
    public static void main(String args[])
    {
        // creating empty set
        Set<String> s = new HashSet<String>();
        s.add("GeeksforGeeks");
        s.add("Practice");

        // An immutable copy of s
        Set<String> is  = ImmutableSet.copyOf(s);

        // Now if we change 's', 'is' does not change
        s.add("Contribute");
        System.out.println(is);
    }
}
```

输出:

```java
[GeeksforGeeks, Practice]
```

**参考**
[创建不可变列表、集合和地图](https://docs.oracle.com/javase/9/core/creating-immutable-lists-sets-and-maps.htm#JSCOR-GUID-DD066F67-9C9B-444E-A3CB-820503735951)