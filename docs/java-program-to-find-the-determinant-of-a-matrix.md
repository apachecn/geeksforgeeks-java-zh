# 寻找矩阵行列式的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-find-a-matrix 的行列式/](https://www.geeksforgeeks.org/java-program-to-find-the-determinant-of-a-matrix/)

矩阵的行列式是只能为方阵定义的实数，即矩阵的行数和列数必须相等。此外，它有助于确定线性方程组以及计算所述矩阵的逆。

**计算程序:**

*   First, we need to calculate the cofactors of all elements in the first row or column of the matrix.
*   Then, each element in the first row or column is multiplied by their respective cofactor.
*   Finally, we need to add them up with alternating symbols.

**例:**

*   ***Determinant of 2 * 2 matrix:***

```
[4, 3]
[2, 3]

= (4*3)-(3*2)
= 12-6
= 6
```

*   ***Determinant of 3 * 3 matrix:***

```
[1, 3, -2]
[-1, 2, 1]
[1, 0, -2]

= 1(-4-0)-3(2-1)+(-2)(0-2)
= -4-3+4
= -3
```

**注:**

1.  **1*1** 矩阵的行列式就是元素本身。
2.  所述矩阵的任何元素的因子 的 **C** ***可以通过从所述矩阵中消除该元素的行和列来计算。***

让我们*看一个例子以便得到*一个*清晰的概念*上面的*题目。*

**示例:使用递归**

## Java

```
// Java program to find
// Determinant of a matrix
class GFG {

    // Dimension of input square matrix
    static final int N = 2;

    // Function to get cofactor of
    // mat[p][q] in temp[][]. n is
    // current dimension of mat[][]
    static void getCofactor(int mat[][], int temp[][],
                            int p, int q, int n)
    {
        int i = 0, j = 0;

        // Looping for each element
        // of the matrix
        for (int row = 0; row < n; row++) {
            for (int col = 0; col < n; col++) {
                // Copying into temporary matrix
                // only those element which are
                // not in given row and column
                if (row != p && col != q) {
                    temp[i][j++] = mat[row][col];
                    // Row is filled, so increase
                    // row index and reset col index
                    if (j == n - 1) {
                        j = 0;
                        i++;
                    }
                }
            }
        }
    }

    /* Recursive function for finding determinant
    of matrix. n is current dimension of mat[][]. */
    static int determinantOfMatrix(int mat[][], int n)
    {
        int D = 0; // Initialize result

        // Base case : if matrix
        // contains single element
        if (n == 1)
            return mat[0][0];

        // To store cofactors
        int temp[][] = new int[N][N];

        // To store sign multiplier
        int sign = 1;

        // Iterate for each element of first row
        for (int f = 0; f < n; f++) {
            // Getting Cofactor of mat[0][f]
            getCofactor(mat, temp, 0, f, n);
            D += sign * mat[0][f]
                 * determinantOfMatrix(temp, n - 1);

            // terms are to be added
            // with alternate sign
            sign = -sign;
        }

        return D;
    }

    /* function for displaying the matrix */
    static void display(int mat[][], int row, int col)
    {
        for (int i = 0; i < row; i++) {
            for (int j = 0; j < col; j++)
                System.out.print(mat[i][j]);

            System.out.print("\n");
        }
    }

    // Driver code
    public static void main(String[] args)
    {

        int mat[][] = { { 4, 3 }, { 2, 3 } };

        System.out.print("Determinant "
                         + "of the matrix is : "
                         + determinantOfMatrix(mat, N));
    }
}
```

**输出**

```
Determinant of the matrix is : 6
```

**时间复杂度:** O(n <sup>3</sup> )

**示例:非递归实现**

## Java

```
// Java program to find Determinant of a matrix
class GFG {

    // Dimension of input square matrix
    static final int N = 4;

    // Function to get determinant of matrix
    static int determinantOfMatrix(int mat[][], int n)
    {
        int num1, num2, det = 1, index,
                        total = 1; // Initialize result

        // temporary array for storing row
        int[] temp = new int[n + 1];

        // loop for traversing the diagonal elements
        for (int i = 0; i < n; i++) {
            index = i; // initialize the index

            // finding the index which has non zero value
            while (mat[index][i] == 0 && index < n) {
                index++;
            }
            if (index == n) // if there is non zero element
            {
                // the determinant of matrix as zero
                continue;
            }
            if (index != i) {
                // loop for swaping the diagonal element row
                // and index row
                for (int j = 0; j < n; j++) {
                    swap(mat, index, j, i, j);
                }
                // determinant sign changes when we shift
                // rows go through determinant properties
                det = (int)(det * Math.pow(-1, index - i));
            }

            // storing the values of diagonal row elements
            for (int j = 0; j < n; j++) {
                temp[j] = mat[i][j];
            }

            // traversing every row below the diagonal
            // element
            for (int j = i + 1; j < n; j++) {
                num1 = temp[i]; // value of diagonal element
                num2 = mat[j]
                          [i]; // value of next row element

                // traversing every column of row
                // and multiplying to every row
                for (int k = 0; k < n; k++) {
                    // multiplying to make the diagonal
                    // element and next row element equal
                    mat[j][k] = (num1 * mat[j][k])
                                - (num2 * temp[k]);
                }
                total = total * num1; // Det(kA)=kDet(A);
            }
        }

        // multiplying the diagonal elements to get
        // determinant
        for (int i = 0; i < n; i++) {
            det = det * mat[i][i];
        }
        return (det / total); // Det(kA)/k=Det(A);
    }

    static int[][] swap(int[][] arr, int i1, int j1, int i2,
                        int j2)
    {
        int temp = arr[i1][j1];
        arr[i1][j1] = arr[i2][j2];
        arr[i2][j2] = temp;
        return arr;
    }

    // Driver code
    public static void main(String[] args)
    {
        int mat[][] = { { 1, 0, 2, -1 },
                        { 3, 0, 0, 5 },
                        { 2, 1, 4, -3 },
                        { 1, 0, 5, 0 } };

        // Function call
        System.out.printf(
            "Determinant of the matrix is : %d",
            determinantOfMatrix(mat, N));
    }
}
```

**输出**

```
Determinant of the matrix is : 30
```

**时间复杂度:** O(n <sup>3</sup> )