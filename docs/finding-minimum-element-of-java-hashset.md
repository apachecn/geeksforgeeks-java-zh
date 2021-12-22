# 寻找 Java HashSet 的最小元素

> 原文:[https://www . geesforgeks . org/find-minimum-of-Java-hashset/](https://www.geeksforgeeks.org/finding-minimum-element-of-java-hashset/)

Java [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 类用于创建集合，该集合使用哈希表进行存储，该哈希表使用称为哈希的机制。集合的实现类。它继承了[抽象类](https://www.geeksforgeeks.org/abstract-classes-in-java/)，实现了 et [接口](https://www.geeksforgeeks.org/interfaces-in-java/)。主要特点是不允许重复，内部使用哈希表。

**说明:**在 HashSet 中查找最小元素。

**示例:**

```
Input  : [24, 56, 87, 64, 29, 2, 65]
Output : 2

Input  : [45, 3, 65, 32, 64, 12, 43]
Output : 3
```

**方法:**

*   使用每个循环(简单方法)
*   使用 [*集合. min()*](https://www.geeksforgeeks.org/collections-min-method-in-java-with-examples/) 方法的 HashSet(最优方法)

**方法 1:** 使用 for-loop 打印哈希集中的最大元素。

**进场:**

1.  创建哈希集的对象
2.  向创建的对象添加元素
3.  创建一个变量并赋予其值 [MAX_VALUE](https://www.geeksforgeeks.org/integer-max_value-and-integer-min_value-in-java-with-examples/)
4.  对每个循环重复使用

> 记住:
> 
> *   在计算最大值时，将-∞指定为初始最大值
> *   在计算最小分配+∞作为初始最小值时

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to find minimum element on HashSet

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

        // Initially assigning +(infinity) as max value
        // so as to get rid with garbage value issues.
        int min = Integer.MAX_VALUE;

        // For each loop to iterate over elements of HashSet
        // to find minimum among all elements in Set
        for (int var : gfg) {

            // For elements in Set
            if (var < min)

                // Update the minimum element
                min = var;
        }

        // Display final Minimum element in a HashSet
        // i.e after traversing the complete elements
        System.out.println("Minimum element in HashSet = "
                           + min);
    }
}
```

**Output**

```
Elements in HashSet = [64, 65, 2, 87, 24, 56, 29]
Minimum element in HashSet = 2

```

时间复杂度:O(n)，其中 n 是哈希集中的元素数。

**方法二:**使用 [*Collection.min()* 集合类的 HashSet 的](https://www.geeksforgeeks.org/collections-min-method-in-java-with-examples/)方法。

**语法:**

```
public static <T extends Object & Comparable<? super T>> T 
    min(Collection<? extends T> coll)
```

**参数:**该方法将集合 coll 作为一个参数，其最小元素待定

**返回值:**该方法根据元素的自然排序，返回给定集合的最小元素。

**异常:** 此法如果集合为空则抛出[NoSuchElementException](https://www.geeksforgeeks.org/java-util-linkedlist-get-getfirst-getlast-java/)。

**进场:**

1.  创建哈希集的对象
2.  向创建的对象添加元素
3.  使用 *Collection.min()* 方法显示创建后生成的非重复列表中最小的字符串。注意，不会有单一的重复元素。

**例 2**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to find minimum element on HashSet

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

        // Creating object of HashSet
        // Declaring String type objects
        HashSet<String> gfg = new HashSet<String>();

        // Adding element in above object of HashSet
        // Custom inputs
        gfg.add("Geekss");
        gfg.add("Geeks");
        gfg.add("Geek");

        // Print and display all elements inside the object
        // as. inserted above
        System.out.println("Elements in HashSet = " + gfg);

        // Using Collection.min() Method to find
        // minimum string in HashSet
        Object obj = Collections.min(gfg);

        // Display Maximum element in a HashSet
        System.out.println("Minimum String in a HashSet :"
                           + obj);
    }
}
```

**Output**

```
Elements in HashSet = [Geekss, Geek, Geeks]
Minimum String in a HashSet :Geek

```