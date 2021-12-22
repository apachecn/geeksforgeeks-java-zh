# 使用 forEach 循环展平 Java 中的数组流

> 原文:[https://www . geeksforgeeks . org/flat-a-stream-in-Java-use-foreach-loop/](https://www.geeksforgeeks.org/flatten-a-stream-of-arrays-in-java-using-foreach-loop/)

给定 Java 中的数组流，任务是使用 forEach()方法展平该流。

**示例:**

```java
Input: arr[][] = {{ 1, 2 }, { 3, 4, 5, 6 }, { 7, 8, 9 }}
Output: [1, 2, 3, 4, 5, 6, 7, 8, 9]

Input: arr[][] = {{'G', 'e', 'e', 'k', 's'}, {'F', 'o', 'r'}}
Output: [G, e, e, k, s, F, o, r]

```

**进场:**

1.  获取 2D 数组形式的数组。
2.  创建一个空列表来收集展平的元素。
3.  在 forEach 循环的帮助下，将数组的每个元素转换成流，并将其添加到列表中
4.  现在使用 stream()方法将此列表转换为流。
5.  现在，通过使用 to array()方法将其转换为数组来展平流。

下面是上述方法的实现:

**示例 1:** 使用整数数组。

```java
// Java program to flatten a stream of arrays
// using forEach() method

import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;
import java.util.stream.Stream;

class GFG {

    // Function to flatten a Stream of Arrays
    public static <T> Stream<T> flattenStream(T[][] arrays)
    {

        // Create an empty list to collect the stream
        List<T> list = new ArrayList<>();

        // Using forEach loop
        // convert the array into stream
        // and add the stream into list
        for (T[] array : arrays) {
            Arrays.stream(array)
                .forEach(list::add);
        }

        // Convert the list into Stream and return it
        return list.stream();
    }

    public static void main(String[] args)
    {

        // Get the arrays to be flattened.
        Integer[][] arr = {
            { 1, 2 },
            { 3, 4, 5, 6 },
            { 7, 8, 9 }
        };

        // Flatten the Stream
        Integer[] flatArray = flattenStream(arr)
                                  .toArray(Integer[] ::new);

        // Print the flattened array
        System.out.println(Arrays.toString(flatArray));
    }
}
```

**Output:**

```java
[1, 2, 3, 4, 5, 6, 7, 8, 9]

```

**示例 2:** 使用字符数组。

```java
// Java program to flatten a stream of arrays
// using forEach() method

import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;
import java.util.stream.Stream;

class GFG {

    // Function to flatten a Stream of Arrays
    public static <T> Stream<T> flattenStream(T[][] arrays)
    {

        // Create an empty list to collect the stream
        List<T> list = new ArrayList<>();

        // Using forEach loop
        // convert the array into stream
        // and add the stream into list
        for (T[] array : arrays) {
            Arrays.stream(array)
                .forEach(list::add);
        }

        // Convert the list into Stream and return it
        return list.stream();
    }

    public static void main(String[] args)
    {

        // Get the arrays to be flattened.
        Character[][] arr = {
            { 'G', 'e', 'e', 'k', 's' },
            { 'F', 'o', 'r' },
            { 'G', 'e', 'e', 'k', 's' }
        };

        // Flatten the Stream
        Character[] flatArray = flattenStream(arr)
                                    .toArray(Character[] ::new);

        // Print the flattened array
        System.out.println(Arrays.toString(flatArray));
    }
}
```

**Output:**

```java
[G, e, e, k, s, F, o, r, G, e, e, k, s]

```