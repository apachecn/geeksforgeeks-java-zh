# Ints asList()函数|番石榴| Java

> 原文:[https://www . geesforgeks . org/ints-aslist-function-guava-Java/](https://www.geeksforgeeks.org/ints-aslist-function-guava-java/)

番石榴的**T1Ints。asList()** 返回由指定数组支持的固定大小列表。

**语法:**

```java
public static List<Integer> 
    asList(int[] array)

```

**参数:**该方法以*数组*为参数，该数组是支持列表的数组。

**返回值:**这个方法返回一个由指定数组支持的固定大小的列表。

**例 1:**

```java
// Java code to show implementation of
// Guava's Ints.asList() method

import com.google.common.primitives.Ints;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating an integer array
        int arr[] = { 1, 2, 3, 4, 5 };

        // Using Ints.asList() method to wrap
        // the specified primitive Integer array
        // as a List of the Integer type
        List<Integer> myList = Ints.asList(arr);

        // Displaying the elements in List
        System.out.println("List of given array: "
                           + myList);
    }
}
```

**输出:**

```java
List of given array: [1, 2, 3, 4, 5]

```

**例 2:**

```java
// Java code to show implementation of
// Guava's Ints.asList() method

import com.google.common.primitives.Ints;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating an integer array
        int arr[] = { 3, 5, 7 };

        // Using Ints.asList() method to wrap
        // the specified primitive Integer array
        // as a List of the Integer type
        List<Integer> myList = Ints.asList(arr);

        // Displaying the elements in List
        System.out.println("List of given array: "
                           + myList);
    }
}
```

**输出:**

```java
List of given array: [3, 5, 7]

```

**参考:**[https://Google . github . io/guava/releases/22.0/API/docs/com/Google/common/primitives/ints . html # asList-int……-](https://google.github.io/guava/releases/22.0/api/docs/com/google/common/primitives/Ints.html#asList-int...-)