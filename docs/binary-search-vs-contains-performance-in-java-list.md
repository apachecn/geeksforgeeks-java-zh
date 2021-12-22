# 二分搜索法 vs 包含 Java 列表中的性能

> 原文:[https://www . geesforgeks . org/binary-search-vs-contains-performance-in-Java-list/](https://www.geeksforgeeks.org/binary-search-vs-contains-performance-in-java-list/)

Java 提供了两种方法，即[collections . binary search()](https://www.geeksforgeeks.org/binary-search-in-java/)和 [contains()](https://www.geeksforgeeks.org/java-string-contains-method-example/) 来查找列表中的元素。在引擎盖下面，contains()方法使用 indexOf()方法搜索元素。 *indexOf()* 方法在列表中线性循环，并将每个元素与关键字进行比较，直到找到关键字，然后返回 true，否则当找不到该元素时返回 false。所以，contains()的时间复杂度是 O(n)。Collections.binarySearch()的时间复杂度为 O(log2(n))。但是如果我们想使用这个方法，那么列表应该被排序。如果列表没有排序，那么我们需要在使用 Collections.binarySearch()之前对其进行排序，这需要 O(nlog(n))个时间。

**如何选择:**

*   如果要查找的元素靠近列表的起点，那么 contains()方法的性能会更好，因为 contains()从列表的起点开始线性搜索元素。
*   如果元素被排序，并且元素的数量相对较大，那么 Collections.binarySearch()会更快，因为它只需要 O(log2(n))个时间。
*   如果列表的元素没有排序，那么 contains()方法的性能会更好，因为它只需要 O(n)个时间，但是如果搜索查询的数量很高，那么 Collections.binarySearch()方法的整体性能会更好，因为我们在第一次搜索期间只对列表排序一次，这需要 O(nlog(n))个时间，之后每次搜索操作都需要 O(log(n))个时间。
*   对于包含相对少量元素的列表，则包含()会产生更好的速度。
*   如果我们使用的 LinkedList 没有实现 RandomAccess 接口，因此无法提供 O(1)时间来访问元素，那么我们应该更喜欢 contains()而不是 Collections.binarySearch()作为 Collections.binary search()执行链接遍历需要 O(n)，然后执行比较需要 O(log(n))时间。

现在我们将讨论排序列表的两个变体

1.  排序的小列表
2.  已排序的大型列表
3.  未排序列表

**案例 1:** 对于小的排序列表

在下面提到的代码中，我们举了一个排序列表的例子，它只包含从 0 到 99 的 100 个元素，我们搜索了 40 个，正如我们在上面看到的，在小列表中，contains()在速度方面比 Collections.binarySearch 有优势。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to compare the performance
// of contains() and Collections.binarySearch()
// For a Small List (Case 1)

// Importing ArrayList and Collections classes
// from java.util package
import java.util.ArrayList;
import java.util.Collections;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of ArrayList
        // Declaring object of integer type
        ArrayList<Integer> arr = new ArrayList<>();

        // Iterating over object using for loop
        for (int i = 0; i < 100; i++) {
            arr.add(i);
        }

        // Calculating and printing the time taken
        // where we are finding 40
        // Using contains() method
        long start = System.nanoTime();
        arr.contains(40);
        long end = System.nanoTime();

        // Print statement
        System.out.println(
            "Time taken to find 40 inside arr using contains() = "
            + (end - start) + " nano seconds");

        // Calculating and printing the time taken
        // to find 40
        // Using Collections.binarySearch() method
        start = System.nanoTime();
        Collections.binarySearch(arr, 40);
        end = System.nanoTime();

        // Print statement
        System.out.println(
            "Time taken to find 40 inside arr using binarySearch() = "
            + (end - start) + " nano seconds");
    }
}
```

**Output**

```java
Time taken to find 40 inside arr using contains() = 16286 nano seconds
Time taken to find 40 inside arr using binarySearch() = 87957 nano seconds
```

**案例 2:** 对于大型排序列表

在下面提到的例子中，我们创建了一个包含 100000 个元素(从 0 到 99999)的排序数组列表，并使用 contains()和 Collections.sort()方法找到其中的元素 40000。由于列表是排序的，并且具有相对大量的元素，Collections.sort()的性能优于 contains()方法。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Find and Compare the Performance
// of conatins() and Collections.sort() Methods
// For Large Sorted ArrayList (Case 2)

// Importing ArrayList and Collections classes
// from java.util package
import java.util.ArrayList;
import java.util.Collections;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of ArrayList class
        // Declaring object of Integer type
        ArrayList<Integer> arr = new ArrayList<>();

        // Iterating over the object
        for (int i = 0; i < 100000; i++) {

            // Adding elements using add() method
            arr.add(i);
        }

        // Calculating and printing the time taken
        // to find 40000 using contains()
        long start = System.nanoTime();
        arr.contains(40000);
        long end = System.nanoTime();

        // Print statement
        System.out.println(
            "Time taken to find 40000 inside arr "
            + "using contains() = " + (end - start)
            + " nano seconds");

        // Calculating and printing the time taken
        // to find 40000 using Collections.binarySearch()
        start = System.nanoTime();
        Collections.binarySearch(arr, 40000);
        end = System.nanoTime();

        // Print statement
        System.out.println(
            "Time taken to find 40000 inside arr "
            + "using binarySearch() = " + (end - start)
            + " nano seconds");
    }
}
```

**Output**

```java
Time taken to find 40000 inside arr using contains() = 6651276 nano seconds
Time taken to find 40000 inside arr using binarySearch() = 85231 nano seconds
```

**情况 3:** 对于未排序的列表

在下面提到的代码中，我们通过在其中存储 0 到 100000 之间的随机数，创建了一个未排序的数组列表。由于列表未排序，contains()方法的性能更好，因为使用 ***Collections.sort()方法*** 时只需要 O(n)个时间，我们首先要对列表进行排序，这需要额外的 O(nlog(n))个时间，然后再用 O(log2(n))个时间来搜索元素。\

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to compare the performance
// of contains() and Collections.sort() method
//  on an unsorted ArrayList (Case3)

// Importing ArrayList and Collections class
// from java.util package
import java.util.ArrayList;
import java.util.Collections;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of ArrayList class
        ArrayList<Integer> arr = new ArrayList<>();

        // Iterating between 0 to 100000 numbers
        for (int i = 0; i < 100000; i++) {

            // Generating random numbers as iterated
            // using random() function
            int rand = (int)(Math.random() * 100000);

            // Later storing them inside our list
            arr.add(rand);
        }

        // Setting the key to be found as the element
        // at index 30000 inside of unsorted list
        int key = arr.get(30000);

        // Calculating and printing the time taken
        // to find the key using contains()
        long start = System.nanoTime();
        arr.contains(key);
        long end = System.nanoTime();

        // Print statement
        System.out.println(
            "Time takes to find " + key
            + " inside arr using contains() = "
            + (end - start) + " nano seconds");

        // Calculating and printing the time taken to
        // find the key using Collections.binarySearch()
        // after sorting the list using Collections.sort()
        // method
        start = System.nanoTime();
        Collections.sort(arr);
        Collections.binarySearch(arr, key);
        end = System.nanoTime();

        // Print statement
        System.out.println(
            "Time takes to find " + key
            + " inside arr using binarySearch() = "
            + (end - start) + " nano seconds");
    }
}
```

**Output**

```java
Time takes to find 66181 inside arr using contains() = 8331486 nano seconds
Time takes to find 66181 inside arr using binarySearch() = 140322701 nano seconds
```