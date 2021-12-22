# 从 LinkedHashSet 获取第一个元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-get-first-element-from-link edhashset/](https://www.geeksforgeeks.org/java-program-to-get-the-first-element-from-linkedhashset/)

[LinkedHashSet](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 是集合抽象数据类型(ADT)的实现。它从 [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 类扩展而来，后者又实现了 Set 接口。LinkedHashSet 和 HashSet 之间的区别在于维护元素顺序的属性。[链接列表](https://www.geeksforgeeks.org/linked-list-in-java/)只是一个包含元素序列的容器。根据定义，集合不应包含重复的元素。该属性不一定适用于链接列表 ADT。当元素应该被复制并且必须维护顺序时，应该使用 LinkedHashSet。

**方法:**

基本上有三种标准方法可以从 LinkedHashSet 中获取一个元素，而无需将其更改为**或**不同的数据结构。

1.  将其转换为数组或列表
2.  使用[迭代器](https://www.geeksforgeeks.org/iterators-in-java/)
3.  使用[流](https://www.geeksforgeeks.org/stream-in-java/)

**实现:**从 LinkedHashSet 获取第一个元素

**方法 1:** 将其转换为数组或列表

例子

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Get the First Element from LinkedHashSet
// by converting it to an array or List
// Array is demonstrated below so do with List

// Importing generic java packages
import java.io.*;
import java.lang.*;
import java.util.*;

// Class
public class GFG {
    // Main driver method
    public static void main(String[] args)
        throws java.lang.Exception
    {
        // Creating a LinkedHashMap object
        // Declaring object of Integer type
        LinkedHashSet<Integer> hashSet
            = new LinkedHashSet<Integer>();

        // Adding elements to LinkedHashMap
        hashSet.add(2);
        hashSet.add(1);
        hashSet.add(4);
        hashSet.add(6);
        hashSet.add(8);

        // Condition check using isEmpty() method which
        // holds

        // True till there is a single element in an object
        // is remaining False, when there is no object left
        // or if initially there was no element added
        if (!hashSet.isEmpty()) {
            // Converting the above Map to an array
            Integer arr[] = new Integer[hashSet.size()];
            arr = hashSet.toArray(arr);

            // Accessing the first element by passing 0
            // as an argument which by default
            // accesses and prints out first element
            System.out.println("First element: " + arr[0]);
        }
    }
}
```

**Output**

```java
First element: 2
```

**方法 2:** 使用[迭代器](https://www.geeksforgeeks.org/iterators-in-java/)

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Get the First Element from LinkedHashSet
// Using Iterators

// Importing generic java packages
import java.util.*;
import java.lang.*;
import java.io.*;

// Class
public class GFG {
    // Main driver method
    public static void main(String[] args)
        throws java.lang.Exception
    {
        // Creating a LinkedHashMap
        LinkedHashSet<Integer> hashSet
            = new LinkedHashSet<Integer>();

        // Adding elements to LinkedHashMap
        hashSet.add(1);
        hashSet.add(2);
        hashSet.add(3);
        hashSet.add(4);
        hashSet.add(5);

        // Iterator over LinkedHashMap
        Iterator<Integer> iter = hashSet.iterator();

        if (iter != null && iter.hasNext()) {
            // Display the first element of Map using next()
            // ethod
            System.out.println(
                "First element in LinkedHashSet: "
                + iter.next());
        }
    }
}
```

**Output**

```java
First element in LinkedHashSet: 1
```

**方法 3:** 使用[溪流](https://www.geeksforgeeks.org/stream-in-java/)

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Get the First Element from LinkedHashSet
// Using Streams

// Importing generic java packages
import java.util.*;
import java.lang.*;
import java.io.*;

// Class
class GFG {

    // Main driver method
    public static void main(String[] args) throws java.lang.Exception
    {
        // Creating a LinkedHashMap
        LinkedHashSet<Integer> hashSet
            = new LinkedHashSet<Integer>();

        // Adding elemens to LinkedHashMap
        hashSet.add(1);
        hashSet.add(2);
        hashSet.add(3);
        hashSet.add(4);
        hashSet.add(5);

        // Checking whether Map is empty or not
        if (hashSet.size() == 0)

            // Display message
            System.out.println("The Set is Empty!");
        else {
            // Using stream() through findFirst() method
            // over the elements of LinkedHashMap
            int first = hashSet.stream().findFirst().get();

            // Printing the first element of LinkedHashMap
            System.out.println(
                "First element in LinkedHashSet: " + first);
        }
    }
}
```

**Output**

```java
First element in LinkedHashSet: 1
```