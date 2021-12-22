# 用示例在 Java 中抽象设置 hashCode()方法

> 原文:[https://www . geesforgeks . org/abstract set-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractset-hashcode-method-in-java-with-examples/)

**[Java 抽象集](https://www.geeksforgeeks.org/abstractset-class-in-java-with-examples/)** 中的 **AbstractSet.hashCode()** 方法用于获取特定这个抽象集的哈希码值。一个集合由许多存储元素的桶组成。每个桶都有一个唯一的标识，当一个元素被插入桶中时，它的 hashcode 与桶的标识符匹配，如果匹配，该元素被成功存储。这就是哈希代码的工作原理。

**语法:**

```
AbstractSet.hashCode()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回集合的**哈希值**。

下面的程序用来说明 AbstractSet.hashCode()方法的工作原理:

**程序 1:**

```
// Java code to illustrate the hashCode() method

import java.util.*;

public class Abstract_Set_Demo {
    public static void main(String[] args)
    {

        // Creating an empty AbstractSet
        AbstractSet<String>
            abs_set = new HashSet<String>();

        // Adding elements into the set
        abs_set.add("Geeks");
        abs_set.add("4");
        abs_set.add("Geeks");
        abs_set.add("Welcomes");
        abs_set.add("You");

        // Displaying the AbstractSet
        System.out.println("Initial Set is: "
                           + abs_set);

        // Getting the hashcode value for the set
        System.out.println("The hashcode value of the set: "
                           + abs_set.hashCode());
    }
}
```

**输出:**

```
Initial Set is: [4, Geeks, You, Welcomes]
The hashcode value of the set-295204749

```

**程序二:**

```
// Java code to illustrate the hashCode() method

import java.util.*;

public class Abstract_Set_Demo {
    public static void main(String[] args)
    {

        // Creating an empty AbstractSet
        AbstractSet<Integer>
            abs_set = new TreeSet<Integer>();

        // Adding elements into the set
        abs_set.add(15);
        abs_set.add(20);
        abs_set.add(30);
        abs_set.add(40);
        abs_set.add(50);

        // Displaying the AbstractSet
        System.out.println("Initial Set is: "
                           + abs_set);

        // Getting the hashcode value for the set
        System.out.println("The hashcode value of the set: "
                           + abs_set.hashCode());
    }
}
```

**输出:**

```
Initial Set is: [15, 20, 30, 40, 50]
The hashcode value of the set: 155

```

**注意:**同一操作可以对任意类型的集合进行，不同数据类型可以变化和组合。