# 使用 Java 中的 Floor 方法获取小于指定元素的 TreeSet 元素

> 原文:[https://www . geesforgeks . org/get-treeset-element-小于指定的元素-使用 java 中的 floor-method/](https://www.geeksforgeeks.org/getting-treeset-element-smaller-than-specified-element-using-floor-method-in-java/)

使用 Java 中的 [floor()方法](https://www.geeksforgeeks.org/treeset-floor-method-in-java-with-examples/)获取小于指定元素的 [**树集**](https://www.geeksforgeeks.org/treeset-in-java/) 元素。TreeSet 用于按排序顺序存储元素。floor 方法返回集合中小于或等于给定元素的最大元素，如果没有这样的元素，则返回 null。

```
set = {10,20,30,40,50}

// greatest element in the set less than or equal to the 23
Floor value of 23: 20

// There is no such element so it returns null
Floor value of 5: null
```

[**Java . util . treeset<E>**](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)类的 **floor()** 方法用于返回该集合中小于或等于给定元素的最大元素，如果没有该元素，则返回 null。

**语法:**

```
public E floor(E e)
```

**参数:**该方法将值 **e** 作为待匹配的参数。

**返回值:**该方法返回小于或等于 e 的**最大元素**，如果没有该元素则返回**空值**

**异常:**如果指定元素为空，并且该集合使用自然排序，或者其比较器不允许空元素，则该方法抛出**空指针异常**。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program demonstrate how to get TreeSet Element
// Smaller than Specified Element using Floor Method 

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // New TreeSet
        TreeSet<Integer> set = new TreeSet<>();

        // Adding element to TreeSet
        set.add(40);
        set.add(50);
        set.add(30);
        set.add(10);
        set.add(20);

        // Print TreeSet
        System.out.println("TreeSet: " + set);

        // Print floor value of 23
        System.out.println("Floor value of 23: "
                           + set.floor(23));
    }
}
```

**Output**

```
TreeSet: [10, 20, 30, 40, 50]
Floor value of 23: 20
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program demonstrate how to get TreeSet Element
// Smaller than Specified Element using Floor Method 

import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // New TreeSet
        TreeSet<Integer> set = new TreeSet<>();

        // Adding element to TreeSet
        set.add(40);
        set.add(50);
        set.add(30);
        set.add(10);
        set.add(20);

        // Print TreeSet
        System.out.println("TreeSet: " + set);

        // Print floor value of 5
        System.out.println("Floor value of 5: "
                           + set.floor(5));
    }
}
```

**Output**

```
TreeSet: [10, 20, 30, 40, 50]
Floor value of 5: null
```