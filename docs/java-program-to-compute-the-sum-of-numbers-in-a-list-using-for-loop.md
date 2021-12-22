# 使用 For 循环计算列表中数字总和的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到计算列表中数字的总和-使用 for 循环/](https://www.geeksforgeeks.org/java-program-to-compute-the-sum-of-numbers-in-a-list-using-for-loop/)

给定一个数字列表，编写一个 Java 程序，找出用于循环的[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)中所有元素的总和。为了执行给定的任务，完整的列表遍历是必要的，这使得整个程序的时间复杂度为 O(n)，其中 n 是列表的长度。

**例:**

```
Input : List = [1, 2, 3]
Output: Sum = 6

Input : List = [5, 1, 2, 3]
Output: Sum = 11
```

**方法 1:**

1.  Create and variables of integer data type.
2.  Initialize and with 0.
3.  Use the for loop to start the iteration list.
4.  During the iteration, add each element with and variables.
5.  After the loop is executed, the sum is printed.

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Compute the Sum of
// Numbers in a List Using For-Loop
import java.util.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        List<Integer> list = new ArrayList<>();
        list.add(5);
        list.add(6);
        list.add(7);
        list.add(10);
        list.add(9);
        int sum = 0;
        for (int i = 0; i < list.size(); i++)
            sum += list.get(i);

        System.out.println("sum-> " + sum);
    }
}
```

**Output**

```
sum-> 37
```

**时间复杂度:** O(n)

**方法 2:**

1.  Create and variables of integer data type.
2.  Initialize and with 0.
3.  Use the enhanced for loop to start the iteration list.
4.  During the iteration, add each element with and variables.
5.  After the loop is executed, the sum is printed.

下面是上述方法的实现:

T3】JavaT5

```
// Java Program to Compute the Sum of
// Numbers in a List Using Enhanced For-Loop
import java.util.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        List<Integer> list = new ArrayList<>();
        list.add(5);
        list.add(6);
        list.add(7);
        list.add(10);
        list.add(9);
        int sum = 0;
        for (Integer i : list)
            sum += i;

        System.out.println("sum-> " + sum);
    }
}
```

T6T8**输出**T1

**时间复杂度:** O(n)