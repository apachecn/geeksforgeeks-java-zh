# Java 中的 NavigableSet subSet()方法

> 原文:[https://www . geesforgeks . org/navigableset-subset-method-in-Java/](https://www.geeksforgeeks.org/navigableset-subset-method-in-java/)

Java 中[navigatableset 接口的 headSet()方法用于返回该集合中元素范围从*到*到*再到*的部分的视图。](https://www.geeksforgeeks.org/navigableset-java-examples/)

[*   If fromElement and toElement are equal, the returned collection is empty unless both fromInclusive and toInclusive are true.*   The returned collection of is supported by this collection, so the changes in the returned collection are reflected in this collection and vice versa.*   The returned collection supports all optional collection operations supported by the collection.](https://www.geeksforgeeks.org/navigableset-java-examples/)

**注意**:返回的集合将在试图插入其范围之外的元素时抛出一个 IllegalArgumentException。

**语法** :

```java
NavigableSet<E> subSet( E fromElement,
                       boolean fromInclusive,
                       E toElement,
                       boolean toInclusive);

```

其中，E 是此 Set 容器维护的元素类型。

**参数**:该函数接受 4 个参数，解释如下:

*   **From Element** : This is a mandatory parameter, which specifies the low-end point of the return set.
*   **From inclusive** : this is an optional parameter, which is of Boolean type. If set to true, the low point will be included in the returned view, otherwise it will not be included.
*   [T0】 to element :his is a required option, which specifies the high-end point of the return set.
*   **to include** : this is an optional parameter, which is of Boolean type. If set to true, the low point will be included in the returned view, otherwise it will not be included.

**返回值**:返回该集合中元素范围为从元素到元素的部分的视图。

下面的程序说明了 Java 中的 subSet()方法:

**程序 1** :带整数元素的导航集。

```java
// A Java program to demonstrate
// subSet() method of NavigableSet

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

        System.out.println("Map with key-value between the given argument : "
                                                           + ns.subSet(1, 6));

        System.out.println("Map with key-value between the given argument : "
                                                           + ns.subSet(2, 6));
    }
}
```

**输出:**

```java
Map with key-value between the given argument : [1, 2, 3, 4, 5]
Map with key-value between the given argument : [2, 3, 4, 5]

```

**程序 2:** 带字符串元素的导航集。

```java
// A Java program to demonstrate
// subSet() method of NavigableSet

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

        System.out.println("Map with key-value between the given range : " 
                                                   + ns.subSet("B", "G"));
    }
}
```

**输出:**

```java
Map with key-value between the given range : [B, C, D, E, F]

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/util/naviableset . html # subSet(E，E)](https://docs.oracle.com/javase/10/docs/api/java/util/NavigableSet.html#subSet(E, E))