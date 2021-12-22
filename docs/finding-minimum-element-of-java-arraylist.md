# 寻找 Java 数组列表的最小元素

> 原文:[https://www . geesforgeks . org/find-minimum-of-Java-ArrayList/](https://www.geeksforgeeks.org/finding-minimum-element-of-java-arraylist/)

要在[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/) ( 这个类在[T5】Java . util](https://www.geeksforgeeks.org/java-util-package-java/)包中找到)中找到最小元素，需要完整遍历数组列表。数组列表类中有一个内置函数，用来寻找数组列表中的最小元素，即时间复杂度为 O(N)，其中 N 是数组列表的大小，下面我们来讨论这两种方法。

**例**

```java
Input : ArrayList = {2, 9, 1, 3, 4}
Output: Min = 1

Input : ArrayList = {6, 7, 2, 8}
Output: Min = 2
```

**方法 1:**

1.  在变量上创建并用数组列表的第一个元素初始化它。
2.  开始遍历数组列表。
3.  如果当前元素小于变量，则用数组列表中的当前元素更新变量。
4.  最后，打印该变量。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Finding Minimum Element of Java ArrayList
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

        int minimum = myList.get(0);
        for (int i = 1; i < myList.size(); i++) {
            if (minimum > myList.get(i))
                minimum = myList.get(i);
        }
        System.out.println("Minimum element in ArrayList = "
                           + minimum);
    }
}
```

**Output**

```java
Minimum element in ArrayList = 3
```

**方法 2:**

java 集合类的 min '方法可以用来查找 ArrayList。' min '方法根据元素的自然顺序返回集合的最小元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Finding Minimum Element of Java ArrayList
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

        // 'min' method is used to find the minimum element
        // from Collections Class
        System.out.println("Minimum Element in ArrayList = "
                           + Collections.min(myList));
    }
}
```

**Output**

```java
Minimum Element in ArrayList = 3
```