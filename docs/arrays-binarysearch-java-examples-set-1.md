# Java 中的 Arrays.binarySearch()示例| Set 1

> 原文:[https://www . geesforgeks . org/arrays-binary search-Java-examples-set-1/](https://www.geeksforgeeks.org/arrays-binarysearch-java-examples-set-1/)

**Arrays.binarySearch()** 方法使用二分搜索法算法在给定数据类型的指定数组中搜索指定值。在进行此调用之前，必须按照 [Arrays.sort()](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/) 方法对数组进行排序。如果没有排序，结果是未定义的。如果数组包含多个具有指定值的元素，则不能保证找到哪一个。让我们浏览下面提供的插图。

**图解:**

```java
Searching for 35 in byteArr[] = {10,20,15,22,35}
will give result as 4 as it is the index of 35

Searching for g in charArr[] = {'g','p','q','c','i'}
will give result as 0 as it is the index of 'g'

Searching for 22 in intArr[] = {10,20,15,22,35};
will give result as 3 as it is the index of 22

Searching for 1.5 in doubleArr[] = {10.2,15.1,2.2,3.5}
will give result as -1 as it is the insertion point of 1.5

Searching for 35.0 in floatArr[] = {10.2f,15.1f,2.2f,3.5f}
will give result as -5 as it is the insertion point of 35.0

Searching for 5 in shortArr[] = {10,20,15,22,35}
will give result as -1 as it is the insertion point of 5
```

> 在 Java 中寻找排序数组中的元素是最简单有效的方法

**语法:**

```java
public static int binarySearch(data_type arr, data_type key)
```

> **记住:**这里的数据类型可以是任何原始数据类型，例如字节、字符、双精度、int、float、short、long，甚至 object。

**参数:**

*   Array to be searched
*   Value to be searched

**返回类型:**搜索关键字的索引，如果包含在数组中；否则，(-(插入点)–1)。插入点定义为将键插入数组的点:大于键的第一个元素的索引，如果数组中的所有元素都小于指定的键，则为. length。请注意，这保证了当且仅当找到密钥时，返回值将为> = 0。

有一些重要的点需要记住如下:

*   If the input list is not sorted, the result is undefined.
*   If there are duplicates, there is no guarantee which one will be found.

如上所述，我们已经讨论过，我们可以通过**arrays . binary search()vs**[**collections . binary search()**](https://www.geeksforgeeks.org/collections-binarysearch-java-examples/)**来操作这个算法。** Arrays.binarysearch()适用于也可以是原始数据类型的数组。[收藏](https://www.geeksforgeeks.org/collections-in-java-2/)。binarysearch()适用于对象集合，如[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)和[链接列表](https://www.geeksforgeeks.org/linked-list-in-java/)。

**例 1:**

## Java

```java
// Java program to demonstrate working of Arrays.
// binarySearch() in a sorted array

// Importing Arrays class from
// java.util package
import java.util.Arrays;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Declaring and initializing byte arrays
        // to search over them
        byte byteArr[] = { 10, 20, 15, 22, 35 };
        char charArr[] = { 'g', 'p', 'q', 'c', 'i' };
        int intArr[] = { 10, 20, 15, 22, 35 };
        double doubleArr[] = { 10.2, 15.1, 2.2, 3.5 };
        float floatArr[] = { 10.2f, 15.1f, 2.2f, 3.5f };
        short shortArr[] = { 10, 20, 15, 22, 35 };

        // Using sort() method of Arrays class
        // and passing arrays to be sorted as in arguments
        Arrays.sort(byteArr);
        Arrays.sort(charArr);
        Arrays.sort(intArr);
        Arrays.sort(doubleArr);
        Arrays.sort(floatArr);
        Arrays.sort(shortArr);

        // Primitive datatypes
        byte byteKey = 35;
        char charKey = 'g';
        int intKey = 22;
        double doubleKey = 1.5;
        float floatKey = 35;
        short shortKey = 5;

        // Now in sorted array array we will fetch and
        // return elements/indiciesaccessing indexes to show
        // array is really sorted

        // Print commands where we are implementing
        System.out.println(
            byteKey + " found at index = "
            + Arrays.binarySearch(byteArr, byteKey));
        System.out.println(
            charKey + " found at index = "
            + Arrays.binarySearch(charArr, charKey));
        System.out.println(
            intKey + " found at index = "
            + Arrays.binarySearch(intArr, intKey));
        System.out.println(
            doubleKey + " found at index = "
            + Arrays.binarySearch(doubleArr, doubleKey));
        System.out.println(
            floatKey + " found at index = "
            + Arrays.binarySearch(floatArr, floatKey));
        System.out.println(
            shortKey + " found at index = "
            + Arrays.binarySearch(shortArr, shortKey));
    }
}
```

**输出**

```java
35 found at index = 4
g found at index = 1
22 found at index = 3
1.5 found at index = -1
35.0 found at index = -5
5 found at index = -1
```

这种方法有多种变体，在这些变体中，我们还可以指定要搜索的数组范围。我们将在以后的文章中讨论这个问题以及在对象数组中进行搜索。

**例 2:**

## Java

```java
// Java Program to Illustrate binarySearch() method
//  of  Collections class

// Importing required classes
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating empty List
        List<Integer> al = new ArrayList<Integer>();

        // Adding elements to the List
        al.add(12);
        al.add(53);
        al.add(23);
        al.add(46);
        al.add(54);

        // Using binarySearch() method of Collections class
        // over random inserted element and storing the
        // index
        int index = Collections.binarySearch(al, 23);

        // Print and display the indedx
        System.out.print(index);
    }
}
```

**输出**

```java
2
```

本文由 **Shikhar** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。