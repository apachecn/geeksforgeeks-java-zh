# Java 中的 NavigableSet descendingSet()方法

> 原文:[https://www . geesforgeks . org/navigableset-dependingset-method-in-Java/](https://www.geeksforgeeks.org/navigableset-descendingset-method-in-java/)

Java 中[navigatable set 接口的 descendingSet()方法用于返回该集合中包含的元素的逆序视图。该集合支持降序集合，因此对该集合的任何更改都会反映在降序集合中，反之亦然。如果在对其他集合进行迭代的过程中修改了任何集合，则迭代的结果是未定义的。](https://www.geeksforgeeks.org/navigableset-java-examples/)

**语法** :

```
Iterator<E> descendingSet()

```

其中，E 是此 Set 容器维护的元素类型。

**参数**:本功能不接受任何参数。

**返回值**:返回该集合中包含的元素的逆序视图。

下面的程序说明了 Java 中的 descendingSet()方法:

**程序 1** :带整数元素的导航集。

```
// A Java program to demonstrate
// descendingSet() method of NavigableSet

import java.util.NavigableSet;
import java.util.TreeSet;
import java.util.*;

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

        NavigableSet new_ns = ns.descendingSet();

        Iterator itr = new_ns.iterator();

        // Iterate over the elements using itr
        while (itr.hasNext()) {
            System.out.println("Value: " + itr.next() + " ");
        }
    }
}
```

**输出:**

```
Value: 6 
Value: 5 
Value: 4 
Value: 3 
Value: 2 
Value: 1 
Value: 0

```

**程序 2:** 带字符串元素的导航集。

```
// A Java program to illustrate descendingSet()
// method of NavigableSet
import java.util.NavigableSet;
import java.util.TreeSet;
import java.util.*;

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

        NavigableSet new_ns = ns.descendingSet();

        Iterator itr = new_ns.iterator();

        // Iterate over the elements using itr
        while (itr.hasNext()) {
            System.out.println("Value: " + itr.next() + " ");
        }
    }
}
```

**输出:**

```
Value: G 
Value: F 
Value: E 
Value: D 
Value: C 
Value: B 
Value: A

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/util/navigableset . html # DecendingSet()](https://docs.oracle.com/javase/10/docs/api/java/util/NavigableSet.html#descendingSet())