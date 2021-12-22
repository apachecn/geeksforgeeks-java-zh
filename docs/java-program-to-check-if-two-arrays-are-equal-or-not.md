# 检查两个数组是否相等的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序检查两个数组是否相等/](https://www.geeksforgeeks.org/java-program-to-check-if-two-arrays-are-equal-or-not/)

给定两个长度相等的给定数组，任务是找出给定数组是否相等。如果两个数组都包含相同的元素集并且顺序相同，则称这两个数组相等。

**注意:**如果有重复，那么重复元素的计数应该相同，两个数组才相等。

**示例:**

```
Input  : arr1[] = {1, 2, 5, 4, 0};
         arr2[] = {1, 2, 5, 4, 0}; 
Output : Yes

Input  : arr1[] = {1, 2, 5, 4, 0, 2};
         arr2[] = {2, 4, 5, 0}; 
Output : No

Input : arr1[] = {1, 7, 7};
        arr2[] = {7, 7, 1};
Output : No

```

**方法 1:使用预定义的方法**

*   首先，我们将初始化两个数组，并将元素插入这两个数组中。
*   之后，调用 [Arrays.equal()](https://www.geeksforgeeks.org/java-util-arrays-equals-java-examples/) 函数检查两个数组是否相等，结果将存储到一个布尔变量中，即**结果**。
*   最后，将打印结果。

**示例:**下面是上述方法的实现。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to find the if the arrays are equal

import java.util.Arrays;

public class CheckArraysEqual {
    public static void main(String[] args)
    {
        // Initializing the first array
        int a[] = { 30, 25, 40 };

        // Initializing the second array
        int b[] = { 30, 25, 40 };

        // store the result
        // Arrays.equals(a, b) function is used to check
        // whether two arrays are equal or not
        boolean result = Arrays.equals(a, b);

        // condition to check whether the
        // result is true or false
        if (result == true) {
            // Print the result
            System.out.println("Two arrays are equal");
        }
        else {
            // Print the result
            System.out.println("Two arrays are not equal");
        }
    }
}
```

**Output**

```
Two arrays are equal
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to find the if the arrays are equal

import java.util.Arrays;

public class CheckArraysEqual {
    public static void main(String[] args)
    {
        // Initializing the first array
        int a[] = { 30, 25, 40, 23 };

        // Initializing the second array
        int b[] = { 30, 26, 40 };

        // store the result
        // Arrays.equals(a, b) function is used to check
        // whether two arrays are equal or not
        boolean result = Arrays.equals(a, b);

        // condition to check whether the
        // result is true or false
        if (result == true) {
            // Print the result
            System.out.println("Two arrays are equal");
        }
        else {
            // Print the result
            System.out.println("Two arrays are not equal");
        }
    }
}
```

**Output**

```
Two arrays are not equal
```

**时间复杂度:**O(n)
T5】辅助空间: O(1)

**方法二:不使用预定义函数**

*   首先，我们将初始化两个数组 **a** 和 **b** ，并在两个数组中插入元素。然后创建一个名为**结果**的布尔变量来存储检查后的结果。
*   然后我们将检查数组的长度，数组的长度是否相等。
*   如果相等，循环将对每个元素重复，直到数组结束。如果某处某个元素不相等，那么我们将使结果为**假**。
*   如果**结果**变量的值为**假**，则表示数组不相等。
*   如果数组相等，那么结果变量的值将保持为真。
*   此外，如果数组的长度不相等，它将返回 false。

**例 1** :以下是上述方法的实现。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to check if the arrays are equal

public class checkArraysEqual {
    public static void main(String[] args)
    {
        // Initializing the first array
        int a[] = { 10, 30, 12 };
        // Initializing the second array
        int b[] = { 10, 30, 12 };

        // store the result
        boolean result = true;

        // Check if length of the two arrays are equal or
        // not
        if (a.length == b.length) {

            // Loop to check elements of arrays one by one
            for (int i = 0; i < a.length; i = i + 1) {

                // To check if any element is different
                if (a[i] != b[i]) {

                    // If any element is different then it
                    // will assign false into boolean
                    // variable
                    result = false;
                }
            }
        }
        else {

            // If the length of two arrays is
            // different then it will assign
            // false into boolean variable
            result = false;
        }

        // After completion to check whether
        // result is true of false
        if (result == true) {

            // Print the result
            System.out.println("Arrays are equal");
        }
        else {

            // Print the result
            System.out.println("Arrays are not equal");
        }
    }
}
```

**Output**

```
Arrays are equal
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to check if the arrays are equal

public class checkArraysEqual {

    public static void main(String[] args)
    {
        // Initializing the first array
        int a[] = { 10, 30, 12 };
        // Initializing the second array
        int b[] = { 45, 50, 55, 60, 65 };

        // stores the result
        boolean result = true;

        // Check if length of the two arrays are equal or
        // not
        if (a.length == b.length) {

            // Loop to check elements of arrays one by one
            for (int i = 0; i < a.length; i = i + 1) {

                // To check if any element is different
                if (a[i] != b[i]) {

                    // If any element is different then it
                    // will assign false into boolean
                    // variable
                    result = false;
                }
            }
        }
        else {

            // If the length of two arrays is different then
            // it will assign false into boolean variable
            result = false;
        }

        // After completion to check whether result is true
        // of false
        if (result == true) {

            // Print the result
            System.out.println("Arrays are equal");
        }
        else {
            // Print the result
            System.out.println("Arrays are not equal");
        }
    }
}
```

**Output**

```
Arrays are not equal
```

**时间复杂度:**O(n)
T5】辅助空间: O(1)