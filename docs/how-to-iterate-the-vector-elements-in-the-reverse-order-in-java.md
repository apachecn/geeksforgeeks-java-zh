# 在 Java 中如何逆序迭代向量元素？

> 原文:[https://www . geesforgeks . org/如何以 java 中的逆序迭代向量元素/](https://www.geeksforgeeks.org/how-to-iterate-the-vector-elements-in-the-reverse-order-in-java/)

在 java.util 包中找到了[向量类](https://www.geeksforgeeks.org/java-util-vector-class-java/)，它实现了 List 接口。Vector 类包含在 java 1.2 版本的 Java 集合框架中。与数组不同，向量可以增长和缩小其大小，因此它们也被称为动态数组。向量是[同步的](https://www.geeksforgeeks.org/synchronized-in-java/)，即它们是线程安全的。

基本上有两种方法来以相反的顺序迭代向量元素，虽然还有另一种方法使用 Apache Commons 在向后的方向上向后迭代向量，但是要使用它，我们只需要下载一些 jar 文件和包，而且，系统的大部分不支持 apache-commons。

**我们将使用两种方法:**

1.  使用 For 循环
2.  使用列表迭代器

**方法 1:用于循环**

要使用 for 循环向后迭代向量元素，我们可以通过从索引(向量)运行循环来从向后遍历向量。size()-1)到索引 0。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to traverse the vector elements in backward
// direction

import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // creating a vector of String type
        Vector<String> numbers = new Vector<String>();

        // adding elements to vector
        numbers.add("One");
        numbers.add("Two");
        numbers.add("Three");
        numbers.add("Four");

        // Iterating from index equal to numbers.size()-1to
        // 0 and decrement index by 1 using the for loop

        for (int index = numbers.size() - 1; index >= 0; index--) {
            System.out.println(numbers.get(index));
        }
    }
}
```

**Output**

```java
Four
Three
Two
One

```

**方法二:使用列表迭代器**

向量类有一个列表迭代器方法，用来迭代向量。列表迭代器方法从遍历必须开始的地方获取起始索引，并返回列表迭代器。

*   列表迭代器有向前和向后遍历的方法。由于我们必须向后遍历，所以我们将起始索引作为数组大小传递，然后我们将使用 ListIterator 的 **hasPrevious()** 方法，在该方法中，如果存在，我们将向后元素打印到当前索引。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to traverse the vector elements in backward
// direction using ListIterator

import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // creating a vector of String type
        Vector<String> numbers = new Vector<String>();

        // adding elements to vector
        numbers.add("One");
        numbers.add("Two");
        numbers.add("Three");
        numbers.add("Four");

        // listIterator method will return the list of
        // String of type ListIterator.
        ListIterator<String> listIterator
            = numbers.listIterator(numbers.size());

        // Iterate the ListIterator using the hasPrevious()
        // method

        while (listIterator.hasPrevious()) {

            // if element exist at previous index,then print
            // that element
            System.out.println(listIterator.previous());
        }
    }
}
```

**Output**

```java
Four
Three
Two
One

```