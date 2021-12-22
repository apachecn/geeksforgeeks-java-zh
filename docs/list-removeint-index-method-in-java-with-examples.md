# 用示例列出 Java 中的移除(int index)方法

> 原文:[https://www . geesforgeks . org/list-removeint-index-method-in-Java-with-examples/](https://www.geeksforgeeks.org/list-removeint-index-method-in-java-with-examples/)

Java 中 List 接口的 **remove(int index)** 方法用于从 List 容器的指定索引中移除一个元素，并在移除后返回该元素。它还会将列表中被移除元素之后的元素向左移动 1 个位置。

**语法** :

```java
E remove(int index)

Where, E is the type of element maintained
by this List collection

```

**参数**:它接受一个整数类型的单参数*索引*，代表需要从列表中删除的元素的索引。

**返回值**:移除后返回给定索引处的元素。

下面的程序说明了 Java 中 List 的移除(int index)方法:

**程序 1** :

```java
// Program to illustrate the
// remove(int index) method

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declare an empty List of size 5
        List<Integer> list = new ArrayList<Integer>(5);

        // Add elements to the list
        list.add(5);
        list.add(10);
        list.add(15);
        list.add(20);
        list.add(25);

        // Index from which you want to remove element
        int index = 2;

        // Initial list
        System.out.println("Initial List: " + list);

        // remove element
        list.remove(index);

        // Final list
        System.out.println("Final List: " + list);
    }
}
```

**输出:**

```java
Initial List: [5, 10, 15, 20, 25]
Final List: [5, 10, 20, 25]

```

**程序二** :

```java
// Program to illustrate the
// remove(int index) method

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declare an empty List of size 5
        List<String> list = new ArrayList<String>(5);

        // Add elements to the list
        list.add("Welcome");
        list.add("to");
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");

        // Index from which you want
        // to remove element
        int index = 2;

        // Initial list
        System.out.println("Initial List: " + list);

        // remove element
        list.remove(index);

        // Final list
        System.out.println("Final List: " + list);
    }
}
```

**输出:**

```java
Initial List: [Welcome, to, Geeks, for, Geeks]
Final List: [Welcome, to, for, Geeks]

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/util/list . html # remove-int-](https://docs.oracle.com/javase/8/docs/api/java/util/List.html#remove-int-)