# 用示例列出 Java 中的子列表()方法

> 原文:[https://www . geesforgeks . org/list-sublist-method-in-Java-with-examples/](https://www.geeksforgeeks.org/list-sublist-method-in-java-with-examples/)

此方法给出此列表中指定的 fromIndex(包含)和 toIndex(不包含)之间的部分的视图。

**语法:**

```java
List subList(int fromIndex,
              int toIndex)
```

**参数:**这个函数有两个参数*从索引*和*到索引*，分别是开始和结束范围，从给定的列表创建一个子列表。

**返回:**该方法返回给定范围之间的列表视图。

下面的程序展示了这种方法的实现。

**程序 1:**

```java
// Java code to show the implementation of
// lastIndexOf method in list interface
import java.util.*;
public class GfG {

    // Driver code
    public static void main(String[] args)
    {

        // Initializing a list of type Linkedlist
        List<Integer> l = new LinkedList<>();
        l.add(1);
        l.add(3);
        l.add(5);
        l.add(7);
        l.add(3);
        System.out.println(l);
        System.out.println(l.lastIndexOf(3));
    }
}
```

**Output:**

```java
[1, 3, 5, 7, 3]
4

```

**Output:**

```java
[1, 3, 5, 7, 3]
4

```

**程序 2:** 下面是使用 Linkedlist 展示 list.subList()实现的代码。

```java
// Java code to show the implementation of
// subList method in list interface
import java.util.*;
public class GfG {

    // Driver code
    public static void main(String[] args)
    {

        // Initializing a list of type Linkedlist
        List<Integer> l = new LinkedList<>();
        l.add(10);
        l.add(30);
        l.add(50);
        l.add(70);
        l.add(30);
        List<Integer> sub = new LinkedList<>();
        System.out.println(l);
        sub = l.subList(1, 3);
        System.out.println(sub);
    }
}
```

**Output:**

```java
[10, 30, 50, 70, 30]
[30, 50]

```

**参考:**
[甲骨文文档](https://docs.oracle.com/javase/6/docs/api/java/util/ArrayList.html#contains(java.lang.Object))