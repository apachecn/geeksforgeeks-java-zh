# 用示例列出 Java 中的 retainAll()方法

> 原文:[https://www . geesforgeks . org/list-retain all-method-in-Java-with-examples/](https://www.geeksforgeeks.org/list-retainall-method-in-java-with-examples/)

此方法用于将集合中的所有元素从指定集合保留到列表中。

**语法:**

```
boolean retainAll(Collection c)
```

**参数:**该方法只有一个参数，集合中的哪些元素要保留在给定的列表中。

**返回:**如果元素被保留，列表发生变化，该方法返回 True。

下面的程序展示了这种方法的实现。

**程序 1:**

```
// Java code to show the implementation of
// retainAll method in list interface
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
        l.add(9);
        System.out.println(l);

        ArrayList<Integer> arr = new ArrayList<>();
        arr.add(3);
        arr.add(5);
        l.retainAll(arr);

        System.out.println(l);
    }
}
```

**Output:**

```
[1, 3, 5, 7, 9]
[3, 5]

```

**程序 2:** 下面是显示使用 Linkedlist 实现 list.retainAll()的代码。

```
// Java code to show the implementation of
// retainAll method in list interface
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
        l.add("90");
        System.out.println(l);

        ArrayList<String> arr = new ArrayList<>();
        arr.add("30");
        arr.add("50");
        l.retainAll(arr);

        System.out.println(l);
    }
}
```

**Output:**

```
[10, 30, 50, 70, 90]
[30, 50]

```

**参考:**
[甲骨文文档](https://docs.oracle.com/javase/6/docs/api/java/util/ArrayList.html#contains(java.lang.Object))