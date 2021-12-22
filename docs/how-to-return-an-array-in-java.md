# 如何在 Java 中返回数组？

> 原文:[https://www . geesforgeks . org/如何返回 java 数组/](https://www.geeksforgeeks.org/how-to-return-an-array-in-java/)

[数组](https://www.geeksforgeeks.org/array-data-structure/)是由一组相同数据类型的元素组成的数据结构，因此数组的每个元素都可以由单个数组索引或键来标识。数组的元素以这样一种方式存储，即任何元素的地址都可以使用简单的数学关系使用数组第一个索引的位置来计算。[与 C/C++中的数组相比，Java 中的数组在实现和用法上有所不同，尽管它们也有许多相似之处。这里我们将讨论如何用 java 返回数组。](https://www.geeksforgeeks.org/arrays-in-java/)

为了在 java 中返回数组，我们需要注意以下几点:

**关键点 1:** 返回数组的方法的返回类型必须与被返回数组的数据类型相同。返回类型可能是通常的整数、双精度、字符、字符串或用户定义的类对象。

```
// Method returning an String array.
int[] methodName() {...}
```

```
// Method returning a String array.
String[] methodName() {...}
```

```
// Method returning an array of objects of class named Students.
Students[] methodName() {...} 
```

**关键点 2:** 考虑到方法和返回数组的用法，必须准确使用访问修饰符。静态和非静态声明也必须考虑在内。

```
// Using public access modifier and static to call the method from a static class, method or block.
public static char[] methodName() {...} 
```

**关键点 3:** 在方法调用中必须有任何相同数据类型或类似的变量数组来处理返回的数组。例如，从任何方法返回的整数数组都可以存储如下。

```
int[] storage = methodReturningArray();
```

**实施:**

为了更好地理解这一点，我们可以研究几种可能返回数组的不同场景。这里我们将考虑三个场景示例。

*   Case 1: Simple built-in array
*   Situation 2: Object array
*   Situation 3:

**情况 1:** 在 java 中返回一个整数(内置数据类型)数组

任何内置数据类型的数组，无论是整数、字符、浮点还是双精度，都可以简单地使用 return 语句返回，记住上面列出的几点。

**示例**

## Java

```
// Java Program to Illustrate Returning
// simple built-in arrays

// Importing input output classes
import java.io.*;

// Main class
class GFG {

    // Method 1
    // Main driver method
    public static void main(String[] args)
    {
        // An integer array storing the returned array
        // from the method
        int[] storage = methodReturningArray();

        // Printing the elements of the array
        for (int i = 0; i < storage.length; i++)
            System.out.print(storage[i] + " ");
    }

    // Method 2
    // Returning an integer array
    public static int[] methodReturningArray()
    {
        int[] sample = { 1, 2, 3, 4 };

        // Return statement of the method.
        return sample;
    }
}
```

**输出**

```
1 2 3 4 
```

**情况 2:** 返回 java 中的对象数组

在返回内置数据类型数组的情况下，这完全是以类似的方式完成的。

**示例**

## Java

```
// Java Program to Illustrate Returning
// an array of objects in java

// Importing all input output classes
import java.io.*;

// Class 1
// Helper class
// Courses whose objects are returned as an array
class Courses {

    String name;
    int modules;

    // Constructor to instantiate class objects.
    public Courses(String n, int m)
    {
        // This keyword refers to current instance  itself
        this.name = n;
        this.modules = m;
    }
}

// Class 2
// Main class
class GFG {

    // Method 1
    // Main driver method
    public static void main(String[] args)
    {
        // Calling the method for returning an array of
        // objects of the Courses class.
        Courses[] sample = methodReturningArray();

        // Printing the returned array elements.
        for (int i = 0; i < sample.length; i++)
            System.out.print(sample[i].name + " - "
                             + sample[i].modules
                             + " modules\n");
    }

    // Method 2
    // Note that return type is an array
    public static Courses[] methodReturningArray()
    {
        // Declaring Array of objects of the Courses class
        Courses[] arr = new Courses[4];

        // Custom array of objects
        arr[0] = new Courses("Java", 31);
        arr[1] = new Courses("C++", 26);
        arr[2] = new Courses("DSA", 24);
        arr[3] = new Courses("DBMS", 12);

        // Statement to return an array of objects
        return arr;
    }
}
```

**输出**

```
Java - 31 modules
C++ - 26 modules
DSA - 24 modules
DBMS - 12 modules
```

**情况 3:** 返回多维数组

[Java 中的多维数组](https://www.geeksforgeeks.org/multidimensional-arrays-in-java/)可以说是数组内部的数组的数组。最简单的形式可以是二维数组。他们有他们的大小和根据他们的大小申报。下面演示了二维数组的返回，其方法与一维数组非常相似。

**示例**

## Java

```
// Java Program to Illustrate Returning
// Multi-dimensional Arrays

// Importing input output classes
import java.io.*;

// Main class
class GFG {

    // Method 1
    // Main driver method
    public static void main(String[] args)
    {
        // An integer 2D array storing the
        // returned array from the method
        int[][] storage = methodReturningArray();

        // Printing the elements of the array
        // using nested for loops
        for (int i = 0; i < storage.length; i++) {
            for (int j = 0; j < storage[0].length; j++)

                System.out.print(storage[i][j] + " ");

            System.out.println();
        }
    }

    // Method 2
    // Returning an integer array
    public static int[][] methodReturningArray()
    {
        // Custom 2D integer array
        int[][] sample
            = { { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };

        // Return statement of the method
        return sample;
    }
}
```

**输出**

```
1 2 3 
4 5 6 
7 8 9 
```