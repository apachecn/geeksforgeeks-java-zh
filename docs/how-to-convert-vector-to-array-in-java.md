# Java 中如何将向量转换成数组？

> 原文:[https://www . geesforgeks . org/如何在 java 中将向量转换为数组/](https://www.geeksforgeeks.org/how-to-convert-vector-to-array-in-java/)

众所周知[数组](https://www.geeksforgeeks.org/array-data-structure/)是一组相似类型的变量，它们被一个共同的名字引用，而另一方面向量基本上属于遗留类，但是现在它与集合完全兼容。在 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中找到，实现 [List](https://www.geeksforgeeks.org/list-interface-java-examples/) 接口，在这里使用 List 接口的所有方法都有优势。现在，问题简单地分解为如何使用这些方法，这些方法是为了将向量转换为数组而定义的，我们将提出如下方法:

**方法:**

1.  利用向量类的 toArray()方法
2.  使用 toArray(新的 String[vector.size()])方法

让我们先看一个例子，然后再讨论方法，以便快速理解方法。

**插图:**

```java
Input : Vector: ['G', 'e', 'e', 'k', 's'] 
Output: Array: ['G', 'e', 'e', 'k', 's'] 
```

```java
Input : Vector: [1, 2, 3, 4, 5]
Output: Array: [1, 2, 3, 4, 5] 
```

**方法 1:** 使用 Vector 类的 toArray()方法

**进场:**

1.  获取向量。
2.  使用[*到数组()方法*](https://www.geeksforgeeks.org/vector-toarray-method-in-java-with-examples/) 将向量转换为对象数组
3.  使用 [*Arrays.copyOf()方法*](https://www.geeksforgeeks.org/arrays-copyof-in-java-with-examples/) 将对象数组转换为所需类型的数组
4.  将打印件返回阵列。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert Vector to Array

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Method 1
    // To convert Vector to Array
    public static <T>
        Object[] convertVectorToArray(Vector<T> vector)
    {
        // Converting vector to array
        // using toArray() method of Vector class
        Object[] array = vector.toArray();

        // Returning the array
        return array;
    }

    // Method 2
    // Main driver method
    public static void main(String args[])
    {
        // Creating a vector of string type
        Vector<String> vector = new Vector<String>();

        // Adding custom elements using add() method
        vector.add("G");
        vector.add("e");
        vector.add("e");
        vector.add("k");
        vector.add("s");

        // Printing the vector elements
        System.out.println("Vector: " + vector);

        // Converting vector to object array
        Object[] objArray = convertVectorToArray(vector);

        // Converting object array to string array
        String[] array = Arrays.copyOf(
            objArray, objArray.length, String[].class);

        // Lastly printing the string array
        System.out.println("Array: "
                           + Arrays.toString(array));
    }
}
```

**Output:** 

```java
Vector: [G, e, e, k, s]
Array: [G, e, e, k, s]
```

**方法 2:** 使用 toArray(新的 String[vector.size()])方法

**进场:**

1.  创建了矢量字符串类型。
2.  使用添加(E)方法将元素添加到矢量中。
3.  使用 to Array(新字符串[vector.size()])将向量转换为数组。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Convert Vector to Array

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Creating a vector of string type
        Vector<String> vector = new Vector<String>();

        // Adding elements to above object
        // using add() method
        vector.add("G");
        vector.add("e");
        vector.add("e");
        vector.add("k");
        vector.add("s");

        // Printing the elements inside vector
        System.out.println("Vector: " + vector);

        // Converting vector to string array
        String[] array
            = vector.toArray(new String[vector.size()]);

        // Printing the string array
        System.out.println("Array: "
                           + Arrays.toString(array));
    }
}
```

**Output:** 

```java
Vector: [G, e, e, k, s]
Array: [G, e, e, k, s]
```