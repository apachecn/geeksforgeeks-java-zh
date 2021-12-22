# Java 中的 NavigableSet descendingIterator()方法

> 原文:[https://www . geesforgeks . org/navigableset-dependingiterator-method-in-Java/](https://www.geeksforgeeks.org/navigableset-descendingiterator-method-in-java/)

Java 中[navigatable set 接口的 DecendingTerrar()方法用于以降序返回该集合中元素的迭代器。这个迭代器可以用来迭代集合的元素。](https://www.geeksforgeeks.org/navigableset-java-examples/)

这个集合返回的迭代器也相当于下行集合()。迭代器()。

**语法** :

```
Iterator<E> descendingIterator()

```

其中，E 是此 Set 容器维护的元素类型。

**参数**:本功能不接受任何参数。

**返回值**:以降序返回这个集合容器中包含的元素集合的迭代器。

下面的程序说明了 Java 中的 descendingIterator()方法:

**程序 1** :带整数元素的导航集。

```
// A Java program to demonstrate
// descendingIterator() method of NavigableSet

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

        Iterator<Integer> itr = ns.descendingIterator();

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
// A Java program to illustrate iterator()
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

        Iterator<String> itr = ns.descendingIterator();

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

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/util/navigatableset . html # dependingiterator()](https://docs.oracle.com/javase/10/docs/api/java/util/NavigableSet.html#descendingIterator())