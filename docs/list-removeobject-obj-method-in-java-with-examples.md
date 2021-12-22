# 用示例列出 Java 中的 remove(Object obj)方法

> 原文:[https://www . geesforgeks . org/list-remove object-obj-method-in-Java-with-examples/](https://www.geeksforgeeks.org/list-removeobject-obj-method-in-java-with-examples/)

Java 中 List 接口的 **remove(Object obj)** 方法用于从这个 List 中移除指定元素 *obj* 的第一个出现，如果它存在于 List 中。

**语法** :

```
boolean remove(Object obj)

```

**参数**:它接受列表类型的单个参数*对象*，表示要从给定列表中移除的元素。

**返回值**:从列表中删除指定元素的第一个匹配项后，返回布尔值“真”，否则，如果列表中没有该元素，该方法将返回“假”。

下面的程序说明了在 Java 中移除列表的方法:

**程序 1** :

```
// Program to illustrate the
// remove(int index) method

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declare an empty List of size 5
        List<Double> list = new ArrayList<Double>(5);

        // Add elements to the list
        list.add(5.0);
        list.add(10.5);
        list.add(15.1);
        list.add(20.6);
        list.add(25.2);

        // Element needed to be removed
        double obj = 15.1;

        // Initial list
        System.out.println("Initial List: " + list);

        // remove element
        list.remove(obj);

        // Final list
        System.out.println("Final List: " + list);
    }
}
```

**输出:**

```
Initial List: [5.0, 10.5, 15.1, 20.6, 25.2]
Final List: [5.0, 10.5, 20.6, 25.2]

```

**程序二** :

```
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

        // Element to be removed
        String obj = "for";

        // Initial list
        System.out.println("Initial List: " + list);

        // remove element
        list.remove(obj);

        // Final list
        System.out.println("Final List: " + list);
    }
}
```

**输出:**

```
Initial List: [Welcome, to, Geeks, for, Geeks]
Final List: [Welcome, to, Geeks, Geeks]

```

**注意**:在将整数元素传递给 remove 方法时，使用整数列表时要小心，列表会将该方法视为 remove(int index)。它会将元素视为索引，而不是实际元素。

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/util/list . html # remove-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/util/List.html#remove-java.lang.Object-)