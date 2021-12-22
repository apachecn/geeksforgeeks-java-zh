# 在 Java 中实现铜匠 Winograd 算法

> 原文:[https://www . geeksforgeeks . org/impering-copper Smith-winograd-algorithm-in-Java/](https://www.geeksforgeeks.org/implementing-coppersmith-winograd-algorithm-in-java/)

**科波菲尔·维诺格拉算法**是迄今为止已知的矩阵乘法算法中渐进最快的算法。在实际中很少使用具有优于**斯特拉森**计算的渐近运行时间的算法，因为它们运行场合中的巨大稳定因素使它们不合适。

它可以在 O(n^{2.375477}时间内乘以两个 n × sn 矩阵。它用于检查矩阵乘法。

它决定矩阵是否等价于在 O(kn^2).的 2^-k 下具有失败期望值的 k 的选择值

**例**

```java
Input:M1={{1,2},
      {3,4}}
      M2={{3,2},
          {5,1}}
      Result={{13,4},
              {29,10}}
Output:Resultant matrix is matching

```

**算法**

```java
// Task is to verify matrix multiplication as M1*M2=M3 or not.
1\. Start
2\. Take Matrices M1, M2, M3 as an input of (n*n).
3\. Choose matrix a[n][1] randomly to which component will be 0 or 1.
4\. Calculate M2 * a, M3 * a and then M1 * (M2 * a) for computing the expression,
   M1 * (M2 * a) - M3 * a.
5\. Verify if M1 * (M2 * a) - M3 * a = 0 or not.
6\. If it is zero or false, then matrix multiplication is correct otherwise not.
7\. End

```

下面是上述方法的实现。

## 爪哇

```java
// Implementing Coppersmith Winograd Algorithm in Java
import java.io.*;
import java.util.Random;

class GFG {

    public static boolean coppersmithWinograd(double[][] M1,
                                       double[][] M2,
                                       double[][] M3, int n)
    {
        double[][] a = new double[n][1];
        Random rand = new Random();
        for (int i = 0; i < n; i++) {
            a[i][0] = rand.nextInt() % 2;
        }

        double[][] M2a = new double[n][1];
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < 1; j++) {
                for (int k = 0; k < n; k++) {
                    M2a[i][j]
                        = M2a[i][j] + M2[i][k] * a[k][j];
                }
            }
        }

        double[][] M3a = new double[n][1];
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < 1; j++) {
                for (int k = 0; k < n; k++) {
                    M3a[i][j]
                        = M3a[i][j] + M3[i][k] * a[k][j];
                }
            }
        }

        double[][] M12a = new double[n][1];
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < 1; j++) {
                for (int k = 0; k < n; k++) {
                    M12a[i][j]
                        = M12a[i][j] + M1[i][k] * M2a[k][j];
                }
            }
        }
        for (int i = 0; i < n; i++) {
            M12a[i][0] -= M3a[i][0];
        }
        boolean sameResultantMatrix = true;
        for (int i = 0; i < n; i++) {
            if (M12a[i][0] == 0)
                continue;
            else
                sameResultantMatrix = false;
        }
        return sameResultantMatrix;
    }

    // Driver's Function
    public static void main(String[] args)
    {

        /// "Input the dimension of the matrices: "
        int n;
        n = 2;
        // "Input the 1st or M1 matrix: "
        double[][] M1 = { { 1, 2 }, { 3, 4 } };
        // "Input the 2nd or M2 matrix: "

        double[][] M2 = { { 2, 0 }, { 1, 2 } };

        // "Input the result or M3 matrix: "
        double[][] M3 = { { 4, 4 }, { 10, 8 } };

        if (coppersmithWinograd(M1, M2, M3, n))
            System.out.println("Resultant matrix is Matching");
        else
            System.out.println("Resultant matrix is not Matching");
    }
}
```

**输出**

```java
Resultant matrix is Matching

```

**时间复杂度:** O(n^{2.375477})