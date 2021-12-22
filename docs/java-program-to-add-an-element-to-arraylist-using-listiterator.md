# 使用列表迭代器向数组列表添加元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-add-a-element-to-ArrayList-use-listiterator/](https://www.geeksforgeeks.org/java-program-to-add-an-element-to-arraylist-using-listiterator/)

在本文中，我们将学习如何使用列表迭代器向[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)添加元素。列表迭代器用于返回列表元素的列表迭代器。[列表迭代器()](https://www.geeksforgeeks.org/arraylist-listiterator-method-in-java-with-examples/)从开始返回列表的迭代器，但是**T5[列表迭代器(索引)](https://www.geeksforgeeks.org/arraylist-listiterator-method-in-java-with-examples/)从给定的索引返回列表的迭代器。**

**语法:**

> // listIterator()方法从列表的开头返回一个迭代器
> 
> 列表迭代器 <integer>it = list.listIterator()</integer>
> 
> // listIterator(index)方法从给定的索引返回列表的迭代器
> 
> ListIterator <integer>它= list . ListIterator(index)；</integer>

**返回值:** 这个方法在这个列表中的元素上返回一个 **列表迭代器** (按适当的顺序)。

**方法:**要使用 Java ListIterator 向数组列表中添加元素，该过程分为两部分:

**1。**做一个迭代器。

```java
ListIterator<Integer> it = list.listIterator()
```

**2。**使用 Add()方法添加元素。

```java
it.add(element)
```

下面是上述方法的实现:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to add elements to ArrayList using
// ListIterator

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // New empty ArrayList
        List<Integer> list = new ArrayList<>();

        // Add elements to ArrayList
        list.add(10);
        list.add(20);
        list.add(30);

        // Print ArrayList before add 50
        System.out.println("Before add 50: " + list);

        // ListIterator
        ListIterator<Integer> it = list.listIterator();

        // iterate ArrayList and add 50 to ArrayList
        while (it.hasNext()) {
            // add 50 to ArrayList
            it.add(50);
            // move iterator
            it.next();
        }

        // Print ArrayList after add 50
        System.out.println("After add 50: " + list);
    }
}
```

**Output**

```java
Before add 50: [10, 20, 30]
After add 50: [50, 10, 50, 20, 50, 30]
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to add elements to ArrayList using
// ListIterator

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // New empty ArrayList
        List<Integer> list = new ArrayList<>();

        // Add elements to ArrayList
        list.add(10);
        list.add(20);
        list.add(30);

        // Print ArrayList before add 50
        System.out.println("Before add 50: " + list);

        // Returns an iterator over the list from the given
        // index
        ListIterator<Integer> it = list.listIterator(1);

        // iterate ArrayList and add 50 to ArrayList
        while (it.hasNext()) {
            // add 50 to ArrayList
            it.add(50);
            // move iterator
            it.next();
        }

        // Print ArrayList after add 50
        System.out.println("After add 50: " + list);
    }
}
```

**Output**

```java
Before add 50: [10, 20, 30]
After add 50: [10, 50, 20, 50, 30]
```