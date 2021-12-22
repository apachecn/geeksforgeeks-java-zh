# Java 中流的中间方法

> 原文:[https://www . geesforgeks . org/intermediate-of-of-stream-in-Java/](https://www.geeksforgeeks.org/intermediate-methods-of-stream-in-java/)

流应用编程接口用于处理对象集合。流是支持各种方法的对象序列，这些方法可以通过流水线来产生所需的结果。该流提供的方法大致分为

*   [Intermediate method]
*   [Terminal method]

在这里，我们将讨论流应用编程接口的中间方法。这些方法都在[*Java . util . stream*](https://www.geeksforgeeks.org/stream-in-java/)中。中间操作符直到终端操作被调用时才执行，即直到实际需要处理结果时才执行。我们将讨论几个最重要和最常用的:

1.  [*Filter (predicate)* Method](https://www.geeksforgeeks.org/stream-filter-java-examples/)
2.  [*Sort ()* Method](https://www.geeksforgeeks.org/stream-sorted-in-java/)
3.  [*Clear distinction ()* Method](https://www.geeksforgeeks.org/stream-distinct-java/)
4.  [*Figure ()* Method](https://www.geeksforgeeks.org/stream-map-java-examples/)

**方法 1:** [*过滤(谓词)*](https://www.geeksforgeeks.org/stream-filter-java-examples/)

它返回一个新的流，该流由根据谓词(条件)调用它的流的元素组成。

> **注意:**
> 
> *   The intermediate function returns a stream back.
> *   On any stream, you can perform any number of intermediate operations, but the terminal operations should be single and finally written. Next is Stream
> *   Predicate, which is a non-intrusive stateless predicate, is applied to each element to determine whether it should be included.

**示例**

## Java

```java
// Java Program to illustrate Intermediate Methods of Streams
// Case 1: filter(predicate) Method

// Importing input output classes
import java.io.*;
// Importing List Class from java.util package 
import java.util.List;

// Main Class
public class GFG {

    // Main driver method
    public static void main (String[] args) {

      // Creating an object of List Class by
      // declaring a list of Integers

      // Custom entries in the list elements
      List<Integer> intList = List.of(15,20,48,63,49,27,56,32,9);

      // Calling the function to
      // print the list of Even numbers
      printEvenNumber(intList);
    }

  // Method 2
  // Helper method
  // To print the even numbers using filter method.
  private static void printEvenNumber(List<Integer> intList){

        // Display message
        System.out.print("\nEven numbers are : ");

        // Illustrating filter method usage 
        intList.stream().filter(
          element -> (element%2==0)
        )
        .forEach(
          element -> System.out.print(element+ " ")
        );

    }
}
```

**输出**

```java
Even numbers are : 20 48 56 32 
```

**方法二:** [*排序()*](https://www.geeksforgeeks.org/stream-sorted-in-java/)

返回由传递的流的元素组成的流，按照自然顺序排序。如果该流的元素不可比较，则在执行终端操作时可能会引发 java.lang.ClassCastException。

**示例**

## Java

```java
// Java Program to illustrate Intermediate Method of Stream
// Case 2: sorted() Method

// Importing input output class
import java.io.*;
// Importing List class from java.util package
import java.util.List;

// Main class
class GFG {

    // Method 1
    // To print the elements og the Sorted List
    public static void
    printSortedList(List<Integer> intList)
    {

        // Sorts and returns the stream to the forEach
        // illustrating stream method
        intList.stream().sorted().forEach(
            element -> System.out.println(element));
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of List class
        // Declaring object of Integer type

        // Custom entries
        List<Integer> intList
            = List.of(68, 45, 99, 21, 8, 76, 34, 19);

        // Display message only
        System.out.println(
            "Elements of Sorted List are as follows : ");

        // Calling the method to print the Sorted List
        printSortedList(intList);
    }
}
```

**输出**

```java
8
19
21
34
45
68
76
99
```

**方法三:** [*泾渭分明()*](https://www.geeksforgeeks.org/stream-distinct-java/)

它返回一个由传递的流的不同元素组成的流。对于有序流，不同元素的选择是稳定的(对于重复的元素，在相遇顺序中最先出现的元素被保留)。而对于非有序流，它不能保证任何稳定性。

**示例**

## Java

```java
// Java Program to illustrate Intermediate Method of Stream
// Case 3: distinct() Method

// Importing input output classes
import java.io.*;
// Importing List class from java.util package
import java.util.List;

// Main Class
class GFG {

    // Method 1
    // To find distinct elements from the List
    public static void
    findDistinctElements(List<Integer> intList)
    {
        intList.stream().distinct().forEach(
            element -> System.out.print(element + " "));

        // Display message only
        System.out.println("\n\nSorted List is ");

        // Also we are sorting elements at the same time
        intList.stream().distinct().sorted().forEach(
            element -> System.out.print(element + " "));
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of List class
        // Declaring object of Integer type

        // Custom integer inputs
        List<Integer> intList
            = List.of(12, 54, 63, 12, 7, 98, 63, 54, 72);

        // Calling the Method 1 as above created to
        // find the distinct elements from the list
        findDistinctElements(intList);
    }
}
```

**输出**

```java
12 54 63 7 98 72 

Sorted List is 
7 12 54 63 72 98 
```

**方法四:** [*地图()*](https://www.geeksforgeeks.org/stream-map-java-examples/)

映射器是一个无干扰的无状态函数，应用于流的每个元素。它返回一个流，该流由给定函数应用于传递的流的元素的结果组成。

**语法:**

```java
stream().map(mapper)
```

**实施:**

**示例**

## Java

```java
// Java Program to illustrate Intermediate Stream Methods
// Case 4: map() Method

// Importing input output class
import java.io.*;
// Importing List class from the java.util package
import java.util.List;

// Main Class
class GFG {

    // Method 1
    // To find the cube of elements in the List
    public static void findTheCube(List<Integer> intList)
    {

        intList.stream()
            .map(element -> element * element * element)
            .forEach(
                element -> System.out.print(element + " "));

        // Display message only
        System.out.println(
            "\n\nOutput after distinct() implementation : ");

        // Applying distinct() on this
        intList.stream()
            .distinct()
            .map(element -> element * element * element)
            .forEach(
                element -> System.out.print(element + " "));

        // Display message only
        System.out.println(
            "\n\nOutput after sorted() implementation : ");

        // Now applying sorted() on this
        intList.stream()
            .distinct()
            .sorted()
            .map(element -> element * element * element)
            .forEach(
                element -> System.out.print(element + " "));

        // Display message only
        System.out.println(
            "\n\nOutput after filter() implementation : ");

        // Applying Filter() that values
        // only below 10000 will be printed
        intList.stream()
            .distinct()
            .sorted()
            .map(element -> element * element * element)
            .filter(element -> element < 10000)
            .forEach(
                element -> System.out.print(element + " "));
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of List class and
        // declaring object of Integer type

        // Custom entries
        List<Integer> intList
            = List.of(5, 19, 8, 23, 6, 54, 32, 5, 23);

        // Calling the Method1 in the main() body
        // to get the cube of the elements in the List
        findTheCube(intList);
    }
}
```

**输出**

```java
125 6859 512 12167 216 157464 32768 125 12167 

Output after distinct() implementation : 
125 6859 512 12167 216 157464 32768 

Output after sorted() implementation : 
125 216 512 6859 12167 32768 157464 

Output after filter() implementation : 
125 216 512 6859 
```