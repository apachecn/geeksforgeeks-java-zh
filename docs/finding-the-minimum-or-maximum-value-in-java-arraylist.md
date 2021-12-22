# 在 Java 数组列表中寻找最小值或最大值

> 原文:[https://www . geesforgeks . org/find-Java 中的最小值或最大值-arraylist/](https://www.geeksforgeeks.org/finding-the-minimum-or-maximum-value-in-java-arraylist/)

最小值为最小值，最大值为最大值。这里的主要任务是从[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)中找到最小值和最大值。考虑一个数组列表的例子，我们需要找到最大和最小的元素。

**例:**

```java
Input List: {10, 20, 8, 32, 21, 31};

Output: 

Maximum is: 32

Minimum is: 8
```

**方法 1:通过迭代数组列表值**

1.  First, we need to initialize the array list value.
2.  Then use the **size ()** function to find the length of the array list.
3.  After that, the first element of the array list will be stored in the variables min and max.
4.  Then use the for loop to iterate through the array list elements one by one to find the minimum and maximum values from the array list.

## Java

```java
// Java program to find the minimum and
// maximum value of the ArrayList

import java.util.*;
public class Max {
    public static void main(String args[])
    {

        // initializing the ArrayList elements
        ArrayList<Integer> arr = new ArrayList<>();
        arr.add(10);
        arr.add(20);
        arr.add(8);
        arr.add(32);
        arr.add(21);
        arr.add(31);

        int min = arr.get(0);
        int max = arr.get(0);

        // store the length of the ArrayList in variable n
        int n = arr.size();

        // loop to find minimum from ArrayList
        for (int i = 1; i < n; i++) {
            if (arr.get(i) < min) {
                min = arr.get(i);
            }
        }

        // loop to find maximum from ArrayList
        for (int i = 1; i < n; i++) {
            if (arr.get(i) > max) {
                max = arr.get(i);
            }
        }

        // The result will be printed
        System.out.println("Maximum is : " + max);
        System.out.println("Minimum is : " + min);
    }
}
```

**输出**

```java
Maximum is : 32
Minimum is : 8
```