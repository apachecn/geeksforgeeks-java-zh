# 跨列排序 2D 数组的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-排序-2d-数组-跨列/](https://www.geeksforgeeks.org/java-program-to-sort-2d-array-across-columns/)

**向量**类实现了一个可增长的对象数组。向量基本上属于遗留类，但现在它与集合完全兼容。在[java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中找到，实现了 [List](https://www.geeksforgeeks.org/list-interface-java-examples/) 接口，所以我们可以在这里使用 List 接口的所有方法。该程序用于对跨列的 2D 数组进行排序。我们将使用向量的概念来对每一列进行排序。

**算法:**

1.  Traverse each column one by one.
2.  Add the element of column 1 to vector v.
3.  Sort the vectors.
4.  Push the sorted elements back from the vector to the column.
5.  Clear the vector by removing all elements for fresh sorting.
6.  Repeat the above steps until all columns are completed.

**图示:**创建矢量

这里我们创建一个初始容量为 10 的默认向量，语法如下:

```
Vector<E> v = new Vector<E>();
```

将用于实现目标的功能如下:

**a .**[remove all()](https://www.geeksforgeeks.org/vector-removeall-method-in-java/#:~:text=removeAll(Collection%20col)%20method%20is,present%20in%20the%20collection%20specified.&text=Parameters%3A%20This%20method%20accepts%20a,be%20removed%20from%20the%20vector.)**:**Java . util . vector . remove all(Collection col)方法用于从向量中移除指定集合中存在的所有元素。

**语法:**

```
Vector.removeAll(Vector)  
```

**b .**T2【collections . sort()T4:这个方法是用来对向量进行排序的。

**语法:**

```
Collections.sort(Vector)
```

**C.** [add():](https://www.geeksforgeeks.org/vector-add-method-in-java/) 这个方法是用来在向量中添加元素的。

**语法:**

```
Vector.add(value)
```

**D.** [get():](https://www.geeksforgeeks.org/vector-get-method-in-java/#:~:text=get()%20method%20is%20used,specific%20index%20from%20a%20Vector.&text=Parameters%3A%20This%20method%20accepts%20a,be%20fetched%20from%20the%20Vector.) 该方法将获取 Vector 中存储在特定索引处的元素

**语法:**

```
Vector.get(3);
```

**示例**

## Java

```
// Java Program to Sort 2D array across Columns

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

        // Custom input for 2D array
        int[][] arr = { { 7, 2, 0, 5, 1 },
                        { 3, 8, 2, 9, 14 },
                        { 5, 1, 0, 5, 2 },
                        { 4, 2, 6, 0, 1 } };

        // Display message for better readability
        System.out.println("Matrix without sorting \n");

        // Nested iteration to display matrix
        for (int i = 0; i < 4; i++) {

            for (int j = 0; j < 5; j++) {

                // Printing elements of 2D matrix
                System.out.print(arr[i][j] + " ");
            }
            // New line as we are done with row
            System.out.println();
        }

        // Creating an object of Vector class
        Vector<Integer> v = new Vector<>();

        // Nested iteration using for loops
        for (int i = 0; i < 5; i++) {
            for (int j = 0; j < 4; j++) {

                // Adding elements of columns in vector
                // using add() method
                v.add(arr[j][i]);
            }

            // Sorting elements in vector
            // using sort() method
            Collections.sort(v);

            for (int j = 0; j < 4; j++) {

                // Sorted elements are pushed back
                // from vector to column
                arr[j][i] = v.get(j);
            }

            // Elements are removed from vector for
            // fresh sorting using remove() method
            v.removeAll(v);
        }

        // Printing matrix after sorting
        System.out.println("Matrix after sorting \n");

        for (int i = 0; i < 4; i++) {
            for (int j = 0; j < 5; j++) {

                System.out.print(arr[i][j] + " ");
            }

            System.out.println();
        }
    }
}
```

**输出**

```
Matrix without sorting 

7 2 0 5 1 
3 8 2 9 14 
5 1 0 5 2 
4 2 6 0 1 
Matrix after sorting 

3 1 0 0 1 
4 2 0 5 1 
5 2 2 5 2 
7 8 6 9 14 
```