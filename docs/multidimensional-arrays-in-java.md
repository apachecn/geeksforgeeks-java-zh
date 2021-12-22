# Java 中的多维数组

> 原文:[https://www . geesforgeks . org/多维数组-in-java/](https://www.geeksforgeeks.org/multidimensional-arrays-in-java/)

[数组 Java 中的基础](https://www.geeksforgeeks.org/arrays-in-java/)
**多维数组**可以简单的定义为数组的数组。多维数组中的数据以表格形式存储(按行主顺序)。

**语法:**

> **数据类型**【第一维】【第二维】【】..【第 n 个维度】**数组 _ 名称** = **新增** **数据 _ 类型**【大小 1】【大小 2】…。[SiZen]；

其中:

*   **数据类型**:数组中要存储的数据类型。例如:int、char 等。
*   **维度**:创建的数组的维度。
    比如:1D、2D 等。
*   **数组名**:数组名
*   **尺寸 1、尺寸 2、…、尺寸 N** :各尺寸的尺寸。

**示例:**

```
Two dimensional array:
int[][] twoD_arr = new int[10][20];

Three dimensional array:
int[][][] threeD_arr = new int[10][20][30];

```

**多维数组的大小**:可以存储在多维数组中的元素总数可以通过乘以所有维度的大小来计算。

**例如:**
数组 **int[][] x = new int[10][20]** 总共可以存储(10*20) = 200 个元素。
同样，数组**int[][][]x = new int[5][10][20]**总共可以存储(5*10*20) = 1000 个元素。

## 二维阵列(2D 阵列)

二维数组是多维数组的最简单形式。为了便于理解，二维数组可以看作一维数组的数组。

**间接申报方式:**

*   **声明–语法:**

    ```
    data_type[][] array_name = new data_type[x][y];
            For example: int[][] arr = new int[10][20];

    ```

*   **初始化–语法:**

    ```
    array_name[row_index][column_index] = value;
            For example: arr[0][0] = 1;

    ```

**示例:**

```
class GFG {
    public static void main(String[] args)
    {

        int[][] arr = new int[10][20];
        arr[0][0] = 1;

        System.out.println("arr[0][0] = " + arr[0][0]);
    }
}
```

**Output:**

```
arr[0][0] = 1

```