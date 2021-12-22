# 如何修复 Java 中 int 不可解引用的错误？

> 原文:[https://www . geesforgeks . org/how-fix-int-无法取消引用-java 中的错误/](https://www.geeksforgeeks.org/how-to-fix-int-cannot-be-dereferenced-error-in-java/)

在这里，我们将遵循下面提到的要点来理解和消除错误，并在示例代码

*   Adjust the inspection output slightly in. Introduce errors with examples.
*   Explain the dereference in detail.
*   Finally, how to fix the problem with sample code and output.

如果您在编译代码时遇到此错误？到本文结束时，您将获得关于错误的完整知识，并能够解决您的问题，让我们从一个示例开始。

**例 1:**

## 爪哇

```java
// Java Program to Illustrate Dereference

// Importing required classes
import java.io.*;
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Reading input from keyboard by
        // creating object of Scanner class
        Scanner sc = new Scanner(System.in);

        // Taking input for two integer variables
        int a = sc.nextInt();
        int b = sc.nextInt();

        // Calculating sum of two variables and storing the
        // value in sum variable
        int sum = a + b;

        //  Print and display resultant length
        System.out.println(sum.length);
    }
}
```