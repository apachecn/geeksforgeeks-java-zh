# Java 数组不匹配()方法示例

> 原文:[https://www . geesforgeks . org/Java-array-mismatch-method-with-examples/](https://www.geeksforgeeks.org/java-array-mismatch-method-with-examples/)

[**Java . util**](https://www.geeksforgeeks.org/java-util-package-java/)**包中的 [**数组**](https://www.geeksforgeeks.org/array-class-in-java/) 类是 Java Collection Framework 的一部分。这个类提供了动态创建和访问 Java 数组的静态方法。它只包含静态方法和对象类的方法。这个类的方法可以由类名本身使用。**

****mismatch()** 是在 Java.util 包的 Arrays 类下定义的方法，它是针对在 mismatch 方法中作为参数传递的两个数组使用的。此方法返回作为参数传递给 mismatch()函数的两个数组具有第一个不相等元素的索引。检查两个数组是否包含相同的对应元素非常有用。当出现不匹配时，这将做出响应。如果两个数组有相同的对应元素，那么这个函数返回-1。我们可以通过下面的例子来理解它的工作原理:**

**给我们两个数组，array1 = {2，6，1，10}和 array2 = {2，6，11，12}，我们想找到 array1 和 array2 具有第一个不等元素的索引。由于前两个索引具有相同的对应元素集，因此索引为 2。**

**借助 mismatch()方法，我们可以在不迭代数组的情况下完成上述任务。**

****语法:****

```java
Arrays.mismatch(first_array, second_array);
```

****参数:**上述方法接受以下参数:**

> ****1。** first_array:特定数据类型的数组(第一个数组名)。**
> 
> ****2。** second_array:同类型的另一个数组(第二个数组名)。**

****返回值:****

> ****1。-1:** 如果两个数组在所有对应的位置都有相同的元素。**
> 
> ****2。非负整数:**两个数组都有第一个不相等元素的索引。**

> ****注意:**两个数组的数据类型必须相同，此方法遵循从零开始的索引。**

****例 1:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate the working of
// mismatch() method with arrays of integer type

// Including necessary import statements
import java.io.*;
import java.util.Arrays;

class GFG {
    public static void main(String[] args)
    {

        // Initializing an integer array
        int array1[] = { 2, 7, 11, 22, 37 };

        // Initializing another array
        int array2[] = { 2, 7, 11, 22, 37 };

        // Initializing another array
        int array3[] = { 2, 7, 19, 31, 39, 56 };

        // Return the first index at which array1
        // array2 have the different element
        int index1 = Arrays.mismatch(array1, array2);

        // Return the first index at which array1
        // array3 have the different element
        int index2 = Arrays.mismatch(array1, array3);

        // Return the first index at which array2
        // array3 have the different element
        int index3 = Arrays.mismatch(array2, array3);

        // Print the first index at which array1
        // array2 have the different element
        System.out.println(
            "The index at which array1 and array2 have first unequal element: "
            + index1);

        // Print the first index at which array1
        // array3 have the different element
        System.out.println(
            "The index at which array1 and array3 have first unequal element: "
            + index2);

        // Print the first index at which array2
        // array3 have the different element
        System.out.println(
            "The index at which array2 and array3 have first unequal element: "
            + index3);
    }
}
```

****Output**

```java
The index at which array1 and array2 have first unequal element: -1
The index at which array1 and array3 have first unequal element: 2
The index at which array2 and array3 have first unequal element: 2
```** 

****例 2:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate the working of
// mismatch() method with arrays of double type

// Including necessary import statements
import java.io.*;
import java.util.Arrays;

class GFG {
    public static void main(String[] args)
    {

        // Initializing an array containing double values
        double array1[]
            = { 11.21, 22.31, 33.15, 44.18, 55.19, 66.666 };

        // Initializing another array
        double array2[]
            = { 11.21, 22.31, 33.15, 44.18, 55.19, 66.666 };

        // Initializing another array
        double array3[] = { 11.21, 22, 33, 44, 55, 66 };

        // Return the first index at which array1
        // array2 have the different element
        int index1 = Arrays.mismatch(array1, array2);

        // Return the first index at which array1
        // array3 have the different element
        int index2 = Arrays.mismatch(array1, array3);

        // Return the first index at which array2
        // array3 have the different element
        int index3 = Arrays.mismatch(array2, array3);

        // Print the first index at which array1
        // array2 have the different element
        System.out.println(
            "The index at which array1 and array2 have first unequal element: "
            + index1);

        // Print the first index at which array1
        // array3 have the different element
        System.out.println(
            "The index at which array1 and array3 have first unequal element:"
            + index2);

        // Print the first index at which array2
        // array3 have the different element
        System.out.println(
            "The index at which array2 and array3 have first unequal element: "
            + index3);
    }
}
```

****Output**

```java
The index at which array1 and array2 have first unequal element: -1
The index at which array1 and array3 have first unequal element:1
The index at which array2 and array3 have first unequal element: 1
```** 

****例 3:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate the working of
// mismatch() method with arrays of character type

// Including necessary import statements
import java.io.*;
import java.util.Arrays;

class GFG {
    public static void main(String[] args)
    {

        // Initializing an character array
        char array1[] = { 'g', 'e', 'e', 'k', 's' };

        // Initializing another array
        char array2[] = { 'g', 'e', 'e', 'k', 's' };

        // Initializing another array
        char array3[] = { 'g', 'e', 'e', 'k' };

        // Return the first index at which array1
        // array2 have the different element
        int index1 = Arrays.mismatch(array1, array2);

        // Return the first index at which array1
        // array3 have the different element
        int index2 = Arrays.mismatch(array1, array3);

        // Return the first index at which array2
        // array3 have the different element
        int index3 = Arrays.mismatch(array2, array3);

        // Print the first index at which array1
        // array2 have the different element
        System.out.println(
            "The index at which array1 and array2 have first unequal element: "
            + index1);

        // Print the first index at which array1
        // array3 have the different element
        System.out.println(
            "The index at which array1 and array3 have first unequal element: "
            + index2);

        // Print the first index at which array2
        // array3 have the different element
        System.out.println(
            "The index at which array2 and array3 have first unequal element: "
            + index3);
    }
}
```

****Output**

```java
The index at which array1 and array2 have first unequal element: -1
The index at which array1 and array3 have first unequal element: 4
The index at which array2 and array3 have first unequal element: 4
```** 

****例 4:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate the working of
// mismatch() method with arrays of boolean type

// Including necessary import statements
import java.io.*;
import java.util.Arrays;

class GFG {
    public static void main(String[] args)
    {

        // Initializing a boolean array
        boolean array1[] = { true, false, true, false };

        // Initializing another array
        boolean array2[] = { true, false, true, false };

        // Initializing another array
        boolean array3[] = { true, false, false, true };

        // Return the first index at which array1
        // array2 have the different element
        int index1 = Arrays.mismatch(array1, array2);

        // Return the first index at which array1
        // array3 have the different element
        int index2 = Arrays.mismatch(array1, array3);

        // Return the first index at which array2
        // array3 have the different element
        int index3 = Arrays.mismatch(array2, array3);

        // Print the first index at which array1
        // array2 have the different element
        System.out.println(
            "The index at which array1 and array2 have first unequal element: "
            + index1);

        // Print the first index at which array1
        // array3 have the different element
        System.out.println(
            "The index at which array1 and array3 have first unequal element: "
            + index2);

        // Print the first index at which array2
        // array3 have the different element
        System.out.println(
            "The index at which array2 and array3 have first unequal element: "
            + index3);
    }
}
```

****Output**

```java
The index at which array1 and array2 have first unequal element: -1
The index at which array1 and array3 have first unequal element: 2
The index at which array2 and array3 have first unequal element: 2
```**