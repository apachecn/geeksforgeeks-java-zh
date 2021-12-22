# 抽象集合在 Java 中添加()方法，示例

> 原文:[https://www . geesforgeks . org/abstract collection-add-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractcollection-add-method-in-java-with-examples/)

**[Java 抽象集合](https://www.geeksforgeeks.org/abstractcollection-in-java-with-examples/)** 中的 **add()** 方法用于将特定元素添加到集合中。只有当集合中不存在指定的元素时，此方法才会添加元素，否则如果集合中已经存在该元素，函数将返回 False。

**语法:**

```
AbstractCollection.add(Object element)
```

**参数:**参数**元素**属于对象类型，是指要添加到集合中的元素。

**返回值:**如果元素不在集合中，函数返回真；如果元素已经在集合中，函数返回假。

下面的程序说明了 AbstractCollection.add()方法:

**程序 1:** 将字符串元素添加到数组列表的集合中。

```
// Java code to illustrate add(Object o)

import java.util.*;
import java.util.AbstractCollection;

public class AbstractCollectionDemo {
    public static void main(String[] args)
    {

        // Create an empty collection
        AbstractCollection<Object>
            abs = new ArrayList<Object>();

        // Use add() method to add
        // elements in the collection
        abs.add("Welcome");
        abs.add("To");
        abs.add("Geeks");
        abs.add("4");
        abs.add("Geeks");

        // Displaying the Collection
        System.out.println("AbstractCollection: "
                           + abs);
    }
}
```

**Output:**

```
AbstractCollection: [Welcome, To, Geeks, 4, Geeks]

```

**程序 2:** 将整数元素添加到链表的集合中。

```
// Java code to illustrate add(Object o)

import java.util.*;
import java.util.AbstractCollection;

public class AbstractCollectionDemo {
    public static void main(String[] args)
    {

        // Create an empty collection
        AbstractCollection<Object>
            abs = new LinkedList<Object>();

        // Use add() method to add
        // elements in the collection
        abs.add(15);
        abs.add(20);
        abs.add(25);
        abs.add(30);
        abs.add(35);

        // Displaying the Collection
        System.out.println("AbstractCollection: "
                           + abs);
    }
}
```

**Output:**

```
AbstractCollection: [15, 20, 25, 30, 35]

```