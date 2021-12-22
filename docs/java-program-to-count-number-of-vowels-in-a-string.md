# 计算字符串中元音数量的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序对字符串中元音的计数数/](https://www.geeksforgeeks.org/java-program-to-count-number-of-vowels-in-a-string/)

在 java 中，字符串是一个字符序列，char 是用于存储变量的一个数字。该字符在 java 中使用 2 个字节。在 java 中，BufferedReader 和 InputStreamReader 用于读取用户从键盘给出的输入。然后 readLine()用于读取一行。java 中的 java.io 包通过数据流、序列化和文件系统提供输入和输出。

**我们可以通过两种方式统计一个字符串中的元音:**

1.  重复的
2.  递归的

**示例:**

```java
Input: GeeksForGeeks
Output: Total no of vowels in string are: 5

Input: ChETaN
Output: Total no of vowels in string are: 2
```

**方法 1:迭代**

**进场:**

*   我们将在 for 循环中遍历字符串的字符，从索引 0 开始，直到 size-1。
*   检查每个字符是否是元音，并增加计数变量。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Count Number of Vowels
// in a String in a iterative way

import java.io.*;

public class vowel {
    public static void main(String[] args)
        throws IOException
    {
        String str = "GeeksForGeeks";

            str = str.toLowerCase();

        // toCharArray() is used to convert 
        // string to char array
        char[] chars = str.toCharArray();

        int count = 0;

        for (int i = 0; i < str.length(); i++)
        {
            // check if char[i] is vowel
            if (str.charAt(i) == 'a' || str.charAt(i) == 'e'
                || str.charAt(i) == 'i'
                || str.charAt(i) == 'o'
                || str.charAt(i) == 'u')
            {
                // count increments if there is vowel in
                // char[i]
                count++;
            }
        }

        // display total count of vowels in string
        System.out.println("Total no of vowels in string are: " + count);
    }
}
```

**Output**

```java
Total no of vowels in string are: 5

```

**方法二:递归**

**进场:**

*   如果字符串长度为 1，则检查基本条件，如果是元音，则简单地检查单个字符，然后返回 1，否则返回 0。
*   为了将整个字符串分成子字符串以递归方式返回答案，我们将从第一个字符到第二个最后一个字符开始获取该字符串的答案。
*   最后返回上面的答案加上检查最后一个字符的答案(1 表示是元音，0 表示不是)

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Count Number of Vowels
// in a String in a recursive way

import java.io.*;

class GFG {

    // isVowel() function returns 1 if the
    // character is a vowel and 0 if it is not
    static int isVowel(char chars)
    {
        if (chars == 'a' || chars == 'e' || chars == 'i'
            || chars == 'o' || chars == 'u') {
            return 1;
        }
        else {
            return 0;
        }
    }

    // recursive function to return the number
    // of characters in a string
    static int vowelno(String str, int l)
    {
        if (l == 1) {
            return isVowel(str.charAt(l - 1));
        }

        return vowelno(str, l - 1)
            + isVowel(str.charAt(l - 1));
    }

    public static void main(String[] args)
        throws IOException
    {
        String str = "BufferedOutput";

        str = str.toLowerCase();

        System.out.println(
            "Total number of vowels in string are:");

        System.out.println(vowelno(str, str.length()));
    }
}
```

**Output**

```java
Total number of vowels in string are:
6

```