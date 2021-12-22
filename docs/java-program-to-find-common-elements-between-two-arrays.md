# 寻找两个数组间公共元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-查找-两个数组之间的公共元素/](https://www.geeksforgeeks.org/java-program-to-find-common-elements-between-two-arrays/)

给定两个数组，我们的任务是找到它们的公共元素。
**例:**

```java
Input:  Array1 = ["Article", "for", "Geeks", "for", "Geeks"], 
        Array2 = ["Article", "Geeks", "Geeks"]
Output: [Article,Geeks]

Input:  Array1 = ["a", "b", "c", "d", "e", "f"], 
        Array2 = ["b", "d", "e", "h", "g", "c"]
Output: [b, c, d, e]
```

### **使用迭代方法**

**进场:**

1.  获取两个 java 数组。
2.  逐个迭代数组中的每个元素，并检查它们在两者中是否相同。
3.  为唯一条目添加集合中的每个公共元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to find common elements
// in two Arrays
// Using iterative method

import java.io.*;
import java.util.*;

class GFG {
    private static void FindCommonElemet(String[] arr1,
                                         String[] arr2)
    {
        Set<String> set = new HashSet<>();
        for (int i = 0; i < arr1.length; i++) {
            for (int j = 0; j < arr2.length; j++) {
                if (arr1[i] == arr2[j]) {

                    // add common elements
                    set.add(arr1[i]);
                    break;
                }
            }
        }
        for (String i : set) {
            System.out.print(i + " ");
        }
    }

    // main method
    public static void main(String[] args)
    {

        // create Array 1
        String[] arr1
            = { "Article", "in", "Geeks", "for", "Geeks" };

        // create Array 2
        String[] arr2 = { "Geeks", "for", "Geeks" };

        // print Array 1
        System.out.println("Array 1: "
                           + Arrays.toString(arr1));

        // print Array 2
        System.out.println("Array 2: "
                           + Arrays.toString(arr2));

        System.out.print("Common Elements: ");

        // Find the common elements
        FindCommonElemet(arr1, arr2);
    }
}
```

**Output**

```java
Array 1: [Article, in, Geeks, for, Geeks]
Array 2: [Geeks, for, Geeks]
Common Elements: Geeks for 
```

**时间复杂度:** O(n^2)

#### 使用哈希集:

通过使用 [**HashSet**](https://www.geeksforgeeks.org/hashset-in-java/) 的**retainal()**方法，我们可以找到两个数组之间的公共元素。

**语法:**

```java
// This method keeps only the common elements
// of both Collection in Collection1.

Collections1.retainAll(Collections2)
```

**进场:**

1.  获取两个数组。
2.  创建两个 hashsets，并将数组中的元素添加到这些集合中。
3.  使用**collection . retainal()方法**找出两组中的公共元素。此方法只保留集合 1 中两个集合的公共元素。
4.  集合 1 现在只包含公共元素。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to find common elements
// in two Arrays using hashsets
// and retainAll() method
import java.io.*;
import java.util.*;

class GFG {

    // function to create hashsets
    // from arrays and find
    // their common element
    public static void FindCommonElements(int[] arr1,
                                          int[] arr2)
    {
        // create hashsets
        Set<Integer> set1 = new HashSet<>();
        Set<Integer> set2 = new HashSet<>();

        // Adding elements from array1
        for (int i : arr1) {
            set1.add(i);
        }

        // Adding elements from array2
        for (int i : arr2) {
            set2.add(i);
        }

        // use retainAll() method to
        // find common elements
        set1.retainAll(set2);
        System.out.println("Common elements- " + set1);
    }

    // main method
    public static void main(String[] args)
    {
        // create Array 1
        int[] arr1
            = { 1, 4, 9, 16, 25, 36, 49, 64, 81, 100 };

        // create Array 2
        int[] arr2 = { 100, 9, 64, 7, 36, 5, 16, 3, 4, 1 };

        // print Array 1
        System.out.println("Array 1: "
                           + Arrays.toString(arr1));
        // print Array 2
        System.out.println("Array 2: "
                           + Arrays.toString(arr2));
        FindCommonElements(arr1, arr2);
    }
}
```

**Output**

```java
Array 1: [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
Array 2: [100, 9, 64, 7, 36, 5, 16, 3, 4, 1]
Common elements- [16, 64, 1, 4, 36, 100, 9]

```

**时间复杂度:** O(n)
**使用 HashSet:**

**进场:**

1.将第一个数组的所有元素添加到 hashset 中。

2.迭代第二个数组，并使用 contains 方法检查 hashset 中是否存在元素。如果 contains == true，则将元素添加到结果数组中。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program for the above approach
import java.io.*;
import java.util.Arrays;
import java.util.HashSet;
import java.util.Set;

class Test {

    private static void findCommonElements(int[] arr1,
                                           int[] arr2)
    {

        // Check if length of arr1 is greater than 0
        // and length of arr2 is greater than 0
        if (arr1.length > 0 && arr2.length > 0) {
            Set<Integer> firstSet = new HashSet<Integer>();
            for (int i = 0; i < arr1.length; i++) {
                firstSet.add(arr1[i]);
            }

            // Iterate the elements of the arr2
            for (int j = 0; j < arr2.length; j++) {
                if (firstSet.contains(arr2[j])) {
                    System.out.println(arr2[j]);
                }
            }
        }
    }

    // Driver Code
    public static void main(String[] args)
    {
        int[] arr1 = new int[] { 1, 2, 3, 4, 5, 6, 7 };
        int[] arr2 = new int[] { 1, 3, 4, 5, 6, 9, 8 };

        // Function Call
        findCommonElements(arr1, arr2);
    }
}
```

**Output**

```java
1
3
4
5
6

```

**时间复杂度** : O(n)