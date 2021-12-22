# 打印数字螺旋图案的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序转打印-数字螺旋图案/](https://www.geeksforgeeks.org/java-program-to-print-spiral-pattern-of-numbers/)

给定 n 作为矩阵的大小，任务是打印 n 大小的螺旋图案。

**示例:**

```
Input : n = 4
Output: 1   2  3 4 
    12 13 14 5 
    11 16 15 6 
    10  9  8 7
```

**螺旋图案预览:**

![Lightbox](img/a8211e835983cf7fe7651fd8447826cf.png)

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class GFG {

    public static void printSpiral(int size)
    {

        // Create row and col
        // to traverse rows and columns
        int row = 0, col = 0;

        int boundary = size - 1;
        int sizeLeft = size - 1;
        int flag = 1;

        // Variable to determine the movement
        // r = right, l = left, d = down, u = upper
        char move = 'r';

        // Array for matrix
        int matrix[][] = new int[size][size];

        for (int i = 1; i < size * size + 1; i++) {

            // Assign the value
            matrix[row][col] = i;

            // switch-case to determine the next index
            switch (move) {

            // If right, go right
            case 'r':
                col += 1;
                break;

            // if left, go left
            case 'l':
                col -= 1;
                break;

            // if up, go up
            case 'u':
                row -= 1;
                break;

            // if down, go down
            case 'd':
                row += 1;
                break;
            }

            // Check if the matrix
            // has reached array boundary
            if (i == boundary) {

                // Add the left size for the next boundary
                boundary += sizeLeft;

                // If 2 rotations has been made,
                // decrease the size left by 1
                if (flag != 2) {

                    flag = 2;
                }
                else {

                    flag = 1;
                    sizeLeft -= 1;
                }

                // switch-case to rotate the movement
                switch (move) {

                // if right, rotate to down
                case 'r':
                    move = 'd';
                    break;

                // if down, rotate to left
                case 'd':
                    move = 'l';
                    break;

                // if left, rotate to up
                case 'l':
                    move = 'u';
                    break;

                // if up, rotate to right
                case 'u':
                    move = 'r';
                    break;
                }
            }
        }

        // Print the matrix
        for (row = 0; row < size; row++) {
            for (col = 0; col < size; col++) {

                int n = matrix[row][col];
                System.out.print((n < 10) ? (n + " ")
                                          : (n + " "));
            }

            System.out.println();
        }
    }

    // Driver Code
    public static void main(String[] args)
    {

        // Get the size of size
        int size = 5;

        // Print the Spiral Pattern
        printSpiral(size);
    }
}
```

**Output**

```
1 2 3 4 5 
16 17 18 19 6 
15 24 25 20 7 
14 23 22 21 8 
13 12 11 10 9 

```