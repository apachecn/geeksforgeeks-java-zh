# Java 中的 Arrays.sort()，示例

> 原文:[https://www . geeksforgeeks . org/arrays-sort-in-Java-with-examples/](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/)

数组类是一个包含静态方法的类，这些静态方法用于数组，以便搜索、排序、比较、插入元素或返回数组的字符串表示形式。在一个数组中。因此，让我们先指定函数，稍后我们将讨论相同的内容。它们如下所示出现在 [java.util.Arrays](https://www.geeksforgeeks.org/array-class-in-java/) 类中。在这里，我们将使用数组类的[排序()方法来讨论不同的图。](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/)

Arrays.sort()方法由两种变体组成，一种是我们不传递任何参数，它对整个数组进行排序，无论是整数数组还是字符数组，但是如果我们要使用 Arrays 类的这个方法对特定部分进行排序，那么我们就重载它，并将开始和最后一个索引传递给数组。

**语法:**排序()方法

```java
Arrays.sort(); 
```

**语法:**重载排序()方法

```java
public static void sort(int[] arr, int from_Index, int to_Index) ;
```

**参数:**从语法上可以看出它有三个参数，如下所示:

*   The array to sort.
*   The index (inclusive) of the first element to sort (called from_index)
*   The index (excluding) of the last element to sort (called last_index)

**返回类型:**不返回值。

现在让我们看看 sort()函数在 Arrays 类的不同场景中的实现，如下所示:

**例 1:**

## 爪哇

```java
// Java Program to Sort Array of Integers
// by Default Sorts in an Ascending Order
// using Arrays.sort() Method

// Importing Arrays class from the utility class
import java.util.Arrays;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Custom input array
        int[] arr = { 13, 7, 6, 45, 21, 9, 101, 102 };

        // Applying sort() method over to above array
        // by passing the array as an argument
        Arrays.sort(arr);

        // Printing the array after sorting
        System.out.println("Modified arr[] : %s",
                           Arrays.toString(arr));
    }
}
```

**输出:**

```java
Modified arr[] : [6, 7, 9, 13, 21, 45, 101, 102]
```

**例 2:**

## 爪哇

```java
// Java program to Sort a Subarray in Array
// Using Arrays.sort() method

// Importing Arrays class from java.util package
import java.util.Arrays;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Custom input array
        // It contains 8 elements as follows
        int[] arr = { 13, 7, 6, 45, 21, 9, 2, 100 };

        // Sort subarray from index 1 to 4, i.e.,
        // only sort subarray {7, 6, 45, 21} and
        // keep other elements as it is.
        Arrays.sort(arr, 1, 5);

        // Printing the updated array which is
        // sorted after 2 index inclusive till 5th index
        System.out.println("Modified arr[] : %s",
                           Arrays.toString(arr));
    }
}
```