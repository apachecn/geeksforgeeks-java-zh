# Java 程序求数组元素的和

> 原文:[https://www . geesforgeks . org/Java-程序查找数组元素的和/](https://www.geeksforgeeks.org/java-program-to-find-sum-of-array-elements/)

给定一个整数数组。写一个 Java 程序来求数组元素的和。

**例:**

```java
Input : arr[] = {1, 2, 3}
Output : 6
1 + 2 + 3 = 6

Input : arr[] = {15, 12, 13, 10}
Output : 50
15 + 12 + 13 + 10 = 50
```

一个**数组**是一个包含**一组元素** **的数据结构。**通常这些元素都是相同的数据类型，例如整数或字符串。数组通常在计算机程序中用于组织数据，以便可以快速对一组相关的值进行排序或搜索。数组中的所有项目都存储在连续的存储位置中。

**数组元素:**数组中的每一项都是一个**元素**。数组中的所有元素必须是相同的类型。

#### 算法

1.  初始化数组 arr 和变量 sum。
2.  设置 sum=0 的值。
3.  从索引 0 到数组长度-1 开始一个 for 循环。
4.  在每次迭代中，执行 sum = sum + arr[i]。
5.  循环结束后，打印总和的值。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to find sum of elements in a given array
class Test {
    static int arr[] = { 12, 3, 4, 15 };

    // method for sum of elements in an array
    static int sum()
    {
        int sum = 0; // initialize sum
        int i;

        // Iterate through all elements and add them to sum
        for (i = 0; i < arr.length; i++)
            sum += arr[i];

        return sum;
    }

    // Driver method
    public static void main(String[] args)
    {
        System.out.println("Sum of given array is "
                           + sum());
    }
}
```

**Output**

```java
Sum of given array is 34
```