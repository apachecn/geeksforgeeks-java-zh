# Java 中的数组类

> 原文:[https://www.geeksforgeeks.org/array-class-in-java/](https://www.geeksforgeeks.org/array-class-in-java/)

**java.util 包**中的**数组**类是 **Java 集合框架**的一部分。这个类提供静态方法来动态创建和访问 **Java 数组**。它只包含静态方法和对象类的方法。这个类的方法可以由类名本身使用。

类层次结构如下:

```java
java.lang.Object
 ↳ java.util.Arrays
```

Geek，现在你一定想知道，当我们能够在数组上声明、初始化和计算操作时，为什么我们需要 java Arrays 类。这个问题的答案在这个类的方法中，我们将进一步讨论，因为实际上这些函数帮助程序员扩展数组的视野，例如，经常有 [**循环**](https://www.geeksforgeeks.org/loops-in-java/) 被用来在数组上执行一些任务，比如:

*   用特定值填充数组。
*   对数组进行排序。
*   在数组中搜索。
*   还有更多。

> 这里，数组类提供了几个静态方法，可以用来直接执行这些任务，而不需要使用循环，从而使我们的代码变得超级短和优化。

**语法:**类声明

```java
public class Arrays
    extends Object
```

**语法:**为了使用数组

```java
Arrays.<function name>;
```

**Java 数组类中的方法**

[java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)的 Array 类包含了几个静态方法，可以用来填充、排序、搜索等数组。现在让我们讨论一下这个类的方法，如下表所示:

<figure class="table">的帮助下搜索数组中的指定元素 比较器)

| 【 Method 】 | [Operation performed] |
| --- | --- |
| 作为列表() | Returns a fixed-size list supported by the specified array. |
| 【二分搜索法() | In method of bisection algorithm |
| Use method of bisection algorithm |
| Comparison (Array1, Array2) | Compares two arrays passed as parameters in dictionary order, and searches for the specified object within the specified array. |
|  | The specified array is truncated or filled with the default value (if necessary) so that the copy has the specified length. |
|  |
|  | Returns true if the two specified arrays are equal in depth. |
| 深度哈希代码(对象[]a) | Returns the hash code according to the "deep content" of the specified array. |
|  | Returns the string representation of the "deep content" of the specified array. |
|  | Check whether two arrays are equal. |
|  | Assign the padding value to each index of the array. |
| hashCode(原始 larray) | Returns the integer hashCode of this array instance. |
| 不匹配(数组 1，数组 2) | Finds and returns the index of the first mismatched element between two specified arrays. |
| 并行 refix(original lay，fromIndex，endIndex，函数运算符) | Use the specified function operator to execute parallel refix on the given range of the array. |
| parallelPrefix(originalArray，运算符) | Executes parallelPrefix on a complete array using the specified function operator. |
| 并行失速(原始光线，功能发生器) | Set all elements of the array in parallel using the provided generator function. |
|  |
| Sets all elements of the specified array using the provided generator function. |
|  | Sort the complete array in ascending order. |
|  | Sorts the array of the specified range in ascending order. |
|  | Sorts the specified range of the specified object array according to the order summarized by the specified comparator. |
|  | Sorts the specified array of objects in the order summarized by the specified comparator. |
| 分割器(原始光线) | Returns the Spliterator that covers all the specified arrays. |
| 拆分器(原始数组，从索引，结束索引) | Returns the Spliterator of the array type that covers the specified range of the specified array. |
|  | Returns the sequential stream with the specified array as the source. |
|  | It returns a string representation of the contents of this array. The string representation consists of a list of array elements enclosed in square brackets ("[]"). Adjacent elements of are separated by a comma followed by a space. Convert function elements to strings. |

</figure>

**实施:**

**例 1:**T2【asList()方法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Demonstrate Arrays Class
// Via asList() method

// Importing Arrays utility class
// from java.util package
import java.util.Arrays;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // To convert the elements as List
        System.out.println("Integer Array as List: "
                           + Arrays.asList(intArr));
    }
}
```

**Output**

```java
Integer Array as List: [[I@2f4d3709]

```

**例 2:**T2【binary search()方法

这些方法在二分搜索法算法的帮助下搜索数组中的指定元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Demonstrate Arrays Class
// Via binarySearch() method

// Importing Arrays utility class
// from java.util package
import java.util.Arrays;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        Arrays.sort(intArr);

        int intKey = 22;

        // Print the key and corresponding index
        System.out.println(
            intKey + " found at index = "
            + Arrays.binarySearch(intArr, intKey));
    }
}
```

**Output**

```java
22 found at index = 3

```

**示例 3:** [二进制搜索(数组、从索引、到索引、键、比较器)](https://www.geeksforgeeks.org/arrays-binarysearch-in-java-with-examples-set-2-search-in-subarray/)方法

此方法使用二分搜索法算法在指定数组的范围内搜索指定对象。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Arrays.binarySearch() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        Arrays.sort(intArr);

        int intKey = 22;

        System.out.println(
            intKey
            + " found at index = "
            + Arrays
                  .binarySearch(intArr, 1, 3, intKey));
    }
}
```

**Output**

```java
22 found at index = -4

```

**示例 4:** 比较(数组 1，数组 2)方法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Arrays.compare() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // Get the second Array
        int intArr1[] = { 10, 15, 22 };

        // To compare both arrays
        System.out.println("Integer Arrays on comparison: "
                           + Arrays.compare(intArr, intArr1));
    }
}
```

**Output**

```java
Integer Arrays on comparison: 1

```

**示例 5:** 比较符号(数组 1，数组 2)方法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Arrays.compareUnsigned() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Arrays
        int intArr[] = { 10, 20, 15, 22, 35 };

        // Get the second Arrays
        int intArr1[] = { 10, 15, 22 };

        // To compare both arrays
        System.out.println("Integer Arrays on comparison: "
                           + Arrays.compareUnsigned(intArr, intArr1));
    }
}
```

**Output**

```java
Integer Arrays on comparison: 1

```

**例 6:** [仿(originalArray，newLength)](https://www.geeksforgeeks.org/arrays-copyof-in-java-with-examples/) 法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Arrays.copyOf() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // To print the elements in one line
        System.out.println("Integer Array: "
                           + Arrays.toString(intArr));

        System.out.println("\nNew Arrays by copyOf:\n");

        System.out.println("Integer Array: "
                           + Arrays.toString(
                                 Arrays.copyOf(intArr, 10)));
    }
}
```

**Output**

```java
Integer Array: [10, 20, 15, 22, 35]

New Arrays by copyOf:

Integer Array: [10, 20, 15, 22, 35, 0, 0, 0, 0, 0]

```

**例 7:**[copy for range(original ray，fromIndex，endIndex)](https://www.geeksforgeeks.org/java-util-arrays-copyofrange-java/) 方法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Arrays.copyOfRange() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // To print the elements in one line
        System.out.println("Integer Array: "
                           + Arrays.toString(intArr));

        System.out.println("\nNew Arrays by copyOfRange:\n");

        // To copy the array into an array of new length
        System.out.println("Integer Array: "
                           + Arrays.toString(
                                 Arrays.copyOfRange(intArr, 1, 3)));
    }
}
```

**Output**

```java
Integer Array: [10, 20, 15, 22, 35]

New Arrays by copyOfRange:

Integer Array: [20, 15]

```

**例 8:**[deep equals(Object[]a1，Object[] a2)](https://www.geeksforgeeks.org/java-util-arrays-deepequals-java/) 法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Arrays.deepEquals() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Arrays
        int intArr[][] = { { 10, 20, 15, 22, 35 } };

        // Get the second Arrays
        int intArr1[][] = { { 10, 15, 22 } };

        // To compare both arrays
        System.out.println("Integer Arrays on comparison: "
                           + Arrays.deepEquals(intArr, intArr1));
    }
}
```

**Output**

```java
Integer Arrays on comparison: false

```

**例 9:** 深度哈希码(对象[] a)方法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Arrays.deepHashCode() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[][] = { { 10, 20, 15, 22, 35 } };

        // To get the dep hashCode of the arrays
        System.out.println("Integer Array: "
                           + Arrays.deepHashCode(intArr));
    }
}
```

**Output**

```java
Integer Array: 38475344

```

**例 10:**T2【deepToString(Object[]a)法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Arrays.deepToString() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[][] = { { 10, 20, 15, 22, 35 } };

        // To get the deep String of the arrays
        System.out.println("Integer Array: "
                           + Arrays.deepToString(intArr));
    }
}
```

**Output**

```java
Integer Array: [[10, 20, 15, 22, 35]]

```

**例 11:** [等于(array1，array2)](https://www.geeksforgeeks.org/java-util-arrays-equals-java-examples/) 法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Arrays.equals() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Arrays
        int intArr[] = { 10, 20, 15, 22, 35 };

        // Get the second Arrays
        int intArr1[] = { 10, 15, 22 };

        // To compare both arrays
        System.out.println("Integer Arrays on comparison: "
                           + Arrays.equals(intArr, intArr1));
    }
}
```

**Output**

```java
Integer Arrays on comparison: false

```

**示例 12:** [填充(原始光线，填充值)](https://www.geeksforgeeks.org/arrays-fill-java-examples/)方法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Arrays.fill() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Arrays
        int intArr[] = { 10, 20, 15, 22, 35 };

        int intKey = 22;

        Arrays.fill(intArr, intKey);

        // To fill the arrays
        System.out.println("Integer Array on filling: "
                           + Arrays.toString(intArr));
    }
}
```

**Output**

```java
Integer Array on filling: [22, 22, 22, 22, 22]

```

**例 13:**hashCode(original larray)方法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Arrays.hashCode() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // To get the hashCode of the arrays
        System.out.println("Integer Array: "
                           + Arrays.hashCode(intArr));
    }
}
```

**Output**

```java
Integer Array: 38475313

```

**实施例 14:** 错配(数组 1，数组 2)方法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Arrays.mismatch() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Arrays
        int intArr[] = { 10, 20, 15, 22, 35 };

        // Get the second Arrays
        int intArr1[] = { 10, 15, 22 };

        // To compare both arrays
        System.out.println("The element mismatched at index: "
                           + Arrays.mismatch(intArr, intArr1));
    }
}
```

**Output**

```java
The element mismatched at index: 1

```

**例 15:**T2【平行(原拉雷)法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Arrays.parallelSort() method

// Importing Arrays class from
// java.util package
import java.util.Arrays;

// Main class
public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // To sort the array using parallelSort
        Arrays.parallelSort(intArr);

        System.out.println("Integer Array: "
                           + Arrays.toString(intArr));
    }
}
```

**Output**

```java
Integer Array: [10, 15, 20, 22, 35]

```

**例 16:** [排序(原拉雷)](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/)方法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Arrays.sort() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // To sort the array using normal sort-
        Arrays.sort(intArr);

        System.out.println("Integer Array: "
                           + Arrays.toString(intArr));
    }
}
```

**Output**

```java
Integer Array: [10, 15, 20, 22, 35]

```

**示例 17:** [排序(originalArray，fromIndex，endIndex)](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/) 方法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Arrays.sort() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // To sort the array using normal sort
        Arrays.sort(intArr, 1, 3);

        System.out.println("Integer Array: "
                           + Arrays.toString(intArr));
    }
}
```

**Output**

```java
Integer Array: [10, 15, 20, 22, 35]

```

**示例 18:** [排序(T[] a，int fromIndex，int toIndex，比较器< super T > c)](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/) 方法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of Comparator
// interface
import java.util.*;
import java.lang.*;
import java.io.*;

// A class to represent a student.
class Student {
    int rollno;
    String name, address;

    // Constructor
    public Student(int rollno, String name,
                   String address)
    {
        this.rollno = rollno;
        this.name = name;
        this.address = address;
    }

    // Used to print student details in main()
    public String toString()
    {
        return this.rollno + " "
            + this.name + " "
            + this.address;
    }
}

class Sortbyroll implements Comparator<Student> {
    // Used for sorting in ascending order of
    // roll number
    public int compare(Student a, Student b)
    {
        return a.rollno - b.rollno;
    }
}

// Driver class
class Main {
    public static void main(String[] args)
    {
        Student[] arr = { new Student(111, "bbbb", "london"),
                          new Student(131, "aaaa", "nyc"),
                          new Student(121, "cccc", "jaipur") };

        System.out.println("Unsorted");
        for (int i = 0; i < arr.length; i++)
            System.out.println(arr[i]);

        Arrays.sort(arr, 1, 2, new Sortbyroll());

        System.out.println("\nSorted by rollno");
        for (int i = 0; i < arr.length; i++)
            System.out.println(arr[i]);
    }
}
```

**Output**

```java
Unsorted
111 bbbb london
131 aaaa nyc
121 cccc jaipur

Sorted by rollno
111 bbbb london
131 aaaa nyc
121 cccc jaipur

```

**例 19:** [排序(T[] a，比较器<超 T > c)](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/) 法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate working of Comparator
// interface
import java.util.*;
import java.lang.*;
import java.io.*;

// A class to represent a student.
class Student {
    int rollno;
    String name, address;

    // Constructor
    public Student(int rollno, String name,
                   String address)
    {
        this.rollno = rollno;
        this.name = name;
        this.address = address;
    }

    // Used to print student details in main()
    public String toString()
    {
        return this.rollno + " "
            + this.name + " "
            + this.address;
    }
}

class Sortbyroll implements Comparator<Student> {

    // Used for sorting in ascending order of
    // roll number
    public int compare(Student a, Student b)
    {
        return a.rollno - b.rollno;
    }
}

// Driver class
class Main {
    public static void main(String[] args)
    {
        Student[] arr = { new Student(111, "bbbb", "london"),
                          new Student(131, "aaaa", "nyc"),
                          new Student(121, "cccc", "jaipur") };

        System.out.println("Unsorted");
        for (int i = 0; i < arr.length; i++)
            System.out.println(arr[i]);

        Arrays.sort(arr, new Sortbyroll());

        System.out.println("\nSorted by rollno");
        for (int i = 0; i < arr.length; i++)
            System.out.println(arr[i]);
    }
}
```

**Output**

```java
Unsorted
111 bbbb london
131 aaaa nyc
121 cccc jaipur

Sorted by rollno
111 bbbb london
121 cccc jaipur
131 aaaa nyc

```

**示例 20:** 分裂器(原始光线)方法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Arrays.spliterator() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // To sort the array using normal sort
        System.out.println("Integer Array: "
                           + Arrays.spliterator(intArr));
    }
}
```

**Output**

```java
Integer Array: java.util.Spliterators$IntArraySpliterator@4e50df2e

```

**示例 21:** 拆分器(originalArray，fromIndex，endIndex)方法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Arrays.spliterator() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // To sort the array using normal sort
        System.out.println("Integer Array: "
                           + Arrays.spliterator(intArr, 1, 3));
    }
}
```

**Output**

```java
Integer Array: java.util.Spliterators$IntArraySpliterator@4e50df2e

```

**例 22:** [流(原拉雷)](https://www.geeksforgeeks.org/arrays-stream-method-in-java/)法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Arrays.stream() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // To get the Stream from the array
        System.out.println("Integer Array: "
                           + Arrays.stream(intArr));
    }
}
```

**Output**

```java
Integer Array: java.util.stream.IntPipeline$Head@7291c18f

```

**例 23:**T2【to string(original larray)法

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// Arrays.toString() method

import java.util.Arrays;

public class Main {
    public static void main(String[] args)
    {

        // Get the Array
        int intArr[] = { 10, 20, 15, 22, 35 };

        // To print the elements in one line
        System.out.println("Integer Array: "
                           + Arrays.toString(intArr));
    }
}
```

**Output**

```java
Integer Array: [10, 20, 15, 22, 35]

```

本文由**里沙布·马赫塞**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上述话题的信息，请写评论