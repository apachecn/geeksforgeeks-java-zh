# 如何在 Java 中从 LinkedHashSet 获取随机元素？

> 原文:[https://www . geesforgeks . org/how-to-random-elements-from-link edhashset-in-Java/](https://www.geeksforgeeks.org/how-to-get-random-elements-from-linkedhashset-in-java/)

[**LinkedHashSet**](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 用于维护插入顺序，为了从 LinkedHashSet 生成随机元素，我们将使用 **Random Class** 来生成介于 0 和 LinkedHashSet 大小之间的随机数。这个随机数将作为 LinkedHashSet 的索引。

**我们可以通过三种方式得到一个随机元素:**

1.  Use for loop by traversing LinkedHashSet and get random elements.
2.  The LinkedHashSet is stored in the array, and the elements existing at the random number index are obtained.
3.  The LinkedHashSet is stored in ArrayList, and the element is obtained at the random number position.

**示例 1:**

*   We will generate random elements from 0 to LinkedHashSet size.
*   Then we will iterate through the LinkedHashSet for the loop, check whether the I <sup>th</sup> index is equal to the random number, and then print the element.

## Java

```java
// Java program to get the randome element
// from LinkedHashSet

import java.util.LinkedHashSet;
import java.util.Random;

class GFG {
    public static void main(String[] args)
    {
        LinkedHashSet<String> cset = new LinkedHashSet<>();

        // Adding elements to LinkedHashSet
        cset.add("Paneer Butter Masala");
        cset.add("Paneer Lababdar");
        cset.add("Kadai Paneer Gravy");
        cset.add("Malai Kofta Curry");
        cset.add("Palak Paneer");
        cset.add("Mughlai Shahi Paneer");
        cset.add("Restaurant Style Chilli Paneer");
        cset.add("Restaurant Style Matar Paneer");
        cset.add("Paneer Tikka Masala");
        cset.add("Paneer Makhani");
        cset.add("Achari Paneer Gravy");

        // This will generate a random number
        // between 0 and LinkedHashSet size()
        Random random = new Random();
        int randomNumber = random.nextInt(cset.size());

        // maintaining the index
        int count = 0;
        for (String s : cset) {

            // when ever our index counter variable "count"
            // will be equal to the random number it will
            // print the element at that position in the
            // LinkedHashSet and after printing we will break
            // the loop
            if (count == randomNumber) {
                System.out.println(s);
                break;
            }
            count++;
        }
    }
}
```

**输出**

```java
Paneer Butter Masala
```