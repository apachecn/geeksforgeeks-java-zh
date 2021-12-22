# 计算列表运行总数的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到计算-运行-列表总数/](https://www.geeksforgeeks.org/java-program-to-compute-the-running-total-of-a-list/)

列表是存储在一起形成集合的有序元素序列。列表是执行位置访问和基于索引的元素检索的结构。列表可用于存储重复和空元素。元素序列的累计是元素的前一个总和和当前接收的整数值的总和。可以使用内置界面 **< <声明和创建列表> >**

按原样将列表的第一个索引元素存储到运行总数中。元素的前一个总和被初始化为此列表的第一个索引元素。然后，对于每个新元素，我们将其添加到之前的总和中。这个更新后的总和值成为相应索引之前的累计值。然后将其添加到运行总数列表中。以下是程序描述:

**程序:**计算列表中总和所遵循的步骤

*   **第一步:**申报清单，用于存储运行总数。
*   **第二步**:将原列表的第一个元素复制到正在运行的总列表中。
*   **步骤 3:** 最初，向列表的第 0 个元素声明 sum。
*   **步骤 4:** 从列表的第一个索引开始迭代列表。
*   **第五步:**将当前元素加到上一个和上。
*   **第 6 步:**将之前的总和复制到正在运行的总和。
*   **第 7 步:**使用 [*hasNext()*](https://www.geeksforgeeks.org/scanner-hasnextint-method-in-java-with-examples/) 方法迭代正在运行的总列表的元素，直到列表中剩下一个元素。
*   **步骤 8:** 打印将运行总列表的列表。

**实现:**下面的 java 程序用来说明元素列表运行总数的计算。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Compute the Running Total of a List

// Importing all classes of input/output java library
// Importing all classes from java.util package
// Iterator class included in java.util package
import java.io.*;
import java.util.*;

// Class- computing running total in list
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an List of integer type
        List<Integer> list = new ArrayList<Integer>();

        // Adding elements to List
        // Custom inputs
        list.add(2);
        list.add(4);
        list.add(6);
        list.add(8);
        list.add(10);
        list.add(12);

        // printing the contents of the list
        System.out.print("Original List :                      ");

        // Iterator
        Iterator iterator = list.iterator();

        // Iterating over the elements of the List
        // using hasNext() which holds true till there is
        // further more element in List
        while (iterator.hasNext()) {

            System.out.print(iterator.next() + " ");
        }

        // Running total concept in List

        // Step 1 : Declaring list for storing running total
        // of list
        List<Integer> runningtotal
            = new ArrayList<Integer>();

        // Step 2: Copy first element of original list to
        // running total list
        runningtotal.add(list.get(0));

        // Step 3: Initially, declaring sum to the 0th
        // element of list
        int prev_sum = list.get(0);

        // Declaring and maintaining counter
        int i = 1;

        // Step 4: Iterating over the list starting with the
        // 1st index
        while (i < list.size()) {

            // Step 5: Adding current element to prev_sum
            prev_sum += list.get(i);

            // Step 6: Copying prev_sum to the running total
            runningtotal.add(prev_sum);

            // Step 6: Incrementing counter
            i++;
        }

        System.out.println();

        // Display Message
        System.out.print("Running total List of Original List: ");

        iterator = runningtotal.iterator();

        // Iterating over the elements of the running total
        // list using hasNext() method which holds true till
        // there is single element remaining in List
        while (iterator.hasNext()) {

          // printing all elements of List
            System.out.print(iterator.next() + " ");
        }
    }
}
```

**Output**

```
Original List :                      2 4 6 8 10 12 
Running total List of Original List: 2 6 12 20 30 42
```