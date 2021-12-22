# 用示例列出 Java 中的 size()方法

> 原文:[https://www . geesforgeks . org/list-size-method-in-Java-with-examples/](https://www.geeksforgeeks.org/list-size-method-in-java-with-examples/)

Java 中[列表界面](https://www.geeksforgeeks.org/list-interface-java-examples/)的 **size()** 方法用于获取该列表中的元素个数。也就是说，此方法返回此列表容器中存在的元素的计数。

**语法:**

```
public int size()
```

**参数**:该方法不取任何参数。

**返回值:**该方法返回该列表中**元素个数**。

![](img/44f83bbf17ed431ea2790361ae6372b3.png)

**说明:**假设它是一个整数列表

```
Input  : {3,2,1,5,7} 
Output : 5
```

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Illustrate size() method
// of List class for Integer value

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] arg)
    {
        // Creating object of ArrayList class
        List<Integer> list = new ArrayList<Integer>();

        // Populating List by adding integer elements
        // using add() method
        list.add(1);
        list.add(2);
        list.add(3);
        list.add(4);
        list.add(5);

        // Printing elements of List
        System.out.println("Before operation: " + list);

        // Getting total size of list
        // using size() method
        int size = list.size();

        // Printing the size of List
        System.out.println("Size of list = " + size);
    }
}
```

**Output**

```
Before operation: [1, 2, 3, 4, 5]
Size of list = 5
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Illustrate size() method
// of List class for Integer value

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an empty string list by
        // declaring elements of string type
        List<String> list = new ArrayList<String>();

        // Populating List by adding string elements
        // using add() method
        list.add("Geeks");
        list.add("for");
        list.add("Geeks");

        // Printing the List
        System.out.println("Before operation: " + list);

        // Getting total size of list
        // using size() method
        int size = list.size();

        // Printing the size of list
        System.out.println("Size of list = " + size);
    }
}
```

**Output**

```
Before operation: [Geeks, for, Geeks]
Size of list = 3
```