# 在 Java 中逆向迭代树形图

> 原文:[https://www . geesforgeks . org/iterate-tree map-in-reverse-order-in-Java/](https://www.geeksforgeeks.org/iterate-treemap-in-reverse-order-in-java/)

Java 中的[树图](https://www.geeksforgeeks.org/treemap-in-java/)与[抽象图](https://www.geeksforgeeks.org/abstractmap-in-java/)类一起用于实现[图](https://www.geeksforgeeks.org/map-interface-java-examples/)接口和[导航地图](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/)。树形图根据其键的自然顺序进行排序。

有三种简单的方法可以在 Java 中以相反的顺序迭代 TreeMap:

1.  使用 [reverseOrder()](https://www.geeksforgeeks.org/collections-reverseorder-java-examples/) 方法
2.  使用[下降键集()](https://www.geeksforgeeks.org/treemap-descendingkeyset-method-in-java-with-examples/)方法
3.  使用[下降映射()](https://www.geeksforgeeks.org/treemap-descendingmap-method-in-java-with-examples/)方法

**方法 1:**

Collections 类的 **reverseOrder()** 方法返回一个比较器，该比较器强制对象的自然顺序相反。在 TreeMap 的构造函数中使用它来创建一个对象，该对象以与键相反的顺序存储映射。

> //在构造函数
> 中使用 reverseOrder()方法树图<整数，字符串>树图=新树图<整数，字符串>(collections . reverseOrder())；

下面是实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to iterate TreeMap in Reverse Order in Java

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Use reverseOrder() method in the constructor
        TreeMap<Integer, String> treeMap
            = new TreeMap<>(Collections.reverseOrder());

        // Add elements to treeMap
        treeMap.put(1, "Hello");
        treeMap.put(2, "geeks");
        treeMap.put(3, "on");
        treeMap.put(4, "geeksforgeeks");

        // Print the TreeMap in reverse order of the keys
        System.out.println("TreeMap in reverse order: "
                           + treeMap);
    }
}
```

**Output**

```java
TreeMap in reverse order: {4=geeksforgeeks, 3=on, 2=geeks, 1=Hello}
```

**时间复杂度:** O(N)

**方法二:**

**下行键集()**方法返回键的逆序集合视图。因此，遍历以降序返回 TreeMap 键的集合视图，并在 get()方法的帮助下获取值。

**注意:**DecendingKeySet()方法返回的键集是一个视图，它由原始的 TreeMap 对象支持。对此视图所做的任何更改都将反映在原始的树形图对象中，反之亦然。

下面是实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to iterate TreeMap in Reverse Order in Java

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // New TreeMap
        TreeMap<Integer, String> treeMap = new TreeMap<>();

        // Add elements to treeMap
        treeMap.put(1, "Hello");
        treeMap.put(2, "geeks");
        treeMap.put(3, "on");
        treeMap.put(4, "geeksforgeeks");

        // Print the TreeMap
        System.out.println("TreeMap before reverse: "
                           + treeMap);

        // view set of the keys in reverseOrder
        Set<Integer> keySet = treeMap.descendingKeySet();

        // After reverse
        System.out.println("TreeMap after reverse:");

        // Iterate view set of the keys
        // and get value of the key
        for (Integer key : keySet) {
            // Print key:value of the TreeMap
            System.out.println(key + " = "
                               + treeMap.get(key));
        }
    }
}
```

**Output**

```java
TreeMap before reverse: {1=Hello, 2=geeks, 3=on, 4=geeksforgeeks}
TreeMap after reverse:
4 = geeksforgeeks
3 = on
2 = geeks
1 = Hello
```