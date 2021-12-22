# 等于()和深度等于()在 Java 中比较两个数组的方法

> 原文:[https://www . geesforgeks . org/equals-and-deep equals-方法比较 java 中的两个数组/](https://www.geeksforgeeks.org/equals-and-deepequals-method-to-compare-two-arrays-in-java/)

数组。 **等于()** 如果一个数组包含另一个数组，则方法不递归比较。 **deepEquals()** 如果一个数组包含另一个数组，方法递归比较。

[**Arrays.equals(Object[]，Object[])**](https://www.geeksforgeeks.org/java-util-arrays-equals-java-examples/)

**语法:**

```
public static boolean equals(int[] a, int[] a2)
```

**参数:**

*   a–测试一个数组的相等性
*   a2–要测试相等性的另一个阵列

**如果两个数组相等，则返回:** true

*   如果数组彼此相等，则返回真。
*   如果两个数组包含相同数量的元素，并且每个索引中包含相同的元素。
*   此外，如果两个数组都为空，则认为它们相等。
*   *Arrays.equals()* 如果一个数组包含另一个数组，则方法不会递归比较。
*   在所有其他情况下，它返回 False。

[**array . deep equals(Object[]，Object[])**](https://www.geeksforgeeks.org/java-util-arrays-deepequals-java/)

**语法:**

```
public static boolean deepEquals(Object[] o1, Object[] o2)

o1 = First Array to test for Equality
o2 = Second Array to test for Equality
```

*   如果两个数组相等，则返回真。
*   如果两个数组包含相同数量的元素并且每个索引中的元素相同。
*   此外，两个数组都为空，则认为它们相等。
*   此外，如果嵌套元素再次是数组，那么嵌套数组的元素也以迭代的方式进行比较。
*   *Arrays.deepEquals()* 方法递归比较一个数组是否包含另一个数组。

**主要区别:**

如果在任何数组中，一个项目本身就是另一个数组，那么对 **equals()** 的调用将转到默认的 java.lang.Object equals()，它将比较两个对象的引用，并且不执行深度比较，如果是嵌套数组，逻辑比较将失败。

另一方面**arrays . deepequals()***方法执行大量检查，调用 *Arrays.equals()* 进行非数组比较，递归调用 *Arrays.deepEquals()* 进行数组类型比较，这样就可以在 Java 中对嵌套数组进行逻辑比较。*

***注意:**总是建议用 *Arrays.equals()* 比较非嵌套数组和 *Arrays.deepEquals()* 比较嵌套数组，因为 *Array.equals()* 在非嵌套数组的情况下比 *Arrays.deepEquals()* 快。*

***Java 中 equals()的说明:***

## *Java 语言(一种计算机语言，尤用于创建网站)*

```
*// Java program to compare two arrays
// using .equals() method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        int[] A = { 1, 2, 3, 4, 5 };
        int[] B = { 1, 2, 3, 4, 5 };
        int[] C = { 2, 1, 4, 3, 5 };

        // Comparing two arrays A and B using .equals()
        if (Arrays.equals(A,B))
            System.out.println(
                "Array A and Array B is equal");
        else
            System.out.println(
                "Array A and Array B is not equal");

        if (Arrays.equals(A, C))
            System.out.println(
                "Array A and Array C is equal");
        else
            System.out.println(
                "Array A and Array C is not equal");
    }
}*
```

***Output**

```
Array A and Array B is equal
Array A and Array C is not equal
```* 

*下面是 java 中 deepEquals()的**图解:-***

## *Java 语言(一种计算机语言，尤用于创建网站)*

```
*// Java program to compare two arrays
// using .deepEquals() method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        int[][] A
            = { { 1, 2, 3 }, { 3, 4, 5 }, { 6, 7, 8 } };
        int[][] B
            = { { 1, 2, 3 }, { 3, 4, 5 }, { 6, 7, 8 } };
        int[][] C
            = { { 3, 4, 5 }, { 4, 5, 6 }, { 7, 2, 4 } };

        // Comparing A and B arrays using .deepEquals() method
        if (Arrays.deepEquals(A, B))
            System.out.println(
                "Array A and Array B is equal");
        else
            System.out.println(
                "Array A and Array B is not equal");

        if (Arrays.deepEquals(A, C))
            System.out.println(
                "Array A and Array C is equal");
        else
            System.out.println(
                "Array A and Array C is not equal");
    }
}*
```

***Output**

```
Array A and Array B is equal
Array A and Array C is not equal
```*