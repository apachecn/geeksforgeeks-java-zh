# 在 Java 中展平嵌套集合

> 原文:[https://www . geesforgeks . org/扁平化-嵌套-集合-in-java/](https://www.geeksforgeeks.org/flattening-nested-collections-in-java/)

一个[流](https://www.geeksforgeeks.org/stream-in-java/)是一个支持各种方法的对象序列，这些方法可以被流水线化以产生期望的结果。流用于根据流水线方法计算元素，而不改变对象的原始值。而且，扁平化意味着将两个或多个集合合并成一个集合。考虑下图，其中我们有一个包含 3 个数组的数组，但是经过展平效果后，我们将有一个结果数组，其中所有元素都在三个数组中。

插图:

```java
Input      : arr1[]  = {{1,2,3,4},{5,6,7},{8,9}}; 
Processing : Flattening
Output     : arr1[]  = {1,2,3,4,5,6,7,8,9};
```

Stream **flatMap()** 方法用于将集合流展平为对象流。这些对象是从原始流中的所有集合组合而成的。 **flatMap()** 方法是对流的元素进行一对多的转换，然后将生成的元素展平为一个新的流。基本上 **Stream.flatMap()** 方法有助于将**Stream<Collection<T>>**转换为 **Stream < T >** 。

**示例 1:** 使用 flatMap()方法展平两个相同类型数组的流

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Flatten a map containing a list of items
// as values using flatMap() method

// Importing input output classes
import java.io.*;
// Importing desired classes from java.util package
import java.util.*;
import java.util.stream.Collectors;
import java.util.stream.Stream;

// Main class
public class GFG {

    // Method 1
    // To flatten a map containing a list of items as values
    public static <T> Stream<T>
    flatten(Collection<List<T> > values)
    {

        // Stream.flatMap() method converts
        // Stream<Collection<T>> to the  Stream<T>
        Stream<T> stream
            = values.stream().flatMap(x -> x.stream());

        // Return the desired stream
        return stream;
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of Map class
        // Declaring object of integer and string type
        Map<Integer, List<String> > map = new HashMap<>();

        // Adding elements to the above Map object
        // Custom input entries
        map.put(1, Arrays.asList("1", "2", "3"));
        map.put(2, Arrays.asList("4", "5", "6"));

        // Creating a List class object holding all elements
        // after flattening
        List<String> s = flatten(map.values())
                             .collect(Collectors.toList());

        // Print and display the above List object
        System.out.println(s);
    }
}
```

**Output**

```java
[A, B, C, i, J, K]
```

**示例 2:** 展平两个相同类型列表的流

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to flatten a stream of same type two arrays
// using flatMap() method

// Importing input output classes
import java.io.*;
// Importing Arrays and Stream classes
// from java.util package
import java.util.Arrays;
import java.util.stream.Stream;

// Main class
class GFG {

    // Method 1
    //  To flatten a stream of two arrays of the same type
    public static <T> Stream<T> flatten(T[] a, T[] b)
    {
        // Stream.flatMap() method converts
        // Stream<Collection<T>> to the  Stream<T>
        Stream<T> stream
            = Stream.of(a, b).flatMap(Arrays::stream);

        // Returns the desired stream
        return stream;
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Input array of strings

        // Array 1 has uppercase characters
        String[] a = { "A", "B", "C" };

        // Array 2 has lowercase characters
        String[] b = { "i", "J", "K" };

        // Calling the above method in the main() method
        String[] s = flatten(a, b).toArray(String[] ::new);

        // Return string representation of contents
        // of integer array
        System.out.println(Arrays.toString(s));
    }
}
```

**Output**

```java
[Ma, Rs, Xy, Jw, Pi, Br]
```

**示例 3:** 使用 flatMap()方法展平包含项目列表作为值的地图

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Flatten a map containing a list of items
// as values using flatMap() method

// Importing input output classes
import java.io.*;
// Importing desired classes from java.util package
import java.util.*;
import java.util.stream.Collectors;
import java.util.stream.Stream;

// Main class
public class GFG {

    // Method 1
    // To flatten a map containing a list of items as values
    public static <T> Stream<T>
    flatten(Collection<List<T> > values)
    {

        // Stream.flatMap() method converts
        // Stream<Collection<T>> to the  Stream<T>
        Stream<T> stream
            = values.stream().flatMap(x -> x.stream());

        // Return the desired stream
        return stream;
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of Map class
        // Declaring object of integer and string type
        Map<Integer, List<String> > map = new HashMap<>();

        // Adding elements to the above Map object
        // Custom input entries
        map.put(1, Arrays.asList("1", "2", "3"));
        map.put(2, Arrays.asList("4", "5", "6"));

        // Creating a List class object holding all elements
        // after flattening
        List<String> s = flatten(map.values())
                             .collect(Collectors.toList());

        // Print and display the above List object
        System.out.println(s);
    }
}
```

**Output**

```java
[1, 2, 3, 4, 5, 6]
```