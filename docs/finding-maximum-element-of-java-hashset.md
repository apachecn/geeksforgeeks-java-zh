# 寻找 Java HashSet 的最大元素

> 原文:[https://www . geesforgeks . org/finding-max-element-of-Java-hashset/](https://www.geeksforgeeks.org/finding-maximum-element-of-java-hashset/)

Java [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 类用于创建集合，该集合使用哈希表进行存储，该哈希表使用称为哈希的机制。集合的实现类。它继承了[抽象类](https://www.geeksforgeeks.org/abstract-classes-in-java/)，实现了 et [接口](https://www.geeksforgeeks.org/interfaces-in-java/)。主要特点是不允许重复，内部使用哈希表。

**说明:**在 HashSet 中找到最大元素。

```java
Input: [24, 56, 87, 64, 29, 2, 65]
Output: 87

Input: [45, 3, 65, 32, 64, 12, 43]
Output: 65
```

**方法:**

*   使用每个循环(简单方法)
*   使用 HashSet 的 [*Collection.max()*](https://www.geeksforgeeks.org/collections-max-method-in-java-with-examples/) 方法(最优方法)

**方法 1:** 使用 for-loop 打印哈希集中的最大元素。

**进场:**

1.  创建哈希集的对象
2.  向创建的对象添加元素
3.  创建一个变量，并赋予其值 [MIN_VALUE](https://www.geeksforgeeks.org/integer-max_value-and-integer-min_value-in-java-with-examples/)
4.  对每个循环重复使用

> 记住:
> 
> *   在计算最大值时，将-∞指定为初始最大值
> *   在计算最小分配+∞作为初始最小值时

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to find maximum element on HashSet

// Importing all java input output classes
// Importing Collection and HashSet class from
// java.util package
import java.io.*;
import java.util.Collections;
import java.util.HashSet;

// Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of HashSet (of Integer type)
        HashSet<Integer> gfg = new HashSet<Integer>();

        // Adding elements in above object of HashSet
        // Custom inputs
        gfg.add(24);
        gfg.add(56);
        gfg.add(87);
        gfg.add(64);
        gfg.add(29);
        gfg.add(2);
        gfg.add(65);

        // Print all the elements in the above HashSet
        System.out.println("Elements in HashSet = " + gfg);

        // Remember :
        // In computing maximum assign -∞ as initial max
        // In computing minimum assign +∞ as initial min

        // Initially assigning -(infinity) as max value
        // so as to deal with garbage value issues.
        int max = Integer.MIN_VALUE;

        // For each loop to iterate over elements of HashSet
        // to find maximum among all elements in Set
        for (int var : gfg) {

            // For elements in Set
            if (var > max)

                // Update the current maximum element
                max = var;
        }

        // Display and print the
        // maximum element in a HashSet
        System.out.println("Maximum element in HashSet = "
                           + max);
    }
}
```

**Output**

```java
Elements in HashSet = [64, 65, 2, 87, 24, 56, 29]
Maximum element in HashSet = 87

```

时间复杂度:O(n)，其中 n 是哈希集中的元素数。

**方法二:**使用 [*Collection.max()* 集合类的 HashSet 的](https://www.geeksforgeeks.org/collections-max-method-in-java-with-examples/)方法。

**语法:**

```java
public static <T extends Object & Comparable> T max(Collection coll)
```

**参数:**该方法将集合 **coll** 作为待确定最大元素的参数。

**返回值:**该方法根据元素的自然排序，返回给定集合的**最大元素**。

**异常:**该方法抛出如下异常:

*   [ClassCastException](https://www.geeksforgeeks.org/class-cast-method-in-java-with-examples/) 如果集合包含不可相互比较的元素(例如字符串和整数)。
*   [nosucheelementexception](https://www.geeksforgeeks.org/java-util-linkedlist-get-getfirst-getlast-java/)**如果集合为空**

****进场:****

1.  **创建哈希集的对象**
2.  **向创建的对象添加元素**
3.  **使用 *Collection.max()* 方法显示创建后生成的非重复列表中最大的字符串。注意，不会有单一的重复元素。**

****例 2****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java Program to find maximum element on HashSet

// Importing all java input-output classes
// Importing Collection and HashSet class from
// java.util package
import java.io.*;
import java.util.Collections;
import java.util.HashSet;

// Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating object of HashSet
        // Declaring String type objects
        HashSet<String> gfg = new HashSet<String>();

        // Adding element in above object of HashSet
        // Custom inputs
        gfg.add("Geekss");
        gfg.add("Geeks");
        gfg.add("Geek");

        // Print and display all elements inside the object
        System.out.println("Elements in HashSet = " + gfg);

        // Using Collection.max() Method to find
        // max string in HashSet
        Object obj = Collections.max(gfg);

        // Display Maximum element in a HashSet
        System.out.println("Maximum element :" + obj);
    }
}
```

****Output**

```java
Elements in HashSet = [Geekss, Geek, Geeks]
Maximum element :Geekss

```**