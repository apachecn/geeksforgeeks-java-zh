# 用示例列出 Java 中的 lastIndexOf()方法

> 原文:[https://www . geesforgeks . org/list-last indexof-method-in-Java-with-examples/](https://www.geeksforgeeks.org/list-lastindexof-method-in-java-with-examples/)

此方法返回此列表中指定元素的最后一个索引，如果此列表不包含该元素，则返回-1。

**语法:**

```
int lastIndexOf(Object o)
```

**参数:**该函数只有一个参数，即列表中要搜索的元素。

**返回:**此方法返回列表中给定元素的最后一个出现索引，如果元素不在列表中，则返回“-1”。

下面的程序展示了这种方法的实现。

**程序 1:**

```
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

```
[1, 3, 5, 7, 3]
4

```

**程序 2:** 下面是使用 Linkedlist 显示 list.lastIndexOf()实现的代码。

```
// Java code to show the implementation of
// lastIndexOf method in list interface
import java.util.*;
public class GfG {

    // Driver code
    public static void main(String[] args)
    {

        // Initializing a list of type Linkedlist
        List<String> l = new LinkedList<>();
        l.add("10");
        l.add("30");
        l.add("50");
        l.add("70");
        l.add("30");
        System.out.println(l);
        System.out.println(l.lastIndexOf("30"));
    }
}
```

**Output:**

```
[10, 30, 50, 70, 30]
4

```

**参考:**
[甲骨文文档](https://docs.oracle.com/javase/6/docs/api/java/util/ArrayList.html#contains(java.lang.Object))