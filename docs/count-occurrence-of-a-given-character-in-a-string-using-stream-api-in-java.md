# 使用 Java 中的 Stream API 计算字符串中给定字符的出现次数

> 原文:[https://www . geesforgeks . org/count-使用 java 中的流 api 计算给定字符串中字符的出现次数/](https://www.geeksforgeeks.org/count-occurrence-of-a-given-character-in-a-string-using-stream-api-in-java/)

给定一个字符串和一个字符，任务是使用[流应用编程接口](https://www.geeksforgeeks.org/stream-in-java/)创建一个计算字符串中给定字符出现次数的函数。

**例:**

```java
Input: str = "geeksforgeeks", c = 'e'
Output: 4
'e' appears four times in str.

Input: str = "abccdefgaa", c = 'a' 
Output: 3
'a' appears three times in str.

```

**进场:**

*   将字符串转换为字符流
*   使用[过滤器()](https://www.geeksforgeeks.org/stream-filter-java-examples/)功能检查流中的字符是否是要计数的字符。
*   使用[计数()](https://www.geeksforgeeks.org/java-util-stream-collectors-counting-method-examples/)功能对匹配的字符进行计数

下面是上述方法的实现:

```java
// Java program to count occurrences
// of a character using Stream

import java.util.stream.*;

class GFG {

    // Method that returns the count of the given
    // character in the string
    public static long count(String s, char ch)
    {

        return s.chars()
            .filter(c -> c == ch)
            .count();
    }

    // Driver method
    public static void main(String args[])
    {
        String str = "geeksforgeeks";
        char c = 'e';
        System.out.println(count(str, c));
    }
}
```

**输出:**

```java
4

```

**相关文章:** [计算字符串中给定字符出现次数的程序](https://www.geeksforgeeks.org/program-count-occurrence-given-character-string/)