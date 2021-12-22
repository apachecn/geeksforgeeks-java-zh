# 如何在 Java 中将字符串转换为数组列表？

> 原文:[https://www . geesforgeks . org/如何在 java 中将字符串转换为数组列表/](https://www.geeksforgeeks.org/how-to-convert-a-string-to-arraylist-in-java/)

将字符串转换为[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)意味着字符串的每个字符都被添加为数组列表中的分隔符元素。

**例:**

```
Input: 0001
Output: 0
        0
        0
        1

Input: Geeks
Output: G
        e
        e
        k
        s
```

我们可以使用 [**split()方法**](https://www.geeksforgeeks.org/split-string-java-examples/) 和正则表达式在 Java 中轻松地将 String 转换为 ArrayList。

**参数:**

*   正则表达式——定界正则表达式
*   极限–最终阈值

**返回:**通过拆分给定字符串计算的字符串数组。

**抛出:**patternsyntaxception–如果提供的正则表达式语法无效。

**方法:**

*   Use Java *split ()* method to split strings and store substrings into arrays.
*   Create an array list, and use the *arrays.aslist ()* method to pass the substring reference to it.

## Java

```
// Java program to convert String to ArrayList

import java.util.ArrayList;
import java.util.Arrays;

public class Main {

    public static void main(String[] args)
    {

        String str = "Geeks";

        // split string by no space
        String[] strSplit = str.split("");

        // Now convert string into ArrayList
        ArrayList<String> strList = new ArrayList<String>(
            Arrays.asList(strSplit));

        // Now print the ArrayList
        for (String s : strList)
            System.out.println(s);
    }
}
```

**输出**

```
G
e
e
k
s
```