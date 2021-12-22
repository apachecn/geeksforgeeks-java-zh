# Java 中数组列表获取(索引)方法示例

> 原文:[https://www . geesforgeks . org/ArrayList-get-method-Java-examples/](https://www.geeksforgeeks.org/arraylist-get-method-java-examples/)

Java 中 [**数组列表**](https://www.geeksforgeeks.org/arraylist-in-java/) 的 **get()** 方法用于获取列表中指定索引的元素。

**语法:**

```java
get(index)
```

**参数:**要返回的元素的索引。它是数据类型 int。

**返回类型:**给定列表中指定索引处的元素。

**异常:**如果索引超出范围(索引=大小())，它将抛出[索引](https://www.geeksforgeeks.org/array-index-out-of-bounds-exception-in-java/)

> **注意:**时间复杂度 **:** 数组列表是构建顶级数组的列表实现之一。因此，get(index)总是一个时间常数 O(1)的操作。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Demonstrate the working of
// get() method in ArrayList

// Importing ArrayList class
import java.util.ArrayList;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an Empty Integer ArrayList
        ArrayList<Integer> arr = new ArrayList<Integer>(4);

        // Using add() to initialize values
        // [10, 20, 30, 40]
        arr.add(10);
        arr.add(20);
        arr.add(30);
        arr.add(40);

        // Printing elements of list
        System.out.println("List: " + arr);

        // Getting element at index 2
        int element = arr.get(2);

        // Displaying element at specified index
        // on console inside list
        System.out.println("the element at index 2 is "
                           + element);
    }
}
```

**Output**

```java
List: [10, 20, 30, 40]
the element at index 2 is 30
```

**例 2** :演示错误的程序

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Demonstrate Error Generated
// while using get() method in ArrayList

// Importing ArrayList class
import java.util.ArrayList;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an Empty Integer ArrayList
        ArrayList<Integer> arr = new ArrayList<Integer>(4);

        // Using add() method to insert elements
        // and adding custom values
        arr.add(10);
        arr.add(20);
        arr.add(30);
        arr.add(40);

        // Getting element at index 2
        int element = arr.get(5);

        // Print all the elements of ArrayList
        System.out.println("the element at index 2 is "
                           + element);
    }
}
```

**输出:**

```java
Exception in thread "main" java.lang.IndexOutOfBoundsException: Index: 5, Size: 4
    at java.util.ArrayList.rangeCheck(ArrayList.java:657)
    at java.util.ArrayList.get(ArrayList.java:433)
    at GFG.main(GFG.java:22)
```