# 在 Java 中迭代数组列表

> 原文:[https://www.geeksforgeeks.org/iterating-arraylists-java/](https://www.geeksforgeeks.org/iterating-arraylists-java/)

ArrayList 是 [**集合框架**](https://www.geeksforgeeks.org/collections-in-java-2/) 的一部分，存在于 java.util 包中。它为我们提供了 Java 中的动态数组。尽管它可能比标准数组慢，但在需要对数组进行大量操作的程序中会很有帮助。这个类可以在[T5【Java . util】T6](https://www.geeksforgeeks.org/java-util-package-java/)包中找到。

随着 java 版本的引入和升级，更新的方法正在出现，就好像我们确实从 Java8 中看到了感知 lambda 表达式和流概念在 Java 版本 8 中引入之前是不可用的。

**方法:**

1.  Use for loop
2.  Use while
3.  Use for each loop
4.  Using iterators
5.  Use Lambda expression (only after Java8)
6.  Use enumeration interface

让我们来讨论一下这些方法，我们马上就能意识到开始三种方法只是简单的简单方法，进一步的方法带有一些优化。请记住，虽然遍历元素较少，但我们通常倾向于通过简单的方法进行迭代，否则，如果要插入的元素很大，我们会使用最佳方法。让我们快速总结以上每一种方法。

**方法一:**使用 for 循环

T5】JavaT7

```java
// Java  program to iterate over an ArrayList
// Using for loop

// Importing all utility classes
import java.util.*;

// Main class
class GFG {

    // Main driver method 
    public static void main(String[] args)
    {
        // Creating and initializing the ArrayList
        // Declaring object of integer type
        List<Integer> numbers = Arrays.asList(1, 2, 3,
                                       4, 5, 6, 7, 8);

        // Iterating using for loop
        for (int i = 0; i < numbers.size(); i++)

            // Printing and display the elements in ArrayList
            System.out.print(numbers.get(i) + " ");       
    }
}
```

T8T10**输出**T1

**方法二:**使用 while 循环

T5】JavaT7

```java
// Java Program to Illustrate ArrayList
// Using While Loop

// Importing required classes
import java.util.ArrayList ;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating and initializing the ArrayList
        // Declaring object of integer type
        ArrayList<Integer> al = new ArrayList<Integer>();

        // Adding elements to ArrayList
        // using add() method
        al.add(3);
        al.add(1);
        al.add(7);
        al.add(20);
        al.add(5);

        // Step 1: Setting and initializing a variable
        // as per syntax of while loop
        // Initially declaring and setting
        int val = 0;

        // Step 2: Condition
        // Till our counter variable is lesser than size of
        // ArrayList
        while (al.size() > val) {

            // Printing the element which holds above
            // condition true
            System.out.println(al.get(val));

            // Step 3: Terminating condition by incrementing
            // our counter in each iteration
            val++ ;
        }
    }
}
```

T8T10**输出**T1

**方法三:**对每个循环使用

T5】JavaT7

```java
// Java Program to Iterate over Arraylist
// using for Each loop

// Importing all utility classes
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Declaring and initializing ArrayList
        List<Integer> numbers
            = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8);

        // For Each Loop for iterating ArrayList
        for (Integer i : numbers)

            // Printing the elements of ArrayList
            System.out.print(i + " ");
    }
}
```

T8T10**输出**T1

**方法四:**使用迭代器

## Java

```java
// Java program to iterate over an ArrayList
// Using Iterator

// Importing all utility classes
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Declaring and initializing ArrayList
        List<Integer> numbers
            = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8);

        // Iterating ArrayList using Iterator
        Iterator it = numbers.iterator();

        // Holds true till there is single element
        // remaining in the list
        while (it.hasNext())

            // Print the elements of ArrayList
            System.out.print(it.next() + " ");
    }
}
```

**输出**

```java
1 2 3 4 5 6 7 8 
```