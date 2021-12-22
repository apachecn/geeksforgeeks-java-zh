# Java 中的 NavigableSet pollFirst()方法

> 原文:[https://www . geesforgeks . org/navigableset-poll first-method-in-Java/](https://www.geeksforgeeks.org/navigableset-pollfirst-method-in-java/)

Java 中[navigatableset 接口的 pollFirst()方法用于检索并移除第一个(最低的)元素，如果该集合为空，则返回 null。](https://www.geeksforgeeks.org/navigableset-java-examples/)

**语法** :

```
E pollFirst()

```

其中，E 是此 Set 容器维护的元素类型。

**参数**:本功能不接受任何参数。

**返回值**:如果该集合为空，则返回空。

下面的程序说明了 Java 中的 pollFirst()方法:

**程序 1** :带整数元素的导航集。

```
// A Java program to demonstrate
// pollFirst() method of NavigableSet

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

        System.out.println("First lowest element removed is : " 
                                              + ns.pollFirst());
    }
}
```

**输出:**

```
First lowest element removed is : 0

```

**程序 2:** 带字符串元素的导航集。

```
// A Java program to demonstrate
// pollFirst() method of NavigableSet

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

        System.out.println("First lowest element removed is : " 
                                              + ns.pollFirst());
    }
}
```

**输出:**

```
First lowest element removed is : A

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/util/navigableset . html # pollsfirst(E)](https://docs.oracle.com/javase/10/docs/api/java/util/NavigableSet.html#pollFirst(E))