# Java 中的数组. deepToString()，示例

> 原文:[https://www . geeksforgeeks . org/arrays-deeptostring-in-Java-with-example/](https://www.geeksforgeeks.org/arrays-deeptostring-in-java-with-example/)

[Java . util . arrays . deeptostring(Object[])](https://docs.oracle.com/javase/7/docs/api/java/util/Arrays.html#deepToString(java.lang.Object[]))方法是一个 [java.util.Arrays 类](https://www.geeksforgeeks.org/array-class-in-java/)方法。

返回指定数组的“深层内容”的字符串表示形式。如果数组包含其他数组作为元素，则字符串表示包含它们的内容，依此类推。此方法设计用于将多维数组转换为字符串。简单的 toString()方法适用于简单数组，但不适用于多维数组。此方法是为将多维数组转换为字符串而设计的。

**语法:**

```
public static String deepToString(Object[] arr)

arr - An array whose string representation is needed

This function returns string representation of arr[].
It returns "null"   if the specified array is null.
```

**示例:**

```
Let us suppose that we are making a 2-D array of
3 rows and 3 column.
    2   3   4   
    5   6   7
    2   4   9

If use deepToString() method to print the 2-D array, 
we will get string representation as :-
[[2,3,4], [5,6,7], [2,4,9]]

```

**打印多维数组**

```
// A Java program to print 2D array using deepToString()
import java.util.Arrays;

public class GfG
{
    public static void main(String[] args)
    {
        // Create a 2D array
        int[][] mat = new int[2][2];
        mat[0][0] = 99;
        mat[0][1] = 151;
        mat[1][0] = 30;
        mat[1][1] = 5;

        // print 2D integer array using deepToString()
        System.out.println(Arrays.deepToString(mat));
    }
}
```

输出:

```
[[99, 151], [30, 5]]
```

**toString()vs deepToString()**
toString()对于一维数组很好用，但是对于多维数组就不行了。

```
// Java program to demonstrate that toString works if we 
// want to print single dimensional array, but doesn't work
// for multidimensional array.
import java.util.Arrays;
public class Deeptostring
{
    public static void main(String[] args)
    {
        // Trying to print array of strings using toString
        String[] strs = new String[] {"practice.geeksforgeeks.org",
                                      "quiz.geeksforgeeks.org"
                                     };
        System.out.println(Arrays.toString(strs));

        // Trying to print multidimensional array using
        // toString
        int[][] mat = new int[2][2];
        mat[0][0] = 99;
        mat[0][1] = 151;
        mat[1][0] = 30;
        mat[1][1] = 50;
        System.out.println(Arrays.toString(mat));
    }
}
```

输出:

```
[practice.geeksforgeeks.org, quiz.geeksforgeeks.org]
[[I@15db9742, [I@6d06d69c]

```

注意:我们可以使用一个循环来使用 deepToString()打印多维数组的内容。

**deepToString()适用于单维和多维度，但不适用于图元的一维数组**

```
// Java program to demonstrate that deepToString(strs))
// works for single dimensional arrays also, but doesn't
// work single dimensional array of primitive types.
import java.util.Arrays;
public class Deeptostring
{
    public static void main(String[] args)
    {
        String[] strs = new String[] {"practice.geeksforgeeks.org",
                                      "quiz.geeksforgeeks.org"
                                     };
        System.out.println(Arrays.deepToString(strs));

        Integer []  arr1 = {10, 20, 30, 40};
        System.out.println(Arrays.deepToString(arr1));

        /* Uncommenting below code would cause error as 
           deepToString() doesn't work for primitive types
        int []  arr2 = {10, 20, 30, 40};
        System.out.println(Arrays.deepToString(arr2));   */    
    }
}
```

输出:

```
[practice.geeksforgeeks.org, quiz.geeksforgeeks.org]
[10, 20, 30, 40]

```

**参考:** 

[https://docs . Oracle . com/javase/7/docs/API/Java/util/arrays . html # deepToString(Java . lang . object[])](https://docs.oracle.com/javase/7/docs/api/java/util/Arrays.html#deepToString(java.lang.Object[]))

本文由**莫希特·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
。