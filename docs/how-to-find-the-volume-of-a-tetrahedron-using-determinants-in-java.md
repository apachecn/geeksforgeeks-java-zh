# 如何用 Java 中的行列式求四面体的体积？

> 原文:[https://www . geesforgeks . org/如何使用 java 中的行列式找到四面体的体积/](https://www.geeksforgeeks.org/how-to-find-the-volume-of-a-tetrahedron-using-determinants-in-java/)

给定四面体的顶点。任务是利用行列式来确定四面体的体积。

**进场:**

1.给定四面体的四个顶点(x1，y1，z1)，(x2，y2，z2)，(x3，y3，z3)和(x4，y4，z4)。使用这些顶点创建一个(4 × 4)矩阵，其中坐标三元组形成矩阵的列，在底部附加一个额外的行，每个值为 1。

```java
x1  x2  x3  x4
y1  y2  y3  y4
z1  z2  z3  z4
1   1   1    1
```

2.对于底部有一行 1 的 4 × 4 矩阵，我们可以用给定的简化公式简化成(3 × 3)矩阵。

```java
x1-x4   x2-x4   x3-x4
y1-y4   y2-y4   y3-y4
z1-z4   z2-z4   z3-z4
```

3.四面体的体积等于上述计算出的矩阵[行列式](https://www.geeksforgeeks.org/determinant-of-a-matrix/)绝对值的 1/6 倍。

### 示例:

```java
Input: x1=9, x2=3, x3=7, x4=9, y1=5, y2=0, y3=4, y4=6, z1=1, z2=0, z3=3, z4=0
Output: Volume of the Tetrahedron Using Determinants: 3.0

Input: x1=6, x2=8, x3=5, x4=9, y1=7, y2=1, y3=7, y4=1, z1=6, z2=9, z3=2, z4=6
Output: Volume of the Tetrahedron Using Determinants: 7.0

```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to find the volume of a
// tetrahedron using determinants

import java.io.*;

class VolumeOfADeterminant {
    public static double determinant(double m[][], int n)
    {
        double dt = 0;

        // if the matrix has only
        // one element
        if (n == 1) {
            dt = m[0][0];
        }

        // if the matrix has 4 elements
        // find determinant
        else if (n == 2) {
            dt = m[0][0] * m[1][1] - m[1][0] * m[0][1];
        }

        else {
            dt = 0;
            for (int j1 = 0; j1 < n; j1++) {

                double[][] w = new double[n - 1][];
                for (int k = 0; k < (n - 1); k++) {
                    w[k] = new double[n - 1];
                }
                for (int i = 1; i < n; i++) {
                    int j2 = 0;
                    for (int j = 0; j < n; j++) {
                        if (j == j1)
                            continue;
                        w[i - 1][j2] = m[i][j];
                        j2++;
                    }
                }
                dt += Math.pow(-1.0, 1.0 + j1 + 1.0)
                      * m[0][j1] * determinant(w, n - 1);
            }
        }
        return dt;
    }

    public static void main(String args[])
    {
        // Input the vertices
        int x1 = 5, x2 = 8, x3 = 1, x4 = 9, y1 = 5, y2 = 0,
            y3 = 7, y4 = 8, z1 = 8, z2 = 3, z3 = 4, z4 = 1;

        // create a 4 * 4 matrix
        double[][] m = new double[4][4];

        // Create a matrix of that vertices
        m[0][0] = x1;
        m[0][1] = x2;
        m[0][2] = x3;
        m[0][3] = x4;
        m[1][0] = y1;
        m[1][1] = y2;
        m[1][2] = y3;
        m[1][3] = y4;
        m[2][0] = z1;
        m[2][1] = z2;
        m[2][2] = z3;
        m[2][3] = z4;
        m[3][0] = 1;
        m[3][1] = 1;
        m[3][2] = 1;
        m[3][3] = 1;

        // Converting the 4x4 matrix into 3x3
        double[][] m1 = new double[3][3];
        m1[0][0] = x1 - x4;
        m1[0][1] = x2 - x4;
        m1[0][2] = x3 - x4;
        m1[1][0] = y1 - y4;
        m1[1][1] = y2 - y4;
        m1[1][2] = y3 - y4;
        m1[2][0] = z1 - z4;
        m1[2][1] = z2 - z4;
        m1[2][2] = z3 - z4;

        // find (determinant/6)
        double deter = determinant(m1, 3) / 6;

        // if determinant is negative
        if (deter < 0)
            System.out.println(
                "Volume of the Tetrahedron Using Determinants: "
                + (deter * -1));
        else
            System.out.println(
                "Volume of the Tetrahedron Using Determinants: "
                + (deter * -1));
    }
}
```

**Output**

```java
Volume of the Tetrahedron Using Determinants: 52.333333333333336

```