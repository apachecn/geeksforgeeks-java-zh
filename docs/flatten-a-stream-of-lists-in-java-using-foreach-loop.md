# 使用 forEach 循环展平 Java 中的列表流

> 原文:[https://www . geeksforgeeks . org/flat-a-stream-in-Java-using-foreach-loop/](https://www.geeksforgeeks.org/flatten-a-stream-of-lists-in-java-using-foreach-loop/)

给定一个 Java 中的列表流，任务是使用 forEach()方法展平该流。

**示例:**

```java
Input: lists = [ [1, 2], [3, 4, 5, 6], [8, 9] ]
Output: [1, 2, 3, 4, 5, 6, 7, 8, 9]

Input: lists = [ ['G', 'e', 'e', 'k', 's'], ['F', 'o', 'r'] ] 
Output: [G, e, e, k, s, F, o, r]

```

**进场:**

1.  以 2D 列表的形式获取列表。
2.  创建一个空列表来收集展平的元素。
3.  在 forEach 循环的帮助下，将列表的每个元素转换成流，并将其添加到列表中
4.  现在使用 stream()方法将此列表转换为流。
5.  现在，通过使用 collect()方法将其转换为 list 来展平流。

下面是上述方法的实现:

**示例 1:** 使用整数列表。

```java
// Java program to flatten a stream of lists
// using forEach() method

import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;
import java.util.stream.*;

class GFG {

    // Function to flatten a Stream of Lists
    public static <T> Stream<T> flattenStream(List<List<T> > lists)
    {

        // Create an empty list to collect the stream
        List<T> finalList = new ArrayList<>();

        // Using forEach loop
        // convert the list into stream
        // and add the stream into list
        for (List<T> list : lists) {
            list.stream()
                .forEach(finalList::add);
        }

        // Convert the list into Stream and return it
        return finalList.stream();
    }

    public static void main(String[] args)
    {

        // Get the lists to be flattened.
        List<Integer> a = Arrays.asList(1, 2);
        List<Integer> b = Arrays.asList(3, 4, 5, 6);
        List<Integer> c = Arrays.asList(7, 8, 9);

        List<List<Integer> > arr = new ArrayList<List<Integer> >();
        arr.add(a);
        arr.add(b);
        arr.add(c);

        // Flatten the Stream
        List<Integer> flatList = new ArrayList<Integer>();
        flatList = flattenStream(arr)
                       .collect(Collectors.toList());

        // Print the flattened list
        System.out.println(flatList);
    }
}
```

**Output:**

```java
[1, 2, 3, 4, 5, 6, 7, 8, 9]

```

**示例 2:** 使用字符列表。

```java
// Java program to flatten a stream of lists
// using forEach() method

import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;
import java.util.stream.*;

class GFG {

    // Function to flatten a Stream of Lists
    public static <T> Stream<T> flattenStream(List<List<T> > lists)
    {

        // Create an empty list to collect the stream
        List<T> finalList = new ArrayList<>();

        // Using forEach loop
        // convert the list into stream
        // and add the stream into list
        for (List<T> list : lists) {
            list.stream()
                .forEach(finalList::add);
        }

        // Convert the list into Stream and return it
        return finalList.stream();
    }

    public static void main(String[] args)
    {

        // Get the lists to be flattened.
        List<Character> a = Arrays.asList('G', 'e', 'e', 'k', 's');
        List<Character> b = Arrays.asList('F', 'o', 'r');
        List<Character> c = Arrays.asList('G', 'e', 'e', 'k', 's');

        List<List<Character> > arr = new ArrayList<List<Character> >();
        arr.add(a);
        arr.add(b);
        arr.add(c);

        // Flatten the Stream
        List<Character> flatList = new ArrayList<Character>();
        flatList = flattenStream(arr)
                       .collect(Collectors.toList());

        // Print the flattened list
        System.out.println(flatList);
    }
}
```

**Output:**

```java
[G, e, e, k, s, F, o, r, G, e, e, k, s]

```