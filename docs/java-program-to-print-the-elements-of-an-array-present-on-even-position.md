# 打印偶数位置数组元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-print-of-elements-of-array-present-on-even-position/](https://www.geeksforgeeks.org/java-program-to-print-the-elements-of-an-array-present-on-even-position/)

任务是打印所有均匀位置的元素。考虑一个例子，我们有一个长度为 6 的数组，我们需要显示存在于 2，4 和 6 位置的所有元素，即；在指数 1，3，5。

**示例:**

```java
Input: [1,2,3,4,5,6]

Output: 2
        4
        6

Input: [1,2]

Output: 2 
```

**进场:**
1)先取一个名为**DisplayElementAtEvenPosition**的班级。
2)然后在主函数内部，用上例中提到的值声明并初始化一个数组。
3)现在，为了在偶数位置显示值，我们需要遍历数组。
4)为此，进行 For 循环并迭代数组，同时用 **2** 增加值，因为我们需要偶数位置的值。
5)方法完成后，编译它以获得输出。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Print the Elements of an Array Present on
// Even Position

import java.io.*;
import java.util.*;

public class EvenPosition {
    public static void main(String[] args)
    {
        // declaration and initialization of array.
        int[] arr = new int[] { 1, 2, 3, 4, 5, 6 };

        // iterating through the array using for loop
        for (int i = 1; i < arr.length; i = i + 2) {

            // print element to the console
            System.out.println(arr[i]);
        }
    }
}
```

**Output**

```java
2
4
6
```

**时间复杂度:** O(n)其中 **n** 是数组的大小

**辅助空间:** O(1)