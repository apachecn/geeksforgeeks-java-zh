# 在 java 中查找数组列表的第一个和最后一个元素

> 原文:[https://www . geesforgeks . org/find-Java 中数组列表的第一个和最后一个元素/](https://www.geeksforgeeks.org/find-first-and-last-element-of-arraylist-in-java/)

**先决条件:**Java 中的[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)

给定一个数组列表，任务是获取 Java 中数组列表的第一个也是最后一个元素，

**示例:**

```
Input: ArrayList = [1, 2, 3, 4] 
Output: First = 1, Last = 4

Input: ArrayList = [12, 23, 34, 45, 57, 67, 89] 
Output: First = 12, Last = 89

```

**进场:**

1.  获取包含元素的数组列表。
2.  通过传递 index = 0，使用 get(index)方法获取 ArrayList 的第一个元素。
3.  通过传递 index = size–1，使用 get(index)方法获取数组列表的最后一个元素。

下面是上述方法的实现:

```
// Java code to find first and last element
// of ArrayList

import java.util.ArrayList;

public class GFG {

    // main method
    public static void main(String[] args)
    {

        // creating an Empty Integer ArrayList
        ArrayList<Integer> list = new ArrayList<Integer>(5);

        // using add() to initialize values
        list.add(1);
        list.add(2);
        list.add(3);
        list.add(4);

        // printing initial value ArrayList
        System.out.print("ArrayList: " + list);

        // find first element
        int first = list.get(0);

        // find last element
        int last = list.get(list.size() - 1);

        // print first and last element of ArrayList
        System.out.println("\nFirst : " + first
                           + ", Last : " + last);
    }
}
```

**Output:**

```
ArrayList: [1, 2, 3, 4]
First : 1, Last : 4

```