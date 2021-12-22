# 用示例列出 Java 中()方法的索引

> 原文:[https://www . geesforgeks . org/list-indexof-method-in-Java-with-examples/](https://www.geeksforgeeks.org/list-indexof-method-in-java-with-examples/)

此方法返回此列表中指定元素的第一个匹配项的索引，如果此列表不包含该元素，则返回-1。

**语法:**

```
public int indexOf(Object o)
```

**参数:**该函数只有一个参数，即列表中要搜索的元素。

**返回:**此方法返回列表中给定元素第一次出现的索引，如果元素不在列表中，则返回“-1”。

下面的程序展示了这种方法的实现。

**程序 1:**

```
// Java code to show the implementation of
// indexOf method in list interface
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
        System.out.println(l);
        System.out.println(l.indexOf(5));
    }
}
```

**Output:**

```
[1, 3, 5, 7]
2

```

**程序 2:** 下面是显示使用 Linkedlist 实现 list.hashCode()的代码。

```
// Java code to show the implementation of
// indexOf method in list interface
import java.util.*;
public class GfG {

    // Driver code
    public static void main(String[] args)
    {

        // Initializing a list of type Linkedlist
        List<String> l = new LinkedList<>();
        l.add("10");
        l.add("15");
        l.add("20");
        System.out.println(l);
        System.out.println(l.indexOf("20"));
    }
}
```

**Output:**

```
[10, 15, 20]
2

```

**参考:**
[甲骨文文档](https://docs.oracle.com/javase/6/docs/api/java/util/ArrayList.html#contains(java.lang.Object))