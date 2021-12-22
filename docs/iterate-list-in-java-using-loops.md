# 使用循环在 Java 中迭代列表

> 原文:[https://www . geesforgeks . org/iterate-list-in-Java-use-loops/](https://www.geeksforgeeks.org/iterate-list-in-java-using-loops/)

在本文中，我们将看到如何遍历列表。在 Java 中，列表是集合框架的一个接口。列表可以是各种类型，如数组列表、堆栈、链接列表和向量。有多种方法可以遍历 java List，但这里我们只讨论使用循环遍历。因此，有标准的三个遍历可用，所以确实存在三个方法，但是随着 java 8 和 streams 的引入，其他方法也出现了。因此，所有四种方法讨论如下:

**方法:**

1.  对于循环方法
2.  当方法
3.  对于每个循环方法
4.  对于 java 8 的每个循环

**实施:**

**方法 1:** 使用 for 循环

For 循环是最常见的流量控制循环。For 循环使用一个变量来遍历列表。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Iterate List in java
// using for loop
// Importing all input output classes
import java.io.*;
// Importing all utility classes from
// java.util package
import java.util.*;

// Class
class GFG {

    // main driver method
    public static void main(String[] args)
    {
        // Creating an ArrayList object
        // Declaring object of Integer type
        // Custom entries in array
        List<Integer> my_list
            = Arrays.asList(10, 20, 30, 40, 50);

        // Display message
        System.out.print("Iterating over ArrayList: ");

        // Iteration over ArrayList
        // using the for loop
        for (int i = 0; i < my_list.size(); i++)

            // Print and display the all elements
            // in List object
            System.out.print(my_list.get(i) + " ");

        // new line
        System.out.println();

        // No, creating a vector of size N
        // Custom entry for N = 5
        // Custom Integer entries
        List<Integer> v = new Vector<Integer>(5);
        v.add(10);
        v.add(20);
        v.add(30);
        v.add(40);
        v.add(50);

        // Display message
        System.out.print("Iterating over Vector:    ");

        // iterating over vector using for loop
        for (int i = 0; i < v.size(); i++)

            // Print and display vector elements
            System.out.print(v.get(i) + " ");

        // New Line
        System.out.println();

        // Creating a stack containing Integer elements
        List<Integer> s = new Stack<Integer>();

        // Adding integer elements
        // Custom input
        s.add(10);
        s.add(20);
        s.add(30);
        s.add(40);
        s.add(50);

        // Display message
        System.out.print("Iterating over Stack:     ");

        // For loop o iterate over elements in stack
        for (int i = 0; i < v.size(); i++)

            // Print and display all stack elements
            System.out.print(s.get(i) + " ");
    }
}
```

**Output**

```java
Iterating over ArrayList: 10 20 30 40 50 
Iterating over Vector:    10 20 30 40 50 
Iterating over Stack:     10 20 30 40 50 
```

**方法 2:** 使用 While 循环

类似于 For 循环的 Java while 循环是一个控制流语句，它允许代码重复运行，直到满足所需的条件。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to iterate over List
// using while loop

// Importing all input output classes
import java.io.*;
// Importing all utility classes from
// java.util package
import java.util.*;

// Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of List
        // Declaring object of Integer type
        // Custom Integer entries
        List<Integer> my_list
            = Arrays.asList(10, 20, 30, 40, 50);

        // Display message
        System.out.print("Iterating over ArrayList: ");

        // Initially loop variable is initialized
        // with zero
        int i = 0;

        // Iterating over List via while loop
        // using size() method
        while (i < my_list.size()) {

            // Print and display all elements
            // of an ArrayList
            System.out.print(my_list.get(i) + " ");

            // Incrementing the counter by unity safter
            // one iteration
            i++;
        }

        i = 0;

        // New Line
        System.out.println();

        // Creating a Vector of size N
        // Custom value for N = 5
        List<Integer> v = new Vector<Integer>(5);

        // Adding 5 elements to the above List object
        // for vector
        // Custom entries
        v.add(10);
        v.add(20);
        v.add(30);
        v.add(40);
        v.add(50);

        // Display message
        System.out.print("Iterating over Vector:    ");

        // Iterating over Vector via while loop
        // using the size() method
        while (i < v.size()) {

            // Print and display all elements of vector
            System.out.print(v.get(i) + " ");

            // Increment the counter variable
            i++;
        }

        //  Counter variable is initially
        // initialized with zero
        i = 0;

        // New Line
        System.out.println();

        // Creating a Stack by creating another
        // list object of Integer type
        // Declaring object of Integer type
        List<Integer> s = new Stack<Integer>();

        // Adding elements to the above stack
        // Custom entries
        s.add(10);
        s.add(20);
        s.add(30);
        s.add(40);
        s.add(50);

        // Display message
        System.out.print("Iterating over Stack:     ");

        // Iterating over stack via while loop
        // using size method()
        while (i < v.size()) {

            // Print and display all elements
            // of the above stack/ obj created
            System.out.print(s.get(i) + " ");

            // Increment the counter by unity
            i++;
        }
    }
}
```

**Output**

```java
Iterating over ArrayList: 10 20 30 40 50 
Iterating over Vector:    10 20 30 40 50 
Iterating over Stack:     10 20 30 40 50 
```

**方法 3:** 用于每个循环

**语法:**

```java
for (type temp : list_name) 
{  
   statements using temp;
}
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
/*package whatever //do not write package name here */

import java.io.*;
import java.util.*;
class GFG {
    public static void main(String[] args)
    {
        // creating Arraylist
        List<Integer> my_list
            = Arrays.asList(10, 20, 30, 40, 50);

        System.out.print("Iterating over ArrayList: ");
         // For Each Loop for iterating ArrayList
        for (Integer i :my_list)
            System.out.print(i + " ");

        System.out.println();

        // creating Vector of size 5
        List<Integer> v = new Vector<Integer>(5);
        v.add(10);
        v.add(20);
        v.add(30);
        v.add(40);
        v.add(50);

        System.out.print("Iterating over Vector:    ");
         // For Each Loop for iterating Vector
        for (Integer i : v)
            System.out.print(i + " ");

        System.out.println();

        // creating Stack
        List<Integer> s = new Stack<Integer>();
        s.add(10);
        s.add(20);
        s.add(30);
        s.add(40);
        s.add(50);

        System.out.print("Iterating over Stack:     ");
        // For Each Loop for iterating Stack
        for (Integer i : s)
            System.out.print(i + " ");
    }
}
```

**Output**

```java
Iterating over ArrayList: 10 20 30 40 50 
Iterating over Vector:    10 20 30 40 50 
Iterating over Stack:     10 20 30 40 50 
```

**方法 4:** 用于 Java 8 的每个循环

此方法将函数接口作为参数，因此 lambda 表达式可以作为参数传递。

**语法:**

```java
void forEach(Consumer<? super T> action)
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Importing all input output classes
import java.io.*;
// Importing all classes from
// java,util package
import java.util.*;

// Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an Arraylist by creating object
        // of List and declaring as Integer type
        // Custom  Integer entries
        List<Integer> my_list
            = Arrays.asList(10, 20, 30, 40, 50);

        // Display message
        System.out.print("Iterating over ArrayList: ");

        // Traversing over ArrayList
        // using for each method Java 8
        my_list.forEach(
            list -> System.out.print(list + " "));

        // New line
        System.out.println();

        // creating Vector by creating object of
        // List and declaring as Integer type

        // Vector is of size N
        // N = 5 for illustration purposes
        List<Integer> v = new Vector<Integer>(5);

        // Adding elements to the vector
        // Custom Integer elements
        v.add(10);
        v.add(20);
        v.add(30);
        v.add(40);
        v.add(50);

        // Display message
        System.out.print("Iterating over Vector:    ");

        // Traversing the above vector elements
        // using for each method Java 8
        v.forEach(vector -> System.out.print(vector + " "));

        // New line
        System.out.println();

        // Creating a Stack by creating an object of
        // List and declaring it as of Integer type
        List<Integer> s = new Stack<Integer>();

        // Adding elements to the above stack created
        // Custom inputs addition using add() method
        s.add(10);
        s.add(20);
        s.add(30);
        s.add(40);
        s.add(50);

        // Display message
        System.out.print("Iterating over Stack:     ");

        // Print and display all the elements inside stack
        // using for each method Java 8
        s.forEach(stack -> System.out.print(stack + " "));
    }
}
```

**Output**

```java
Iterating over ArrayList: 10 20 30 40 50 
Iterating over Vector:    10 20 30 40 50 
Iterating over Stack:     10 20 30 40 50 
```