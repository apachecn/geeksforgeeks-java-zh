# 如何从 Java HashSet 中获取随机元素？

> 原文:[https://www . geesforgeks . org/how-to-random-elements-from-Java-hashset/](https://www.geeksforgeeks.org/how-to-get-random-elements-from-java-hashset/)

与列表类不同的是， [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 类没有提供任何方法，通过这些方法我们可以使用元素的索引来获取元素。使用索引很难从中获取随机元素。

**我们需要从 HashSet 中获取随机元素，可以通过两种方式中的任意一种来完成:**

1.  通过将其转换为数组
2.  使用[迭代器](https://www.geeksforgeeks.org/iterators-in-java/)或 for 循环

**示例:**

```java
Input:

hs.add(11);
hs.add(24);
hs.add(34);
hs.add(43);
hs.add(55);
hs.add(66);
hs.add(72);
hs.add(80);
hs.add(99);

Output:

Random element: 99
```

**方法一:通过转换成数组。**

*   首先将 HashSet 转换成数组，然后从中访问随机元素。
*   然后我们将创建一个对象 [**【随机】**类](https://www.geeksforgeeks.org/java-util-random-class-java/)并将调用该类的 **nextInt()** 方法，该方法将为我们提供任何小于或等于 HashSet 大小的随机数。
*   然后使用一个数组，我们将简单地打印索引处的元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to get random elements from HashSet
// using an array

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // creating the HashSet
        Set<Integer> hs = new HashSet<Integer>();

        hs.add(11);
        hs.add(24);
        hs.add(34);
        hs.add(43);
        hs.add(55);
        hs.add(66);
        hs.add(72);
        hs.add(80);
        hs.add(99);

        // convert HashSet to an array
        Integer[] arrayNumbers = hs.toArray(new Integer[hs.size()]);

        // generate a random number
        Random rndm = new Random();

        // this will generate a random number between 0 and
        // HashSet.size - 1
        int rndmNumber = rndm.nextInt(hs.size());

        // get the element at random number index
        System.out.println("Random element: "
                           + arrayNumbers[rndmNumber]);
    }
}
```

**Output**

```java
Random element: 11
```

**方法 2:使用迭代器或 for 循环**

*   为了从 HashSet 对象中获取随机元素，我们需要生成一个介于 0(包括 0)和 HashSet 大小(不包括 0)之间的随机数。
*   然后遍历集合，直到我们到达位于随机数位置的元素，如下所示。
*   在这种方法中，我们将使用迭代器在随机索引处获取元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to get random elements from HashSet
// using an Iterator

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        Set<Integer> hs = new HashSet<Integer>();

        hs.add(11);
        hs.add(24);
        hs.add(34);
        hs.add(43);
        hs.add(55);
        hs.add(66);
        hs.add(72);
        hs.add(80);
        hs.add(99);

        System.out.println("Random element: "
                           + getRandomElement(hs));
    }

    private static <E>
        E getRandomElement(Set<? extends E> set)
    {

        Random random = new Random();

        // Generate a random number using nextInt
        // method of the Random class.
        int randomNumber = random.nextInt(set.size());

        Iterator<? extends E> iterator = set.iterator();

        int currentIndex = 0;
        E randomElement = null;

        // iterate the HashSet
        while (iterator.hasNext()) {

            randomElement = iterator.next();

            // if current index is equal to random number
            if (currentIndex == randomNumber)
                return randomElement;

            // increase the current index
            currentIndex++;
        }

        return randomElement;
    }
}
```

**Output**

```java
Random element: 99
```