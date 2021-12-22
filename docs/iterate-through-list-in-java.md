# 用 Java 迭代列表

> 原文:[https://www.geeksforgeeks.org/iterate-through-list-in-java/](https://www.geeksforgeeks.org/iterate-through-list-in-java/)

java 中的列表允许我们维护有序的对象集合。在 Java 中，重复元素和空元素也可以存储在列表中。List 接口是 **java.util** 包的一部分，它继承了 Collection 接口。它保留了插入的顺序。

在 Java 中有几种方法可以迭代 List。下文将讨论这些问题:

**方法:**

1.  Use cycle (naive method)
    *   Used for circulation
    *   [for-every cycle](https://www.geeksforgeeks.org/for-each-loop-in-java/)
    *   And circulation
2.  Use [iterator](https://www.geeksforgeeks.org/iterators-in-java/)
3.  Use [list iterator](https://www.geeksforgeeks.org/arraylist-listiterator-method-in-java-with-examples/)
4.  Use λ expression
5.  使用[小溪。foreach()](https://www.geeksforgeeks.org/stream-foreach-method-java-examples/)

**方法 1-A:简单循环**

每个元素都可以通过迭代使用简单的 for 循环来访问。可以使用索引作为循环变量来访问索引。

**语法:**

```java
for (i = 0; i < list_name.size(); i++) 
{
  // code block to be executed
}
```

**示例**

## Java

```java
// Java Program to iterate over List
// Using simple for loop

// Importing all classes of
// java.util package
import java.util.*;

// CLass
class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Creating a ArrayList
        List<String> myList = new ArrayList<String>();

        // Adding elements to the list
        // Custom inputs
        myList.add("A");
        myList.add("B");
        myList.add("C");
        myList.add("D");

        // For loop for iterating over the List
        for (int i = 0; i < myList.size(); i++) {

            // Print all elements of List
            System.out.println(myList.get(i));
        }
    }
}
```

**输出**

```java
A
B
C
D
```

**方法 1-B:增强循环**

每个元素都可以使用增强的 for 循环通过迭代来访问。这个循环是在 J2SE 5.0 中引入的。这是遍历 for 循环的另一种方法。它使代码更易读。

**语法:**

```java
for(data_type variable : List_name)
{  
 // Body of the loop. 
 // Each element can be accessed using variable.  
}
```

## Java

```java
// Java Program to Iterate over a List
// using enhanced for loop (for-each)

// Importing all classes of
// java.util package
import java.util.*;

// Class
class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Creating an Arraylist
        List<String> myList = new ArrayList<String>();

        // Adding elements to the List
        // Custom inputs
        myList.add("A");
        myList.add("B");
        myList.add("C");
        myList.add("D");

        // Using enhanced for loop(for-each) for iteration
        for (String i : myList) {

            // Print all elements of ArrayList
            System.out.println(i);
        }
    }
}
```

**输出**

```java
A
B
C
D
```