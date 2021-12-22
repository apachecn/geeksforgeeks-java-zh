# 两个列表对应元素相乘的 Java 程序

> 原文:[https://www . geeksforgeeks . org/Java-程序对两个列表的对应元素进行乘法运算/](https://www.geeksforgeeks.org/java-program-to-multiply-corresponding-elements-of-two-lists/)

将两个对应的元素相乘意味着将一个列表的第一个元素与另一个列表的第一个元素相乘，然后将第二个元素相乘，直到列表的大小。给定两个元素列表，我们必须将两个列表的对应元素相乘。

**这可以通过两种方式完成:**

1.  Use extra space
2.  No extra space is used.

**方法 1:(使用额外空间)–**可以将对应的元素相乘，使用内置函数**将它们存储在字符串中，最后打印字符串。**

## **Java**

```java
// Java program to multiply the corresponding elements of
// two list. using string in-built function

import java.util.Arrays;

class GFG {
    public static void main(String[] args)
    {
        int a1[] = { 2, 5, -2, 10 };
        int a2[] = { 3, -5, 7, 1 };

        String result = "";

        for (int i = 0; i < a1.length; i++) {
            // converting integer to string and
            // multiplying corresponding element
            result += Integer.toString(a1[i] * a2[i]) + " ";
        }

        System.out.println(result);
    }
}
```

****输出****

```java
6 -25 -14 10
```