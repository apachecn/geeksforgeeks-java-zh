# Java 中 LinkedHashSet equals()方法示例

> 原文:[https://www . geeksforgeeks . org/link edhashset-equals-method-in-Java-with-example/](https://www.geeksforgeeks.org/linkedhashset-equals-method-in-java-with-example/)

**java.util.LinkedHashSet** 类的 **equals()** 方法用于将指定的对象与这个相等集进行比较。当且仅当指定的对象也是集合，两个集合具有相同的大小，并且两个集合中所有对应的元素对相等时，返回 true。(两个元素 e1 和 e2 相等，如果(e1==null？e2==null : e1.equals(e2))。)换句话说，如果两个集合包含相同顺序的相同元素，则它们被定义为相等。

**语法:**

```
public boolean equals(Object o)
```

**参数:**该方法以的**对象为参数，与该集合进行相等性比较。**

**返回值:**如果指定的对象等于这个集合，这个方法返回**真**。

以下是说明**等于()**方法的例子。

**例 1:**

```
// Java program to demonstrate equals()
// method of LinkedHashSet

import java.util.*;

public class GFG {
    public static void main(String[] argv)
    {

        // Creating object of LinkedHashSet<String>
        LinkedHashSet<String>
            set1 = new LinkedHashSet<String>();

        // Populating set1
        set1.add("A");
        set1.add("B");
        set1.add("C");
        set1.add("D");
        set1.add("E");

        // print set1
        System.out.println("First LinkedHashSet: "
                           + set1);

        // Creating another object of LinkedHashSet<String>
        LinkedHashSet<String>
            set2 = new LinkedHashSet<String>();

        // Populating set2
        set2.add("A");
        set2.add("B");
        set2.add("C");
        set2.add("D");
        set2.add("E");

        // print set2
        System.out.println("Second LinkedHashSet: "
                           + set2);

        // comparing first LinkedHashSet to another
        // using equals() method
        boolean value
            = set1.equals(set2);

        // print the value
        System.out.println("Are both set equal: "
                           + value);
    }
}
```

**Output:**

```
First LinkedHashSet: [A, B, C, D, E]
Second LinkedHashSet: [A, B, C, D, E]
Are both set equal: true

```

**例 2:**

```
// Java program to demonstrate equals()
// method of LinkedHashSet

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {

        // Creating object of LinkedHashSet
        LinkedHashSet<Integer>
            set1 = new LinkedHashSet<Integer>();

        // Populating set1
        set1.add(10);
        set1.add(20);
        set1.add(30);
        set1.add(40);
        set1.add(50);

        // print set1
        System.out.println("First LinkedHashSet: "
                           + set1);

        // Creating another object of LinkedHashSet
        LinkedHashSet<Integer>
            set2 = new LinkedHashSet<Integer>();

        // Populating set2
        set2.add(10);
        set2.add(20);
        set2.add(30);

        // print set2
        System.out.println("Second LinkedHashSet: "
                           + set2);

        // comparing first LinkedHashSet to another
        // using equals() method
        boolean value = set1.equals(set2);

        // print the value
        System.out.println("Are both set equal: "
                           + value);
    }
}
```

**Output:**

```
First LinkedHashSet: [10, 20, 30, 40, 50]
Second LinkedHashSet: [10, 20, 30]
Are both set equal: false

```