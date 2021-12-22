# 在 Java 中以逆序迭代列表

> 原文:[https://www . geesforgeks . org/iterate-list-in-reverse-order-in-Java/](https://www.geeksforgeeks.org/iterate-list-in-reverse-order-in-java/)

[列表界面](https://www.geeksforgeeks.org/list-interface-java-examples/) 提供了一种存储订购集合的方式。是 [集合](https://www.geeksforgeeks.org/collections-in-java-2/) 的子界面。它是对象的有序集合，其中可以存储重复的值。因为列表保留了插入顺序，所以它允许元素的位置访问和插入。

**例**

```java
Input: ["geeks", "for", "Geeks"]
Output: ["Geeks", "for", "geeks"]

Input: [ 1, 2, 3, 4, 5]
output: [5, 4, 3, 2, 1]
```

**我们可以通过两种方式以相反的顺序迭代列表:**

1.  使用 List.listIterator() 和使用进行循环的方法。
2.  使用 IntStream 范围(int startInclusive，int endExclusive)。

**方法 1:** 使用[**list . listiterator()**](https://www.geeksforgeeks.org/arraylist-listiterator-method-in-java-with-examples/)**并使用**进行循环**方法。**

****语法:****

```java
public ListIterator listIterator()
```

****返回值:**这个方法在这个列表的元素上返回一个**列表迭代器**(按照正确的顺序)。**

*   **这允许双向访问。**
*   **List.listIterator()方法用于从列表中的指定位置开始，获取列表中元素的列表迭代器。如果我们需要从最后一个元素开始，开始的索引将等于列表的大小。**

****语法:****

```java
ListIterator<Integer> listIterator( Index )

Index = Index from where list element will reverse till index = 0.
```

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to iterate List in Reverse Order

import java.util.*;

class GFG {

    public static void main(String[] args)
    {

        // For ArrayList
        List<String> list = new ArrayList<String>();

        // Add elements to list
        list.add("GEEKS");
        list.add("for");
        list.add("geeks");

        // Generate an iterator to iterate List in reverse
        // order
        ListIterator<String> gfg_itr
            = list.listIterator(list.size());

        // hasPrevious() returns true if the list has
        // previous element
        while (gfg_itr.hasPrevious()) 
        {
            // Iterate in reverse
            System.out.println(gfg_itr.previous());
        }

        // print list in Reverse using for loop
        for (int i = list.size() - 1; i >= 0; i--)
        {
            // access elements by their index (position)
            System.out.println(list.get(i));
        }
    }
}
```

****Output**

```java
geeks
for
GEEKS
geeks
for
GEEKS
```** 

****方法 2:** 使用 [**IntStream 范围(int startInclusive，int endExclusive)**](https://www.geeksforgeeks.org/intstream-range-java/)**

*   **这将返回一个从 startInclusive(包含)到 endExclusive(排除)的顺序有序 IntStream，增量为 1。它可以正确处理溢出。**

****语法:****

```java
static IntStream range(int startInclusive,   int endExclusive)
```

****参数:****

*   ****IntStream :** 一系列原始的 int 值元素。**
*   ****开始包含:**包含初始值。**
*   ****endExclusive** :独占上限。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java Program to iterate List in reverse order

import java.util.*;
import java.util.stream.IntStream;

class GFG {

    public static void main(String[] args)
    {

        // For ArrayList
        List<Integer> list_li = new ArrayList<Integer>();

        // Add elements to list
        list_li.add(1);
        list_li.add(2);
        list_li.add(3);
        list_li.add(4);
        list_li.add(5);

        // Creating an IntStream
        IntStream stream = IntStream.range(0, list_li.size());

        // Displaying the elements in range
        // including the lower bound but
        // excluding the upper bound
        stream.map(i -> list_li.size() - i - 1).map(list_li::get)
            .forEach(System.out::println);
    }
}
```

****Output**

```java
5
4
3
2
1
```** 

****注意:**int stream range(int startInclusive，int endExclusive)基本上像 for 循环一样工作。递增值的等价序列可以按如下顺序产生:**

```java
for (int i = startInclusive; i < endExclusive ; i++) 
{
 ...
 ...
 ...
}
```