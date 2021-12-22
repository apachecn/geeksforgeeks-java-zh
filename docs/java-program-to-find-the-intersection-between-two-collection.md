# 寻找两个集合交集的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-find-two-collection 的交集/](https://www.geeksforgeeks.org/java-program-to-find-the-intersection-between-two-collection/)

[Collection](https://www.geeksforgeeks.org/collections-in-java-2/) 是指一组不同的类和接口组合在一起成为一个具有相似功能的单一单元称为 Collection 和 framework 我们非常了解它提供了一个预定义的架构来表示和操作 java 中的集合。在这里，我们将讨论如何找到两个集合之间的交集，即如果第一个集合中的所有元素在第二个集合中不可用，则从第一个集合中移除所有元素。

在本文中，我们将使用两个集合框架类 vector 类和 ArrayList 类来找到这两个集合之间的交集。

**方法:**

1.  使用[数组列表包含()](https://www.geeksforgeeks.org/arraylist-contains-java/#:~:text=ArrayList%20contains()%20method%20in,the%20given%20list%20or%20not.&text=Returns%3A,list%20else%20it%20returns%20false.)方法
2.  [**使用 Vector.retainAll()方法**](https://www.geeksforgeeks.org/vector-retainall-method-in-java-with-examples/)

**方法 1:**

*   将元素存储在第一个集合和第二个集合(数组列表)中。
*   现在迭代第一个集合并检查第二个集合是否包含第一个集合的元素。
*   如果不包含，则从第一个集合中移除元素。
*   打印第一个集合。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Remove All the Elements from the First
// Collection if it is not Available in the Second
// Using ArrayList.contains() Method  

// Importing input output classes
import java.io.*;
// Importing utility classes
import java.util.*;

// Main class
public class GFG {

    // Method 1 of this class
    // To remove the elements from the collection
    static ArrayList<Integer>
    RemoveElements(ArrayList<Integer> A,
                   ArrayList<Integer> B)
    {
        // Iterating over elements in object
        // using for loop
        for (int i = 0; i < A.size(); ++i) {

            // Removing the elements from the collection
            if (B.contains(A.get(i)) == false) {
                A.remove(i);
            }
        }

        // Returning the update ArrayList
        return A;
    }

    // Method 2 of this class
    // To print the collection
    static void print(ArrayList<Integer> A)
    {
        // Iterating over elements in object
        // using for-each loop
        for (int element : A) {

            // Printing the elements of the linked list
            System.out.print(element + " ");
        }
    }

    // Method 3 of this class
    // Main driver method
    public static void main(String[] args)
    {
        // Creating an object of ArrayList class
        // Declaring object of Integer type
        ArrayList<Integer> A = new ArrayList<>();

        // Inserting elements to ArrayList object
        // Custom input entries
        A.add(1);
        A.add(2);
        A.add(3);
        A.add(4);

        // Creating another object of ArrayList class
        // Again declaring object of Integer type
        ArrayList<Integer> B = new ArrayList<>();

        // Inserting elements to ArrayList object
        // Custom input entries
        B.add(1);
        B.add(2);
        B.add(3);

        // Calling the Function
        ArrayList<Integer> UpdatedCollection
            = RemoveElements(A, B);

        // Lastly printing the updated collection
        print(A);
    }
}
```

**Output**

```java
1 2 3 
```

**方法 2:使用 Vector.retainAll()方法**

*   将元素存储在第一个集合和第二个集合(矢量)中。
*   现在使用**vector . retainal()方法**
*   打印第一个集合。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Remove All the Elements from the First
// Collection if it is not Available in the Second
// Using Vector.retainAll() method

// Importing libraries
import java.io.*;
import java.util.*;

// Main class
public class GFG {
    // Method 1 of this class
    // To remove the elements from the collection
    static Vector<Integer> RemoveElements(Vector<Integer> A,
                                          Vector<Integer> B)
    {
        A.retainAll(B);
        // Returning the update ArrayList
        return A;
    }
    // Method 2 of this class
    // To print the collection
    static void print(Vector<Integer> A)
    {
        // Iterating elements in object using for loop
        for (int element : A) {

            // Printing the elements of the linked list
            System.out.print(element + " ");
        }
    }

    // Method 3 of this class
    // Main driver method
    public static void main(String[] args)
    {
        // Creating an ArrayList object
        // Declaring object of integer type
        Vector<Integer> A = new Vector<>();

        // Inserting elements in the ArrayList
        // Custom input entries
        A.add(1);
        A.add(2);
        A.add(3);
        A.add(4);

        // Creating another ArrayList
        // Again declaring object of integer type
        Vector<Integer> B = new Vector<>();

        // Inserting elements in the ArrayList
        // Custom input entries
        B.add(1);
        B.add(2);
        B.add(3);

        // Calling the Method1 now to
        // remove the elements from the collection
        Vector<Integer> UpdatedCollection
            = RemoveElements(A, B);

        // Printing the updated collection
        print(A);
    }
}
```

**Output**

```java
1 2 3 
```