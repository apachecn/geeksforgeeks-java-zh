# 打印奇数位置数组元素的 Java 程序

> 原文:[https://www . geeksforgeeks . org/Java-program-to-print-the-elements-of-a-array-present-on-odd-position/](https://www.geeksforgeeks.org/java-program-to-print-the-elements-of-an-array-present-on-odd-position/)

一个数组存储相同类型的****的数据集合。它是相同类型元素的固定大小的顺序集合。在数组中，如果有“N”个元素，数组迭代从 0 开始，以“N-1”结束。****

**数组中的奇数位置是索引为偶数的位置，反之亦然。**

****示例:****

```java
Input  : arr[] = { 10,20,30,40,50 }
Output : 10 30 50

Input  : arr1[] = { -5,0,2,5,76,9 }
Output : -5 2 76
```

****我们将通过两种方式在奇数位置打印元素:****

1.  **通过检查位置是否为奇数，即**是否可被 2** 整除(因为索引从 0 开始)，然后打印元素。**
2.  **通过**维护一个标志指针**，该指针将被初始化为 1，并开始遍历数组。如果标志为 1，打印该元素并将标志更改为 0，否则如果标志为 0，将标志设置为 1。**

****方法 1:****

**通过检查位置是否为奇数，即**是否可被 2** 整除(因为索引从数组中的 0 开始)，然后打印元素。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to print the elements at odd positions

import java.util.*;

public class PrintOddElementsInArray {

    public static void main(String[] args)
    {
        // Initialized array
        int inputArray[] = new int[] { 100,  -500, 450, -200,
                          1000, -213, 750 };

        System.out.println("Existing array elements ..");

        for (int i = 0; i < inputArray.length; i++) {

            System.out.println(inputArray[i]);
        }

        System.out.println(
            "Array elements at odd position..");

        // Though the logic looks like taking even position,
        // if 10,20,30,40,50 are elements we need to get
        // 10,30,50\. So followed the logic like this
        for (int i = 0; i < inputArray.length; i++) {

            if (i % 2 == 0) {

                System.out.println(inputArray[i]);
            }
        }
    }
}
```

****Output**

```java
Existing array elements ..
100
-500
450
-200
1000
-213
750
Array elements at odd position..
100
450
1000
750
```** 

*   ****时间复杂度:** O(n)**
*   ****空间复杂度:** O(1)**

****方法 2:****

**通过**维护一个标志指针**，该指针将被初始化为 1，并开始遍历数组。如果标志为 1，打印该元素并将标志更改为 0，否则如果标志为 0，将标志设置为 1。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to print the elements at odd positions

import java.util.*;

public class PrintOddElementsInArray {
    public static void main(String[] args)
    {
        // Initialized array
        int inputArray[] = new int[] { 100,  -500, 450, -200,
                          1000, -213, 750 };

        System.out.println("Existing array elements ..");

        for (int i = 0; i < inputArray.length; i++) {

            System.out.println(inputArray[i]);
        }

        System.out.println(
            "Array elements at odd position..");

        int flag = 1;

        for (int i = 0; i < inputArray.length; i++) {

            if (flag == 1) {
                System.out.print(inputArray[i] + " ");
                flag = 0;
            }

            else
                flag = 1;
        }
    }
}
```

****Output**

```java
Existing array elements ..
100
-500
450
-200
1000
-213
750
Array elements at odd position..
100 450 1000 750
```** 

*   ****时间复杂度:** O(n)**
*   ****空间复杂度:** O(1)**