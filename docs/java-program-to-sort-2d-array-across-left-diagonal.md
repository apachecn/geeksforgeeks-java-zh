# 对左对角线上的 2D 数组进行排序的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到排序-2d-数组-跨左对角/](https://www.geeksforgeeks.org/java-program-to-sort-2d-array-across-left-diagonal/)

[向量类](https://www.geeksforgeeks.org/java-util-vector-class-java/)实现了一个可增长的对象数组。向量基本上属于遗留类，但现在它与集合完全兼容。在 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中找到，实现了 [List](https://www.geeksforgeeks.org/list-interface-java-examples/) 接口，在这里可以使用 List 接口的所有方法。该程序用于对左对角线上的 2D 数组进行排序。我们将使用向量的概念对左对角线进行排序，在此之前，请参考下图。

**图示:**创建矢量

Vector():创建初始容量为 10 的默认向量。

```
Vector<E> v = new Vector<E>();
```

**算法:**

*   逐个遍历对角线元素。条件是(i==j)或(arr[i][i])
*   在向量 v 中添加对角线元素。
*   对向量进行排序。
*   将排序后的元素从向量推回到对角线。

现在，让我们讨论一下在实现部分之前将在上述方法中使用的函数。

**a .**[remove all():](https://www.geeksforgeeks.org/vector-removeall-method-in-java/#:~:text=removeAll(Collection%20col)%20method%20is,present%20in%20the%20collection%20specified.&text=Parameters%3A%20This%20method%20accepts%20a,be%20removed%20from%20the%20vector.)**Java . util . vector . remove all(Collection col)方法用于从向量中移除指定集合中存在的所有元素。**

**语法:**

```
Vector.removeAll(Vector); 
```

****b .**[collections . sort():](https://www.geeksforgeeks.org/collections-sort-java-examples/)**这个方法是用来对向量进行排序的。****

******语法:******

```
**Collections.sort(Vector) ;**
```

******c .**[add():](https://www.geeksforgeeks.org/vector-add-method-in-java/)It**添加矢量中的元素。******

********语法:********

```
**Vector.add(value) ;**
```

******D.** [get():](https://www.geeksforgeeks.org/vector-get-method-in-java/#:~:text=get()%20method%20is%20used,specific%20index%20from%20a%20Vector.&text=Parameters%3A%20This%20method%20accepts%20a,be%20fetched%20from%20the%20Vector.) 这个方法会获取 Vector 中存储在特定索引处的一个元素。****

******语法:******

```
**Vector.get(3);**
```

******示例:******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
**// Java Program to Sort 2D Array Across Left Diagonal

// Importing required classes
import java.io.*;
import java.lang.*;
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
        throws java.lang.Exception
    {

        // Custom input 2D array
        int[][] arr
            = { { 5, 2, 0, 7, 1 }, { 3, 4, 2, 9, 14 },
                { 5, 1, 3, 5, 2 }, { 4, 2, 6, 2, 1 },
                { 0, 6, 3, 5, 1 }, { 1, 4, 7, 2, 8 } };

        // Display message
        System.out.println("Matrix without sorting \n");

        // Nested for loops to display 2D matrix
        for (int i = 0; i < 5; i++) {
            for (int j = 0; j < 5; j++) {

                // Printing elements
                System.out.print(arr[i][j] + " ");
            }

            // By now we are done with one row so
            // new line is needed
            System.out.println();
        }

        // Creating an object of Vector class
        Vector<Integer> v = new Vector<>();

        // Adding elements of diagonal in vector
        // using add() method
        for (int i = 0; i < 5; i++) {
            v.add(arr[i][i]);
        }

        // Sorting elements in vector
        // using Collections.sort() method
        Collections.sort(v);

        // Sorted elements are pushed back from vector to
        // row using get() method
        for (int j = 0; j < 5; j++) {
            arr[j][j] = v.get(j);
        }

        // Display message
        System.out.println("Matrix after sorting \n");

        // Nested for loops to display 2D matrix
        for (int i = 0; i < 5; i++) {
            for (int j = 0; j < 5; j++) {
                System.out.print(arr[i][j] + " ");
            }
            System.out.println();
        }
    }
}**
```

******Output**

```
Matrix without sorting 

5 2 0 7 1 
3 4 2 9 14 
5 1 3 5 2 
4 2 6 2 1 
0 6 3 5 1 
Matrix after sorting 

1 2 0 7 1 
3 2 2 9 14 
5 1 3 5 2 
4 2 6 4 1 
0 6 3 5 5 
```****