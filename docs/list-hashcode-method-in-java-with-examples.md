# 用示例列出 Java 中的 hashCode()方法

> 原文:[https://www . geesforgeks . org/list-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/list-hashcode-method-in-java-with-examples/)

这个方法用于为给定的列表生成 hashCode。

**语法:**

```
int hashCode()
```

**参数:**此功能无参数。

**返回:**该函数返回给定列表的哈希值。

下面的程序展示了这种方法的实现。

**程序 1:**

```
// Java code to show the implementation of
// hashCode method in list interface
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

        int hash = l.hashCode();

        System.out.println(hash);
    }
}
```

**Output:**

```
[10, 15, 20]
39886

```

**程序 2:** 下面是显示使用 Linkedlist 实现 list.hashCode()的代码。

```
// Java code to show the implementation of
// hashCode method in list interface
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

        int hash = l.hashCode();

        System.out.println(hash);
    }
}
```

**Output:**

```
[10, 15, 20]
1586008

```

**参考:**
[甲骨文文档](https://docs.oracle.com/javase/6/docs/api/java/util/ArrayList.html#contains(java.lang.Object))