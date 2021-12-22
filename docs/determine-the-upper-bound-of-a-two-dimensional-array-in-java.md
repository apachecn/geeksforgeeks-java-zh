# 确定 Java 中二维数组的上限

> 原文:[https://www . geesforgeks . org/确定 java 中二维数组的上限/](https://www.geeksforgeeks.org/determine-the-upper-bound-of-a-two-dimensional-array-in-java/)

[Java 中的多维数组](https://www.geeksforgeeks.org/multidimensional-arrays-in-java/)很常见，可以称为数组的数组。Java 中二维数组中的数据以 2D 表格的形式存储。二维数组是多维数组的最简单形式。为了更容易理解，二维数组可以看作一维数组的数组。二维数组是用两个维度声明的，这两个维度也被称为它们的边界。

**数组的语法:**

```
data_type[][] array_name = new data_type[x][y];

```

例如:int[][]arr = new int[20][30]；// 20 X 30 阵列的阵列

**数组的直接声明:**

```
data_type[][] array_name = {
{valueR1C1, valueR1C2, ....},
{valueR2C1, valueR2C2, ....}
};

```

例如:int[][] arr = {{1，2}，{3，4 } }；

**数组中值的分配**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Allocation of values in an Array of Arrays
class GFG {
    public static void main(String[] args)
    {

        int[][] arr = new int[20][30];
        arr[0][0] = 100;

        System.out.println("arr[0][0] = " + arr[0][0]);
    }
}
```

**Output**

```
arr[0][0] = 100
```

**打印完整的数组**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Printing complete Array of Arrays
class GFG {
    public static void main(String[] args)
    {

        int[][] arr = { { 1, 2 }, { 3, 4 } };

        for (int i = 0; i < 2; i++)
            for (int j = 0; j < 2; j++)
                System.out.println("arr[" + i + "][" + j
                                   + "] = " + arr[i][j]);
    }
}
```

**Output**

```
arr[0][0] = 1
arr[0][1] = 2
arr[1][0] = 3
arr[1][1] = 4
```

java 中的数组数组实际上是一维数组的数组。二维数组的每一行都有一个保存列数的长度字段。但是，我们可以使用以下方法获得行上限和列维度:

```
int row_bound = array_name.length;
int column_bound = array_name[0].length;

```

**确定阵列的尺寸**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Determine the Dimension of an Array of Arrays
class GFG {
    public static void main(String args[])
    {
        int[][] arr = new int[10][20];
        int row_bound = arr.length;
        int column_bound = arr[0].length;
        System.out.println("Dimension 1: " + row_bound);
        System.out.println("Dimension 2: " + column_bound);
    }
}
```

**Output**

```
Dimension 1: 10
Dimension 2: 20
```

***注意:*** 重要的是要明白 Java 并不是真的有二维数组。Java 数组本质上是参差不齐的。它有数组数组。所以列级别没有一个上限/长度。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// row bound and column bounds
class GFG {
    public static void main(String args[])
    {
        int[][] arr = { { 1, 2 },
                        { 3 },
                        { 4 },
                        { 5, 6, 7, 8 },
                        { 9, 10, 11, 12, 13, 14, 15 } };
        int row_bound = arr.length;
        int column_bound1 = arr[0].length;
        int column_bound2 = arr[1].length;
        int column_bound5 = arr[4].length;
        System.out.println("Dimension 1: " + row_bound);
        System.out.println("Dimension 2: " + column_bound1);
        System.out.println("Dimension 3: " + column_bound2);
        System.out.println("Dimension 4: " + column_bound5);
    }
}
```

**Output**

```
Dimension 1: 5
Dimension 2: 2
Dimension 3: 1
Dimension 4: 7
```