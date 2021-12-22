# 将数组列表转换为链表的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-convert-ArrayList-to-linked list/](https://www.geeksforgeeks.org/java-program-to-convert-arraylist-to-linkedlist/)

给定一个数组列表，您的任务是编写一个程序，将给定的数组列表转换为 Java 中的链表。

**示例:**

```
Input: ArrayList: [Geeks, forGeeks, A computer Portal] 
Output: LinkedList: [Geeks, forGeeks, A computer Portal]
Input: ArrayList: [1, 2, 3, 4, 5] 
Output: LinkedList: [1, 2, 3, 4, 5] 
```

**数组列表–**一个[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)是集合框架的一部分，存在于 **java.util** 包中。它用 Java 为我们提供了动态数组。尽管它可能比标准数组慢，但在需要对数组进行大量操作的程序中会很有帮助。

**链表–**一个[链表](https://www.geeksforgeeks.org/implementing-a-linked-list-in-java-using-class/)是一个线性数据结构，其中元素不存储在连续的内存位置。链表中的元素使用指针链接，如下图所示:

![](img/d97a233bf3c89e80c46e6a3193e851d6.png)

### 方法

在 Java 中，有许多方法可以将给定的数组列表转换成链表。下面列出了其中的一些。

*   使用暴力或天真的方法
*   使用列表构造函数
*   使用 Java 8 流应用编程接口
*   使用谷歌的番石榴图书馆
*   不兼容类型之间的转换

### 1.使用暴力或天真的方法

在这个方法中，创建一个空的链接列表，数组列表中的所有元素都被一个接一个地添加到其中。

**算法**:

*   获取要转换的数组列表。
*   创建一个空的链接列表。
*   遍历数组列表中的项。
*   对于每个项目，将其添加到链接列表中。
*   返回形成的链接列表。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to convert
// ArrayList to LinkedList 
// using Naive method

import java.util.*;
import java.util.stream.*;

class GFG {

    // Generic function to convert an ArrayList to LinkedList
    public static <T> List<T> convertALtoLL(List<T> aL)
    {

        // Create an empty LinkedList
        List<T> lL = new LinkedList<>();

        // Iterate through the aL
        for (T t : aL) {

            // Add each element into the lL
            lL.add(t);
        }

        // Return the converted LinkedList
        return lL;
    }

    public static void main(String args[])
    {
        // Create an ArrayList
        List<String> aL = Arrays.asList("Geeks",
                                    "forGeeks",
                                    "A computer Portal");

        // Print the ArrayList
        System.out.println("ArrayList: " + aL);

        // convert the ArrayList to LinkedList
        List<String>
            lL = convertALtoLL(aL);

        // Print the LinkedList
        System.out.println("LinkedList: " + lL);
    }
}
```

**Output**

```
ArrayList: [Geeks, forGeeks, A computer Portal]
LinkedList: [Geeks, forGeeks, A computer Portal]
```

### 2.使用列表构造函数

在此方法中，数组列表作为参数传递给链接列表构造函数。

**算法**:

*   获取要转换的数组列表。
*   通过将数组列表作为参数传递给链接列表的构造函数来创建链接列表。
*   返回形成的链接列表。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to convert
// ArrayList to LinkedList
// using List Constructor

import java.util.*;
import java.util.stream.*;

class GFG {

    // Generic function to convert an ArrayList to LinkedList
    public static <T> List<T> convertALtoLL(List<T> aL)
    {

        // Create the LinkedList by passing the ArrayList
        // as parameter in the constructor
        List<T> lL = new LinkedList<>(aL);

        // Return the converted LinkedList
        return lL;
    }

    public static void main(String args[])
    {
        // Create an ArrayList
        List<String> aL = Arrays.asList("Geeks",
                                    "forGeeks",
                                    "A computer Portal");

        // Print the ArrayList
        System.out.println("ArrayList: " + aL);

        // convert the ArrayList to LinkedList
        List<String>
            lL = convertALtoLL(aL);

        // Print the LinkedList
        System.out.println("LinkedList: " + lL);
    }
}
```

**Output**

```
ArrayList: [Geeks, forGeeks, A computer Portal]
LinkedList: [Geeks, forGeeks, A computer Portal]
```

### **3。使用 Java 8 流应用编程接口**

此方法包括将数组列表转换为流，并使用接受收集器的 Stream.collect()方法在链接列表中收集流的元素。

**算法**:

*   获取要转换的数组列表。
*   将数组列表转换为流。
*   使用收集器，收集数组列表流并将其转换为链接列表。
*   现在收集链接列表。
*   返回形成的链接列表。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to convert
// ArrayList to LinkedList
// using Streams API

import java.util.*;
import java.util.stream.*;

class GFG {

    // Generic function to convert an
    // ArrayList to LinkedList
    public static <T> List<T> convertALtoLL(
                                        List<T> aL)
    {

        // Return the converted LinkedList
        return aL

            // Convert the ArrayList into Stream
            .stream()

            // Collect the LinkedList
            .collect(Collectors

            // Convert the Stream into LinkedList
            // Collection type
            .toCollection(LinkedList::new));
    }

    public static void main(String args[])
    {
        // Create an ArrayList
        List<String> aL = Arrays.asList("Geeks",
                                        "forGeeks",
                                        "A computer Portal");

        // Print the ArrayList
        System.out.println("ArrayList: " + aL);

        // convert the ArrayList to LinkedList
        List<String> lL = convertALtoLL(aL);

        // Print the LinkedList
        System.out.println("LinkedList: " + lL);
    }
}
```

**Output**

```
ArrayList: [Geeks, forGeeks, A computer Portal]
LinkedList: [Geeks, forGeeks, A computer Portal]
```

### **4。使用谷歌的番石榴库**

Guava 还提供了一个 LinkedList 实现，可以使用 Collection.addAll()方法从另一个集合创建一个 LinkedList。

**算法**:

*   获取要转换的数组列表。
*   创建一个空的链接列表。
*   使用 LinkedList.addAll()方法并将数组列表作为参数传递，将数组列表的元素添加到链接列表中。
*   返回形成的链接列表。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to convert
// ArrayList to LinkedList
// using Google's Guave library

import java.util.*;
import java.util.stream.*;

class GFG {

    // Generic function to convert an ArrayList
    // to LinkedList
    public static <T> List<T> convertALtoLL(List<T> aL)
    {

        // Create an empty LinkedList
        List<T> lL = new LinkedList<>();

        // Add ArrayList into the lL
        lL.addAll(aL);

        // Return the converted LinkedList
        return lL;
    }

    public static void main(String args[])
    {
        // Create an ArrayList
        List<String> aL = Arrays.asList("Geeks",
                                    "forGeeks",
                                    "A computer Portal");

        // Print the ArrayList
        System.out.println("ArrayList: " + aL);

        // convert the ArrayList to LinkedList
        List<String>
            lL = convertALtoLL(aL);

        // Print the LinkedList
        System.out.println("LinkedList: " + lL);
    }
}
```

**Output**

```
ArrayList: [Geeks, forGeeks, A computer Portal]
LinkedList: [Geeks, forGeeks, A computer Portal]
```

### **5。不兼容类型之间的转换**

如果所需的树映射与哈希映射的类型不同，则可以使用此方法。在这种情况下，转换需要手动完成。

**算法**:

*   获取要转换的数组列表。
*   将数组列表转换为流。
*   通过转换将流元素转换为所需的类型。这可以通过将强制转换函数作为参数传递给 map()函数来实现。
*   使用收集器，收集数组列表流并将其转换为链接列表。
*   现在收集链接列表。
*   返回形成的链接列表。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to convert
// ArrayList to LinkedList for
// Conversion between incompatible types

import java.util.*;
import java.util.stream.*;

class GFG {

    // Generic function to convert an ArrayList to LinkedList
    public static <T> List<String> convertALtoLL(List<T> aL)
    {

        // Return the converted LinkedList
        return aL

            // Convert the ArrayList into Stream
            .stream()

            // Convert the Stream into String
            // Desired casting function can be passed
            // as parameter in next step
            .map(String::valueOf)

            // Collect the LinkedList
            .collect(Collectors

            // Convert the Stream into LinkedList
            // Collection type
            .toCollection(LinkedList::new));
    }

    public static void main(String args[])
    {
        // Create an ArrayList
        List<Integer> aL = Arrays.asList(1, 2, 3, 4, 5);

        // Print the ArrayList
        System.out.println("ArrayList: " + aL);

        // convert the ArrayList to LinkedList
        List<String> lL = convertALtoLL(aL);

        // Print the LinkedList
        System.out.println("LinkedList: " + lL);
    }
}
```

**Output**

```
ArrayList: [1, 2, 3, 4, 5]
LinkedList: [1, 2, 3, 4, 5]
```