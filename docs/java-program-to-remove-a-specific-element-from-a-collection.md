# 从集合中移除特定元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-remove-a-specific-element-from-a-collection/](https://www.geeksforgeeks.org/java-program-to-remove-a-specific-element-from-a-collection/)

**remove()方法**用于从集合中移除元素。它移除列表中指定位置的元素。通过从其索引中减去 1，将任何后续元素向左移动。简单来说，[remove()](https://www.geeksforgeeks.org/arraydeque-remove-method-in-java/)方法用于通过移除值并返回相同的值来移除列表中特定索引的元素。

**方法:**在该方法上定义了两种标准方法，如下所示。

1.  [*移除(int index)*](https://www.geeksforgeeks.org/list-removeint-index-method-in-java-with-examples/)
2.  [移除(对象对象)](https://www.geeksforgeeks.org/list-removeobject-obj-method-in-java-with-examples/)

**方法 1:**Java 中 List 接口的 **remove(int index)** 方法用于从 List 容器的指定索引中移除一个元素，并在移除后返回该元素。它还会将列表中被移除元素之后的元素向左移动 1 个位置。

**语法**:

```java
remove(int index)
```

**参数:**取 int 类型的一个参数作为遍历过索引，其中索引值是要从列表中删除的值。

**返回类型:**删除了部分元素的数组列表。

**异常:**由于处理具有如此明确指定大小的指数[数组的边界](https://www.geeksforgeeks.org/understanding-array-indexoutofbounds-exception-in-java/)在两种情况下抛出

*   两个指数都是负数
*   所提到的索引超出了[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)的索引

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Remove a Specific
// Element from a Collection

// Importing Java libraries
import java.util.List;
import java.util.ArrayList;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an ArrayList
        List<Integer> al = new ArrayList<>();

        // Inserting % elements to it
        al.add(10);
        al.add(20);
        al.add(30);
        al.add(1);
        al.add(2);

        // If elements set is larger use
        // iteration in loops to insert element

        // Display ArrayList after insertion
        System.out.println("Original ArrayList : " + al);

        // Making 1st remove call
        // which throw 20 out of list
        al.remove(1);

        // Here ArrayList: 10 30 1 2

        // Making 2nd remove call
        // which throw 30 out of list
        al.remove(1);
        // Here ArrayList: 10 1 2

        // Printing modified Arraylist after deleting few
        // elements
        System.out.println("Modified ArrayList : " + al);
    }
}
```

**Output**

```java
Original ArrayList : [10, 20, 30, 1, 2]
Modified ArrayList : [10, 1, 2]
```

**方法 2:**Java 中 List 接口的 **remove(Object obj)** 方法用于从这个 List 中移除指定元素 *obj* 的第一个出现，如果它存在于 List 中的话。

**语法**:

```java
boolean remove(Object obj)
```

**参数**:它接受列表类型的单个参数*对象*，表示要从给定列表中移除的元素。

**返回值**:从列表中删除指定元素的第一个匹配项后，返回布尔值“真”，否则，如果列表中没有该元素，该方法将返回“假”。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of remove()
// method on an integer arraylist

// Importing specific libraries
import java.util.List;
import java.util.ArrayList;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an ArrayList and
        // storing elements in list
        List<Integer> al = new ArrayList<>();

        // Addition of elements to List
        al.add(10);
        al.add(20);
        al.add(30);
        al.add(1);
        al.add(2);

        // This makes a call to remove(Object) and
        // removes element 1
        al.remove(new Integer(1));

        // This makes a call to remove(Object) and
        // removes element 2
        al.remove(new Integer(2));

        // Printing modified ArrayList
        System.out.println("Modified ArrayList : " + al);
    }
}
```

**输出:**

```java
Modified ArrayList : [10, 20, 30]
```

**注意** ***:*** 有时确实会抛出使用不推荐使用的函数调用或对象的警告。人们可以像重新编译一样找出它在哪里发生。一般来说，使用在下一个版本中可能会消失的不推荐使用的库是一个坏主意。