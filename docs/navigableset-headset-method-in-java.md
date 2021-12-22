# Java 中的 NavigableSet headSet()方法

> 原文:[https://www . geesforgeks . org/navigableset-headset-in-method-in-Java/](https://www.geeksforgeeks.org/navigableset-headset-method-in-java/)

Java 中[navigatableset 接口的 headSet()方法用于返回该集合中元素小于(或等于，如果包含为真)toElement 的部分的视图。](https://www.geeksforgeeks.org/navigableset-java-examples/)

[*   The returned collection of is supported by this collection, so the changes in the returned collection are reflected in this collection and vice versa.*   The returned collection supports all optional collection operations supported by the collection.](https://www.geeksforgeeks.org/navigableset-java-examples/)

**注意**:返回的集合将在试图插入其范围之外的元素时抛出一个 IllegalArgumentException。

**语法** :

```java
NavigableSet<E> headSet(E toElement,
                        boolean inclusive)

```

其中，E 是此 Set 容器维护的元素类型。

**参数**:该函数有两个参数:

*   **toelement** –Returns the high point of the set.
*   **(inclusive)** –If the high-end point is included in the return view.

中，则为 true

**返回值**:返回该集合中元素小于(或等于，如果包含为真)元素的部分的视图。

下面的程序说明了 Java 中的 HeAd()方法:

**程序 1** :带整数元素的导航集。

```java
// A Java program to demonstrate
// headSet() method of NavigableSet

import java.util.NavigableSet;
import java.util.TreeSet;

public class GFG {
    public static void main(String[] args)
    {
        NavigableSet<Integer> ns = new TreeSet<>();
        ns.add(0);
        ns.add(1);
        ns.add(2);
        ns.add(3);
        ns.add(4);
        ns.add(5);
        ns.add(6);

        System.out.println("Map with key-value less than "+
                        "given argument : " + ns.headSet(6));

        System.out.println("Map with key-value less than or" + 
          " equal to  given argument : " + ns.headSet(6, true));
    }
}
```

**输出:**

```java
Map with key-value less than given argument : [0, 1, 2, 3, 4, 5]
Map with key-value less than or equal to  given argument : [0, 1, 2, 3, 4, 5, 6]

```

**程序 2:** 带字符串元素的导航集。

```java
// A Java program to demonstrate
// headSet?() method of NavigableSet

import java.util.NavigableSet;
import java.util.TreeSet;

public class GFG {
    public static void main(String[] args)
    {
        NavigableSet<String> ns = new TreeSet<>();
        ns.add("A");
        ns.add("B");
        ns.add("C");
        ns.add("D");
        ns.add("E");
        ns.add("F");
        ns.add("G");

        System.out.println("Map with key-value less than"+
                    " given argument : " + ns.headSet("F"));

        System.out.println("Map with key-value less than "+
           "or equal to given argument : " + ns.headSet("F"));
    }
}
```

**输出:**

```java
Map with key-value less than given argument : [A, B, C, D, E]
Map with key-value less than or equal to given argument : [A, B, C, D, E]

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/util/naviableset . html # headSet(E)](https://docs.oracle.com/javase/10/docs/api/java/util/NavigableSet.html#headSet(E))