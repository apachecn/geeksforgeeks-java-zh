# 比较集合中元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序比较-集合中的元素/](https://www.geeksforgeeks.org/java-program-to-compare-elements-in-a-collection/)

A [集合](https://www.geeksforgeeks.org/collections-in-java-2/) 是以单个单位表示的一组个体对象。Java 提供了 [集合框架](https://www.geeksforgeeks.org/java-collection-tutorial/) ，定义了几个类和接口，将一组对象表示为一个单元。

**例:**

```
Input : List = [3, 5, 18, 4, 6]
Output:
Min value of our list : 3
max value of our list : 18

Input : List = ['a', 'a', 'a']
Output:
All elements are equal
```

**进场:**

1.  Take the input from the list.
2.  Create two variables, minimum and maximum.
3.  Use the [collections.min ()](https://www.geeksforgeeks.org/collections-min-method-in-java-with-examples/) method to store the return value in the min variable.
4.  Use the [collections.max ()](https://www.geeksforgeeks.org/collections-max-method-in-java-with-examples/) method to store the return value in the max variable.
5.  If the minimum and maximum variables are equal, the equal elements are printed.
6.  Otherwise, the minimum and maximum variables are printed.

下面是上述方法的实现:

T3】JavaT5

```
// Java Program to Compare Elements in a Collection
import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // List initialization
        List<Integer> l = new ArrayList<>();

        // Add elements in the list
        l.add(3);
        l.add(5);
        l.add(18);
        l.add(4);
        l.add(6);

        // Minimum in the list
        int minimum = Collections.min(l);

        // Maximum in the list
        int maximum = Collections.max(l);

        if (minimum == maximum) {
            System.out.println("All elements are equal");
        }
        else {
            System.out.println("Min value of our list : "
                               + minimum);
            System.out.println("Max value of our list : "
                               + maximum);
        }
    }
}
```

T6T8**输出**T1

**时间复杂度:** O(N)，其中 N 为列表长度。