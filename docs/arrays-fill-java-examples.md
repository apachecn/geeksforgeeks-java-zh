# 数组.用示例在 Java 中填充()

> 原文:[https://www.geeksforgeeks.org/arrays-fill-java-examples/](https://www.geeksforgeeks.org/arrays-fill-java-examples/)

**java.util.Arrays.fill()** 方法在 [java.util.Arrays 类](https://www.geeksforgeeks.org/array-class-in-java/)中。此方法将指定的数据类型值分配给指定数组的指定范围的每个元素。

```
Syntax:
// Makes all elements of a[] equal to "val"
public static void fill(int[] a, int val)

// Makes elements from from_Index (inclusive) to to_Index
// (exclusive) equal to "val"
public static void fill(int[] a, int from_Index, int to_Index, int val)

This method doesn't return any value.

```

```
Exceptions it Throws:
IllegalArgumentException - if from_Index > to_Index
ArrayIndexOutOfBoundsException - if from_Index  a.length

```

**示例:**

**我们可以填满整个阵列。**

```
// Java program to fill a subarray of given array
import java.util.Arrays;

public class Main
{
    public static void main(String[] args)
    {
        int ar[] = {2, 2, 1, 8, 3, 2, 2, 4, 2};

        // To fill complete array with a particular
        // value
        Arrays.fill(ar, 10);
        System.out.println("Array completely filled" +
                  " with 10\n" + Arrays.toString(ar));
    }
}
```

**输出:**

```
Array completely filled with 10
[10, 10, 10, 10, 10, 10, 10, 10, 10]

```

**我们可以填充部分数组。**

```
// Java program to fill a subarray array with 
// given value.
import java.util.Arrays;

public class Main
{
    public static void main(String[] args)
    {
        int ar[] = {2, 2, 2, 2, 2, 2, 2, 2, 2};

        // Fill from index 1 to index 4.
        Arrays.fill(ar, 1, 5, 10);

        System.out.println(Arrays.toString(ar));
    }
}
```

**输出:**

```
[2, 10, 10, 10, 10, 2, 2, 2, 2]
```

**我们可以填充一个多维数组**
我们可以使用一个循环来填充一个多维数组。
T4【1)补 2D 阵

```
// Java program to fill a multidimensional array with 
// given value.
import java.util.Arrays;

public class Main
{
    public static void main(String[] args)
    {
        int [][]ar = new int [3][4];

        // Fill each row with 10. 
        for (int[] row : ar)
            Arrays.fill(row, 10);

        System.out.println(Arrays.deepToString(ar));
    }
}
```

**输出:**

```
[[10, 10, 10, 10], [10, 10, 10, 10], [10, 10, 10, 10]]

```

**2)填充 3D 阵列**

```
// Java program to fill a multidimensional array with 
// given value. 

import java.util.Arrays;

class GFG {

    public static void main(String[] args) {
        int[][][] ar = new int[3][4][5];

        // Fill each row with -1. 
        for (int[][] row : ar) {
            for (int[] rowColumn : row) {
                Arrays.fill(rowColumn, -1);
            }
        }

        System.out.println(Arrays.deepToString(ar));
    }
}
```

**输出:**

```
[[[-1, -1, -1, -1, -1], [-1, -1, -1, -1, -1], [-1, -1, -1, -1, -1], [-1, -1, -1, -1, -1]], [[-1, -1, -1, -1, -1], [-1, -1, -1, -1, -1], [-1, -1, -1, -1, -1], [-1, -1, -1, -1, -1]], [[-1, -1, -1, -1, -1], [-1, -1, -1, -1, -1], [-1, -1, -1, -1, -1], [-1, -1, -1, -1, -1]]]

```

本文由**莫希特·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。