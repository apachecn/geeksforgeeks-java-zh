# 说明总分和百分比计算的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-图解-总分和百分比-计算/](https://www.geeksforgeeks.org/java-program-to-illustrate-total-marks-and-percentage-calculation/)

说明总分数和百分比计算的 Java 程序可以通过将所有科目的分数存储在一个数组中，并对所有科目的分数求和，然后分别取所有分数的平均值来完成。

**例**T0】

**方法:**

*   Enter the number n of subjects and the markers of these subjects into a one-dimensional array, such as the marker [].
*   Create a variable total_marks to store the total number of all marks.
*   To print the percentage of this student, divide total_marks by n.

以下是上述方法的示例。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate Total
// marks and Percentage Calculation
import java.io.*;
class GFG {
    public static void main(String[] args)
    {
        int N = 5, total_marks = 0;
        float percentage;

        // create 1-D array to store marks
        int marks[] = { 89, 75, 82, 60, 95 };

        // calculate total marks
        for (int i = 0; i < N; i++) {
            total_marks += marks[i];
        }
        System.out.println("Total Marks : " + total_marks);

        // calculate percentage
        percentage = (total_marks / (float)N);
        System.out.println(
            "Total Percentage : " + percentage + "%");
    }
}
```

**Output**

```java
Total Marks : 401
Total Percentage : 80.2%

```

**时间复杂度:** O(N)

**空间复杂度:** O(1)