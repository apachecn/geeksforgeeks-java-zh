# 对数组元素进行降序排序的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-按降序对数组元素进行排序/](https://www.geeksforgeeks.org/java-program-to-sort-the-array-elements-in-descending-order/)

给定数组按降序排序，即从大到小排列元素。

**例:**

```
Input :Array = {2, 6, 23, 98, 24, 35, 78}
Output:[98, 78, 35, 24, 23, 6, 2]

Input :Array = {1, 2, 3, 4, 5}
Output:[5, 4, 3, 2, 1]
```

排序是系统地排列项目的过程。sort()是 java.util.Arrays 中的一个内置函数，用于以优化的复杂度对元素数组进行排序。

### 方法

在 Java 中，有许多方法可以按降序对给定的数组进行排序。下面列出了其中的一些。

*   使用 Collections.reverseOrder()方法
*   使用排序和反转

### 1.使用[collections . reverseorder()](https://www.geeksforgeeks.org/collections-reverseorder-java-examples/)方法

通过传入数组和 Collections.reverseOrder()作为 Arrays.sort()的参数，可以按降序对数组元素进行排序。

> **<u>注意</u> :** 需要记住的一点是，当按降序排序时，Arrays.sort()不接受原始数据类型的数组。

**实现:**

T5】Java

```
// Java program to sort the elements in descending order
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // Initializing the array
        Integer array[] = { 1, 2, 3, 4, 5 };

        // Sorting the array in descending order
        Arrays.sort(array, Collections.reverseOrder());

        // Printing the elements
        System.out.println(Arrays.toString(array));
    }
}
```

**输出**

```
[5, 4, 3, 2, 1]
```

**时间复杂度:** O(N log N)

### 2.使用排序和反转

*   给定数组排序。
*   反转排序的数组。

下面是上述方法的实现:

T3】JavaT5

```
// Java program to sort the elements in descending order
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // Initializing the array
        int array[] = { 1, 2, 3, 4, 5, 6 };

        // Sorting the array in ascending order
        Arrays.sort(array);

        // Reversing the array
        reverse(array);

        // Printing the elements
        System.out.println(Arrays.toString(array));
    }

    public static void reverse(int[] array)
    {

        // Length of the array
        int n = array.length;

        // Swaping the first half elements with last half
        // elements
        for (int i = 0; i < n / 2; i++) {

            // Storing the first half elements temporarily
            int temp = array[i];

            // Assigning the first half to the last half
            array[i] = array[n - i - 1];

            // Assigning the last half to the first half
            array[n - i - 1] = temp;
        }
    }
}
```

T6T8**输出**T1

**时间复杂度:** O(N log N)