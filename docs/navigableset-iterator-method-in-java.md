# Java 中的 NavigableSet 迭代器()方法

> 原文:[https://www . geesforgeks . org/navigableset-iterator-method-in-Java/](https://www.geeksforgeeks.org/navigableset-iterator-method-in-java/)

Java 中[navigatableset 接口的迭代器()方法用于以升序返回该集合中元素的迭代器。这个迭代器可以用来迭代集合的元素。](https://www.geeksforgeeks.org/navigableset-java-examples/)

**语法** :

```java
Iterator<E> iterator()

```

其中，E 是此 Set 容器维护的元素类型。

**参数**:本功能不接受任何参数。

**返回值**:返回这个集合容器中包含的元素集合的迭代器。

下面的程序说明了 Java 中的迭代器()方法:

**程序 1** :带整数元素的导航集。

```java
// A Java program to demonstrate iterator()
// method of NavigableSet
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

        Iterator<Integer> itr = ns.iterator();

        // Iterate over the elements using itr
        while (itr.hasNext()) {
            System.out.println("Value: " + itr.next() + " ");
        }
    }
}
```

**输出:**

```java
Value: 0 
Value: 1 
Value: 2 
Value: 3 
Value: 4 
Value: 5 
Value: 6

```

**程序 2:** 带字符串元素的导航集。

```java
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

        Iterator<String> itr = ns.iterator();

        // Iterate over the elements using itr
        while (itr.hasNext()) {
            System.out.println("Value: " + itr.next() + " ");
        }
    }
}
```

**输出:**

```java
Value: A 
Value: B 
Value: C 
Value: D 
Value: E 
Value: F 
Value: G

```

**参考**:[https://docs . Oracle . com/javase/10/docs/API/Java/util/navigableset . html # iterator()](https://docs.oracle.com/javase/10/docs/api/java/util/NavigableSet.html#iterator())