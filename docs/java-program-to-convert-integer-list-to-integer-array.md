# 将整数列表转换为整数数组的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-转换-整数-列表-整数-数组/](https://www.geeksforgeeks.org/java-program-to-convert-integer-list-to-integer-array/)

有许多方法可以将整数列表转换为数组列表，在本文中，我们将讨论以下两种方法:

1.  在 Java8 中使用概念 od 流
2.  使用 Apache Commons Lang
3.  使用番石榴图书馆

**方法 1:** [在 Java8](https://www.geeksforgeeks.org/streams-arrays-java-8/) 中使用概念 od 流

因此，首先，我们将了解如何使用 java 8 将整数列表转换为数组列表。在 java 8 中，提供了一个流，用于将整数列表转换为整数数组。

**程序:**

*   使用 List . Stream()-> List 正在调用 Stream()方法，将 List <integer>转换为 Stream <integer>。</integer></integer>
*   现在我们将流<integer>转换为 int[]。</integer>

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert Integer List to Integer Array

// Importing Arrays and List classes
// from java.util package
import java.util.Arrays;
import java.util.List;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an List of integer type and
        // customly inserting input elements a arguments
        List<Integer> list = Arrays.asList(1, 3, 5, 7, 9);

        // Converting Stream<Integer> to integer array
        // using stream() and mapToInt() methods, lately
        // storing them in an integer array
        int[] primitive = list.stream()
                              .mapToInt(Integer::inValue)
                              .toArray();

        // Print and display the integer array
        System.out.println(Arrays.toString(primitive));
    }
}
```

**输出:**

```java
[1,3,5,7,9]
```

**方法 2:** [使用 Apache Commons Lang](https://www.geeksforgeeks.org/how-to-clone-a-list-in-java/)

Apache Commons Lang 的 ArrayUtils 类提供了 ***toPrimitive()方法*** ，可以将整数数组转换为基元整数。我们需要首先将整数列表转换成整数数组。我们可以使用 List.toArray()来方便转换。

**程序:**

1.  使用阿帕奇常用郎的 topprimary()方法
2.  使用 List.toArray()方法

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert Integer List to Integer Array

// Importing ArrayUtis class
// Importing Arrays and List class from java.util package
import java.util.Arrays;
import java.util.List;
import org.apache.commons.lang3.ArrayUtils;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of List class of integer type
        List<Integer> list = Arrays.asList(1, 2, 3, 4, 5);

        // Using toPrimtive() method of Apache Common Lang's
        int[] primitive = ArrayUtils.toPrimitive(
            list.toArray(new Integer[0]));

        // Print and display the integer array
        System.out.println(Arrays.toString(primitive));
    }
}
```

**输出:**

```java
[1,2,3,4,5]
```

**方法 3:** [使用番石榴库](https://www.geeksforgeeks.org/guava-library-java/)

Guava library 是一个开源的分散软件开发模型，它是 java 的一组公共库，为收集、缓存、原语支持、并发、字符串处理和验证提供实用方法。这里，我们将通过将整数列表转换为整数数组来浏览番石榴库中的字符串处理。下面的例子描述如下:

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert List to Integer Array
// Using Guava Library

// Importing required classes
import com.google.common.primitives.Ints;
import java.util.Arrays;
import java.util.List;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of List class of integer type
        List<Integer> ints = Arrays.asList(3, 7, 8, 6, 1);

        // Converting a list of Integer to primitive integer
        // array and storing in integer array
        int[] primitive = Ints.toArray(ints);

        // Print and display the integer array via Guava
        // by converting it to string
        // via standard toString() method
        System.out.println(Arrays.toString(primitive));
    }
}
```

**输出:**

```java
3,7,8,6,1
```