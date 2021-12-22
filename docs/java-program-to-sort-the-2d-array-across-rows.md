# 跨行排序 2D 数组的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序对 2d 数组进行跨行排序/](https://www.geeksforgeeks.org/java-program-to-sort-the-2d-array-across-rows/)

该程序用于对 2D 数组的行进行排序。我们将使用向量的概念对每一行进行排序。

**矢量**

> Vector():创建初始容量为 10 的默认向量。
> 
> 向量 <e>v =新向量<e>()；</e></e>

我们将在此使用的功能:

**1。*****remove all()***:**Java . util . vector . remove all(Collection col)方法用于从向量中移除指定集合中存在的所有元素。**

****语法:****

```
Vector.removeAll(Vector) 
```

****2。*****collections . sort():***此方法用于对向量进行排序。**

****语法:****

```
Collections.sort(Vector)
```

****3。*****add():******这就把矢量中的元素加起来了。*****

******语法:******

```
**Vector.add(value)**
```

******4。*****get():*****这个方法会获取一个 Vector 元素存储在特定的索引中。******

********语法:********

```
**Vector.get(element);**
```

******算法:******

1.  ****逐一遍历每一行。****
2.  ****在向量 v 中添加行 1 的元素****
3.  ****对向量进行排序。****
4.  ****将排序后的元素从向量推回到行。****
5.  ****通过移除所有元素清空向量，以便重新排序。****
6.  ****重复以上步骤，直到所有行都完成。****

******实施:******

******例******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
**// Java Program to Sort the 2D array Across Rows

// Importing required libraries
import java.io.*;
import java.lang.*;
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
        throws java.lang.Exception
    {

        // Custom input 2D matrix
        int[][] arr = { { 1, 8, 4, 7, 3 },
                        { 8, 3, 1, 7, 5 },
                        { 6, 2, 0, 7, 1 },
                        { 2, 6, 4, 1, 9 } };

        // Display message only
        System.out.println("Matrix without sorting \n");

        // Print and display the matrix before sorting
        // using nested for loops
        for (int i = 0; i < 4; i++) {

            for (int j = 0; j < 5; j++) {
                // Printing the matrix elements
                System.out.print(arr[i][j] + " ");
            }

            // New line as we are finished with one row
            System.out.println();
        }

        // New line for better readability
        System.out.println();

        // Creating an object of Vector class
        Vector<Integer> v = new Vector<>();

        for (int i = 0; i < 4; i++) {

            for (int j = 0; j < 5; j++) {
                // Adding elements of row in vector
                v.add(arr[i][j]);
            }

            // Elements in vector gets sorted
            Collections.sort(v);
            for (int j = 0; j < 5; j++) {

                // Sorted elements are pushed back from
                // vector to row
                arr[i][j] = v.get(j);
            }

            // Elements are removed from vector for fresh
            // sorting
            v.removeAll(v);
        }

        // Display message only
        System.out.println("Matrix after sorting \n");

        // Print and display the matrix after sorting
        // using nested for loops
        for (int i = 0; i < 4; i++) {

            for (int j = 0; j < 5; j++) {

                // Printing the matrix elements
                System.out.print(arr[i][j] + " ");
            }

            // New line as we are finished with one row
            System.out.println();
        }
    }
}**
```

******Output**

```
Matrix without sorting 

1 8 4 7 3 
8 3 1 7 5 
6 2 0 7 1 
2 6 4 1 9 

Matrix after sorting 

1 3 4 7 8 
1 3 5 7 8 
0 1 2 6 7 
1 2 4 6 9 
```****