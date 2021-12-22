# 如何使用 Java 8 从数组列表中获取唯一值？

> 原文:[https://www . geesforgeks . org/如何使用-java-8/](https://www.geeksforgeeks.org/how-to-get-unique-values-from-arraylist-using-java-8/) 从数组列表中获取唯一值

Java 中的[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)不防止列表有重复值。但是如果你想从数组列表中获得唯一的值，有几种方法，每种方法都用一个例子来解释。

**方法 1(使用 Stream API 的 distinct()方法):**对于 Java 8，可以使用 Java 8 Stream API。为了获得不同的值， [distinct()](https://www.geeksforgeeks.org/stream-distinct-java/) 方法是一个中间操作，它也过滤流以通过下一个操作。Java Stream **collect()** 用于将流元素收集到一个集合中(在本例中是一个列表)。

**语法:**

```java
Stream<T> distinct()
```

**返回类型**:流是一个接口和函数。它返回一个由不同元素组成的流。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// how to Get Unique Values from ArrayList

import java.util.*;
import java.util.stream.Collectors;

public class Main {

    public static void main(String[] args)
    {

        // Create ArrayList of Integers
        ArrayList<Integer> Numbers
            = new ArrayList<Integer>();

        // add elements to ArrayList
        Numbers.add(1);
        Numbers.add(2);
        Numbers.add(1);
        Numbers.add(4);
        Numbers.add(2);

        List<Integer> UniqueNumbers
            = Numbers.stream().distinct().collect(
                Collectors.toList());

        System.out.println("Unique Values of ArrayList");

        // iterate through List
        for (int i = 0; i < UniqueNumbers.size(); ++i) {
            System.out.println(UniqueNumbers.get(i));
        }
    }
}
```

**Output**

```java
Unique Values of ArrayList
1
2
4
```

**方法 2(使用 HashSet):** 可以将**数组列表**转换为不允许重复值的 [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 。对于转换，使用接受集合作为参数的 HashSet 类的构造函数。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// how to Get Unique Values from ArrayList

import java.util.ArrayList;
import java.util.HashSet;

public class Main {

    public static void main(String[] args)
    {

        // Create ArrayList of Integer
        ArrayList<Integer> Numbers
            = new ArrayList<Integer>();

        // add elements to ArrayList
        Numbers.add(1);
        Numbers.add(2);
        Numbers.add(1);
        Numbers.add(4);
        Numbers.add(2);

        /*Converting List to HashSet using constructor.
         */

        HashSet<Integer> hashSetNumbers
            = new HashSet<Integer>(Numbers);

        System.out.println("Unique Values of ArrayList");

        // iterate through HashSet
        for (Integer strNumber : hashSetNumbers)
            System.out.println(strNumber);
    }
}
```

**Output**

```java
Unique Values of ArrayList
1
2
4
```

**保持数组列表中没有重复元素插入的顺序。**

[LinkedHashSet](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 是 HashSet 的一个有序版本，在所有元素之间维护一个双向链表。让我们按照元素被插入的顺序迭代它们。下面是保持插入顺序并且不允许重复元素的代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Maintaining order with no duplicate elements insertion in
// the ArrayList.

import java.util.*;

public class Main {

    public static void main(String[] args)
    {

        // Using LinkedHashSet we can prevent
        // insertion of duplicate elements
        // as it implements the Set interface
        LinkedHashSet<Integer> UniqueList
            = new LinkedHashSet<Integer>();

        // Adding elements to LinkedHashSet
        UniqueList.add(1);
        UniqueList.add(2);
        UniqueList.add(3);
        UniqueList.add(3); // duplicate 3 wont be inserted
        UniqueList.add(2); // duplicate 2 wont be inserted

        // Converting LinkedHashSet to List
        List<Integer> ls
            = new ArrayList<Integer>(UniqueList);

        // Printing list
        System.out.println(ls);
    }
}
```

**Output**

```java
[1, 2, 3]
```