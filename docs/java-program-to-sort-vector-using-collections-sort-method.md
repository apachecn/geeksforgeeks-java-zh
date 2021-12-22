# 使用 Collections.sort()方法对向量进行排序的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到排序-向量使用-集合-排序-方法/](https://www.geeksforgeeks.org/java-program-to-sort-vector-using-collections-sort-method/)

**java.util.Collections . sort()**方法存在于 Java . util . collections 类中。用于对集合的指定 [列表](https://www.geeksforgeeks.org/list-interface-java-examples/) 中存在的元素进行升序排序。

**语法:**

> *公共空洞排序(Vector 对象)；*

**参数:**作为参数的向量实例

**图解:** [***收藏.整理()方法***](https://www.geeksforgeeks.org/collections-sort-java-examples/)

```java
Let us suppose that our list contains
{"Geeks For Geeks", "Friends", "Dear", "Is", "Superb"}

After using Collection.sort(), we obtain a sorted list as
{"Dear", "Friends", "Geeks For Geeks", "Is", "Superb"}
```

1.  创建矢量实例。
2.  在向量中添加元素。
3.  函数前打印向量使用方法说明函数负责什么。
4.  使用 Collection.sort()方法。
5.  排序后打印向量，可以看到排序是升序的。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Sort Vector
// using Collections.sort() Method

// Importing Collection and Vector class
import java.util.Collections;
import java.util.Vector;

public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Create a instance vector
        Vector<String> vec = new Vector<String>();

        // Insert the values in vector
        vec.add("a");
        vec.add("d");
        vec.add("e");
        vec.add("b");
        vec.add("c");

        // Display the vector
        System.out.println("original vector : " + vec);

        // Call sort() method
        Collections.sort(vec);

        // Display vector after replacing value
        System.out.println("\nsorted vector : " + vec);
    }
}
```

**Output**

```java
original vector : [a, d, e, b, c]

sorted vector : [a, b, c, d, e]

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Sort Vector
// using Collections.sort() Method

// Importing Collection and Vector class
import java.util.Collections;
import java.util.Vector;

public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Create a instance vector
        Vector<String> vec = new Vector<String>();

        // Insert the values in vector
        vec.add("4");
        vec.add("2");
        vec.add("7");
        vec.add("3");
        vec.add("2");

        // Display the vector
        System.out.println("\noriginal vector : " + vec);

        // Call sort() method
        Collections.sort(vec);

        // Display vector after replacing value
        System.out.println("\nsorted vector : " + vec);
    }
}
```

**Output**

```java
original vector : [4, 2, 7, 3, 2]

sorted vector : [2, 2, 3, 4, 7]

```