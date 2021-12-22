# 从数组中移除重复元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-从数组中删除重复元素的程序/](https://www.geeksforgeeks.org/java-program-to-remove-duplicate-elements-from-the-array/)

[数组](https://www.geeksforgeeks.org/introduction-to-arrays/)是存储在连续存储位置的项目的集合。想法是将多个相同类型的项目存储在一起。为了简单起见，我们可以将数组想象成一排阶梯，每一级阶梯上都有一个值

给定一个数组，任务是从数组中移除重复的元素。

**例:**

```
Input  : a[] = {1, 1, 2, 2, 2}
Output : a[] = {1,2}
         new size = 2

Input  : a[] = {5,2,6,8,6,7,5,2,8}
Output : a[] = {2,5,6,7,8}
         new size = 5
```

**从数组中移除重复元素的方法:**

1.  使用额外空间
2.  恒定额外空间
3.  使用[设置](https://www.geeksforgeeks.org/set-in-java/)
4.  使用频率阵列
5.  使用[哈希表](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)

**方法 1:(使用额外空间)**

1.  Create a temporary array temp[] to store unique elements.
2.  Traverse the array and copy all unique elements of [] to temp[]. In addition, record unique elements. Let this count be j.
3.  Copy j elements from temp[] to a[].

**注:**该方法适用于数组排序时。

## Java

```
// Java Program to Remove Duplicate Elements
// From the Array using extra space

public class Main {

    public static int removeduplicates(int a[], int n)
    {
        if (n == 0 || n == 1) {
            return n;
        }

        // creating another array for only storing
        // the unique elements
        int[] temp = new int[n];
        int j = 0;

        for (int i = 0; i < n - 1; i++) {
            if (a[i] != a[i + 1]) {
                temp[j++] = a[i];
            }
        }

        temp[j++] = a[n - 1];

        // Changing the original array
        for (int i = 0; i < j; i++) {
            a[i] = temp[i];
        }

        return j;
    }
    public static void main(String[] args)
    {
        int a[] = { 1, 1, 2, 2, 2 };
        int n = a.length;

        n = removeduplicates(a, n);

        // Printing The array elements
        for (int i = 0; i < n; i++)
            System.out.print(a[i] + " ");
    }
}
```

**输出**

```
1 2
```

**时间复杂度** : O(n)

**空间复杂度:** O(n)

**方法二** : **(恒定额外空间)**

只需为同一数组维护一个单独的索引，就像方法 1 中为不同数组维护的索引一样。

## 爪哇

T0】输出

```
1 2 3 4 5 6
```