# 寻找 Java 数组列表的最大元素

> 原文:[https://www . geesforgeks . org/finding-max-element-of-Java-ArrayList/](https://www.geeksforgeeks.org/finding-maximum-element-of-java-arraylist/)

为了找到[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)中的最大元素，需要完整遍历数组列表。ArrayList 类中有一个内置函数，用来寻找 ArrayList 中的最大元素，即时间复杂度为 O(N)，其中 N 是 ArrayList 的大小，我们来讨论这两种方法。

**示例:**

```
Input : ArrayList = {2, 9, 1, 3, 4}
Output: Max = 9

Input : ArrayList = {6, 7, 2, 1}
Output: Max = 7
```

**方法 1:**

1.  在变量上创建并用数组列表的第一个元素初始化它。
2.  开始遍历数组列表。
3.  如果当前元素大于变量，则用数组列表中的当前元素更新变量。
4.  最后，打印该变量。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Finding Maximum Element of Java ArrayList
import java.util.ArrayList;
import java.util.Collections;

class MinElementInArrayList {

    public static void main(String[] args)
    {
        // ArrayList of Numbers
        ArrayList<Integer> myList
            = new ArrayList<Integer>();

        // adding elements to Java ArrayList
        myList.add(16);
        myList.add(26);
        myList.add(3);
        myList.add(52);
        myList.add(70);
        myList.add(12);

        int maximum = myList.get(0);
        for (int i = 1; i < myList.size(); i++) {
            if (maximum < myList.get(i))
                maximum = myList.get(i);
        }
        System.out.println("Maximum Element in ArrayList = "
                           + maximum);
    }
}
```

**Output**

```
Maximum Element in ArrayList = 70

```

**方法 2:**

Java 集合类的 **max** 方法可以用来查找 ArrayList。 **max** 方法根据元素的自然顺序返回集合中的最大元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Finding Maximum Element of Java ArrayList
import java.util.ArrayList;
import java.util.Collections;

class MinElementInArrayList {

    public static void main(String[] args)
    {

        // ArrayList of Numbers
        ArrayList<Integer> myList
            = new ArrayList<Integer>();

        // adding elements to Java ArrayList
        myList.add(16);
        myList.add(26);
        myList.add(3);
        myList.add(52);
        myList.add(70);
        myList.add(12);

        // 'min' method is used to find the
        // minimum elementfrom Collections Class
        System.out.println("Maximum Element in ArrayList = "
                           + Collections.max(myList));
    }
}
```

**Output**

```
Maximum Element in ArrayList = 70
```