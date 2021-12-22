# 用示例列出 Java 中的 add()方法

> 原文:[https://www . geesforgeks . org/list-add-method-in-Java-with-examples/](https://www.geeksforgeeks.org/list-add-method-in-java-with-examples/)

List 接口的这个方法用于将参数中指定的元素追加到列表的末尾。

**语法:**

```
boolean add(E e)
```

**参数:**该函数只有一个参数，即 e–要附加到该列表的元素。

**返回:**如果指定的元素被追加，列表发生变化，则返回真。

下面的程序展示了这种方法的实现。

**程序 1:**

```
// Java code to show the implementation of
// add method in list interface
import java.util.*;
public class GfG {

    // Driver code
    public static void main(String[] args)
    {
        List<Integer> l = new ArrayList<>();
        l.add(10);
        l.add(15);
        l.add(20);
        System.out.println(l);
    }
}
```

**Output:**

```
[10, 15, 20]

```

**程序 2:** 下面是使用 Linkedlist 展示 list.add()实现的代码。

```
// Java code to show the implementation of
// add method in list interface using LinkedList
import java.util.*;
public class CollectionsDemo {

    // Driver code
    public static void main(String[] args)
    {

        List<Integer> ll = new LinkedList<>();
        ll.add(100);
        ll.add(200);
        ll.add(300);
        ll.add(400);
        ll.add(500);

        System.out.println(ll);
    }
}
```

**Output:**

```
[100, 200, 300, 400, 500]

```

**参考:**
[甲骨文文档](https://docs.oracle.com/javase/6/docs/api/java/util/ArrayList.html#contains(java.lang.Object))