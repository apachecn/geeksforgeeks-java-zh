# Java 中 IdentityHashMap、WeakHashMap 和 EnumMap 的区别

> 原文:[https://www . geesforgeks . org/difference-identity hashmap-weakashmap-和-enummap-in-java/](https://www.geeksforgeeks.org/difference-between-identityhashmap-weakhashmap-and-enummap-in-java/)

IdentityHashMap、WeakHashMap 和 EnumMap 都是 java 集合中实现 [Map](https://www.geeksforgeeks.org/map-interface-java-examples/) 接口的类。但是他们之间几乎没有什么区别。

**1。**[**identity hashmap**](https://www.geeksforgeeks.org/identityhashmap-class-java/)**:**identity hashmap 实现[映射](https://www.geeksforgeeks.org/map-interface-java-examples/)界面。在比较键(和值)时，它遵循引用相等代替对象相等。当用户需要通过引用比较对象时，使用此类。它不是同步的，必须在外部同步。这个类中的迭代器是快速失败的，在迭代时抛出**ConcurrentModificationException**试图修改。

**身份工作哈希表:**

## 爪哇

```java
// Java program to illustrate the
// working of IdentityHashmap

import java.util.*;

public class IteratingIdentityHashMap {

    public static void main(String[] args)
    {

        // Creating an empty IdentityHashMap
        IdentityHashMap<Integer, String> ihmap
            = new IdentityHashMap<Integer, String>();

        // Mapping string values to int keys
        ihmap.put(10, "Geeks");
        ihmap.put(20, "4");
        ihmap.put(30, "Geeks");
        ihmap.put(40, "Welcomes");
        ihmap.put(50, "You");

        // Displaying the size of IdentityHashMap
        System.out.println("IdentityHashMap size : "
                           + ihmap.size());

        // Displaying the IdentityHashMap
        System.out.println("Initial identity hash map: "
                           + ihmap);

        // Create an Iterator over the
        // IdentityHashMap
        Iterator<IdentityHashMap.Entry<Integer, String> >
            itr = ihmap.entrySet().iterator();

        // The hasNext() method is used to check if there is
        // a next element The next() method is used to
        // retrieve the next element

        while (itr.hasNext())
        {
            IdentityHashMap.Entry<Integer, String> entry = itr.next();

            System.out.println("Key = " + entry.getKey()
                               + ", Value = "
                               + entry.getValue());
        }
    }
}
```

**输出**

```java
IdentityHashMap size : 5
Initial identity hash map: {10=Geeks, 40=Welcomes, 50=You, 30=Geeks, 20=4}
Key = 10, Value = Geeks
Key = 40, Value = Welcomes
Key = 50, Value = You
Key = 30, Value = Geeks
Key = 20, Value = 4
```