# Java 中的抽象顺序列表等于()方法，示例

> 原文:[https://www . geeksforgeeks . org/abstractsequentialist-equals-method-in-Java-with-example/](https://www.geeksforgeeks.org/abstractsequentiallist-equals-method-in-java-with-example/)

**Java . util . AbstractSequentialList**类的 **equals()** 方法用于检查这个 abstractsequentialist 对象是否等于作为参数传递的对象。此方法返回一个表示相同内容的布尔值。

**语法:**

```
public boolean equals(Object o)
```

**参数:**该方法将的**对象作为参数与该列表进行相等比较。**

**返回值:**如果指定的对象等于这个列表，这个方法返回**真**。

以下是说明**等于()**方法的例子。

**例 1:**

```
// Java program to demonstrate equals()
// method of AbstractSequentialList

import java.util.*;

public class GFG {
    public static void main(String[] argv)
    {

        // Creating object of AbstractSequentialList<String>
        AbstractSequentialList<String>
            arrlist1 = new LinkedList<String>();

        // Populating arrlist1
        arrlist1.add("A");
        arrlist1.add("B");
        arrlist1.add("C");
        arrlist1.add("D");
        arrlist1.add("E");

        // print arrlist1
        System.out.println("First AbstractSequentialListlist: "
                           + arrlist1);

        // Creating another object of AbstractSequentialList<String>
        AbstractSequentialList<String>
            arrlist2 = new LinkedList<String>();

        // Populating arrlist2
        arrlist2.add("A");
        arrlist2.add("B");
        arrlist2.add("C");
        arrlist2.add("D");
        arrlist2.add("E");

        // print arrlist2
        System.out.println("Second AbstractSequentialList: "
                           + arrlist2);

        // comparing first AbstractSequentialList to another
        // using equals() method
        boolean value
            = arrlist1.equals(arrlist2);

        // print the value
        System.out.println("Are both list equal: "
                           + value);
    }
}
```

**Output:**

```
First AbstractSequentialListlist: [A, B, C, D, E]
Second AbstractSequentialList: [A, B, C, D, E]
Are both list equal: true

```

**例 2:**

```
// Java program to demonstrate equals()
// method of AbstractSequentialList

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {

        // Creating object of AbstractSequentialList
        AbstractSequentialList<Integer>
            arrlist1 = new LinkedList<Integer>();

        // Populating arrlist1
        arrlist1.add(10);
        arrlist1.add(20);
        arrlist1.add(30);
        arrlist1.add(40);
        arrlist1.add(50);

        // print arrlist1
        System.out.println("First AbstractSequentialListlist: "
                           + arrlist1);

        // Creating another object of AbstractSequentialList
        AbstractSequentialList<Integer>
            arrlist2 = new LinkedList<Integer>();

        // Populating arrlist2
        arrlist2.add(10);
        arrlist2.add(20);
        arrlist2.add(30);

        // print arrlist2
        System.out.println("Second AbstractSequentialList: "
                           + arrlist2);

        // comparing first AbstractSequentialList to another
        // using equals() method
        boolean value = arrlist1.equals(arrlist2);

        // print the value
        System.out.println("Are both list equal: "
                           + value);
    }
}
```

**Output:**

```
First AbstractSequentialListlist: [10, 20, 30, 40, 50]
Second AbstractSequentialList: [10, 20, 30]
Are both list equal: false

```