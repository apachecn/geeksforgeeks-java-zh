# 如何防止在 Java 数组列表中添加重复元素？

> 原文:[https://www . geesforgeks . org/如何防止向 java 数组列表中添加重复元素/](https://www.geeksforgeeks.org/how-to-prevent-the-addition-of-duplicate-elements-to-the-java-arraylist/)

有没有想过如何让一个[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)独一无二？在本文中，我们将看到如何防止将**副本**添加到我们的数组列表中。如果一个数组列表有三个重复的元素，但是在最后，只有唯一的元素被放入数组列表，并且重复被忽略，可以使用下面讨论的各种方法来完成。

**示例:**

```
Input : [1, 1, 2, 2, 3, 3, 4, 5, 8]
Output: [1, 2, 3, 4, 5, 8]

Input : [1, 1, 1, 1, 1, 1, 1, 1, 1]
Output: [1]
```

**进场 1: [含()法](https://www.geeksforgeeks.org/arraylist-contains-java/)T3】**

1.  逐个添加元素。
2.  使用 contains 方法检查它们是否存在。
3.  如果当前元素返回 true，则忽略它。
4.  否则添加元素。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to prevent the addition
// of duplicate elements to an ArrayList.

// Importing the ArrayList class
import java.util.ArrayList;

class GFG {
    public static void main(String[] args)
    {

        // Input
        int array[] = { 1, 1, 2, 2, 3, 3, 4, 5, 8 };

        // Creating an empty ArrayList
        ArrayList<Integer> ans = new ArrayList<>();

        for (int i : array) {

            // Checking if the element is already present or
            // not
            if (!ans.contains(i)) {
                // Adding the element to the ArrayList if it
                // is not present
                ans.add(i);
            }
        }

        // Printing the elements of the ArrayList
        for (int i : ans) {
            System.out.print(i + " ");
        }
    }
}
```

**Output**

```
1 2 3 4 5 8
```

**时间复杂度:** O( ![  ](img/0faf5aa5dcca41fbedb26b2cadf9f952.png "Rendered by QuickLaTeX.com") N <sup>2</sup> ，因为包含法在最坏的情况下可以遍历**整个数组**。

**空间复杂度:** O(1)，因为没有使用额外的空间。

**途径 2: HashSet**

1.  逐个添加元素。
2.  使用 [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 检查它们的存在。
3.  如果当前元素返回 true，则忽略它。
4.  否则添加元素。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to prevent the addition
// of duplicate elements to an ArrayList.

// Importing the ArrayList class
import java.util.ArrayList;

// Importing the HashSet class
import java.util.HashSet;

class GFG {
    public static void main(String[] args)
    {

        // Input
        int array[] = { 1, 1, 1, 1, 1, 1, 1, 1 };

        // Creating an empty ArrayList
        ArrayList<Integer> ans = new ArrayList<>();

        // Creating an empty HashSet
        HashSet<Integer> set = new HashSet<>();

        for (int i : array) {

            // Checking if the element is already present or
            // not
            if (!set.contains(i)) {
                // Adding the element to the ArrayList if it
                // is not present
                ans.add(i);
                // Adding the element to the HashSet if it
                // is not present
                set.add(i);
            }
        }

        // Printing the elements of the ArrayList
        for (int i : ans) {
            System.out.print(i + " ");
        }
    }
}
```

**Output**

```
1
```

**时间复杂度:** O(n)

**空间复杂度:**O(n)**T3】作为 HashSet 用来存储遍历的元素。**