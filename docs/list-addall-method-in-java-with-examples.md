# 用示例列出 Java 中的 addAll()方法

> 原文:[https://www . geesforgeks . org/list-addall-method-in-Java-with-examples/](https://www.geeksforgeeks.org/list-addall-method-in-java-with-examples/)

这个方法按照指定集合的迭代器返回的顺序，将指定集合中的所有元素追加到这个列表的末尾。

**语法:**

```
boolean addAll(Collection c)
```

**参数:**该函数只有一个参数，即 Collection c，其元素将被追加到列表中。

**返回:**如果指定列表的元素被追加，列表发生变化，则返回真。

下面的程序展示了这种方法的实现。

**程序 1:**

```
// Java code to show the implementation of
// addAll method in list interface
import java.util.*;
public class GfG {

    // Driver code
    public static void main(String[] args)
    {

        // Initializing a list of type arraylist
        List<Integer> l = new ArrayList<>();
        l.add(10);
        l.add(15);
        l.add(20);
        System.out.println(l);

        // Initializing a collection to be appended to list
        ArrayList<Integer> arr = new ArrayList<Integer>();
        arr.add(100);
        arr.add(200);
        arr.add(300);
        System.out.println(arr);

        l.addAll(arr);

        System.out.println(l);
    }
}
```

**Output:**

```
[10, 15, 20]
[100, 200, 300]
[10, 15, 20, 100, 200, 300]

```

**程序 2:** 下面是用 Linkedlist 展示 list.addAll()实现的代码。

```
// Java code to show the implementation of
// addAll method in list interface
import java.util.*;
public class GfG {

    // Driver code
    public static void main(String[] args)
    {

        // Initializing a list of type Linkedlist
        List<Integer> l = new LinkedList<>();
        l.add(10);
        l.add(15);
        l.add(20);
        System.out.println(l);

        // Initializing a collection to be appended to list
        ArrayList<Integer> arr = new ArrayList<Integer>();
        arr.add(100);
        arr.add(200);
        arr.add(300);
        System.out.println(arr);

        l.addAll(arr);

        System.out.println(l);
    }
}
```

**Output:**

```
[10, 15, 20]
[100, 200, 300]
[10, 15, 20, 100, 200, 300]

```

**参考:**
[甲骨文文档](https://docs.oracle.com/javase/6/docs/api/java/util/ArrayList.html#contains(java.lang.Object))