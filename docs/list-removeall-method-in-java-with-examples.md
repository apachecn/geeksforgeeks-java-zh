# 用示例列出 Java 中的 removeAll()方法

> 原文:[https://www . geesforgeks . org/list-remove all-in-Java-method-with-examples/](https://www.geeksforgeeks.org/list-removeall-method-in-java-with-examples/)

此方法用于从指定列表中移除集合中存在的所有元素。

**语法:**

```java
boolean removeAll(Collection c)
```

**参数:**该方法只有一个参数，即从给定列表中移除哪些元素的集合。

**返回:**如果元素被移除，列表发生变化，该方法返回真。

下面的程序展示了这种方法的实现。

**程序 1:**

```java
// Java code to show the implementation of
// removeAll method in list interface
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
        l.add(90);
        System.out.println(l);

        ArrayList<Integer> arr = new ArrayList<>();
        arr.add(30);
        arr.add(50);
        l.removeAll(arr);

        System.out.println(l);
    }
}
```

**Output:**

```java
[10, 30, 50, 70, 90]
[10, 70, 90]

```

**程序 2:** 下面是使用 Linkedlist 显示 list.removeAll()实现的代码。

```java
// Java code to show the implementation of
// removeAll method in list interface
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
        l.removeAll(arr);

        System.out.println(l);
    }
}
```

**Output:**

```java
[10, 30, 50, 70, 90]
[10, 70, 90]

```

**参考:**
[甲骨文文档](https://docs.oracle.com/javase/6/docs/api/java/util/ArrayList.html#contains(java.lang.Object))