# 不使用任何第三变量交换两个字符串的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到交换-两个字符串-不使用任何第三个变量/](https://www.geeksforgeeks.org/java-program-to-swap-two-strings-without-using-any-third-variable/)

给定两个字符串变量 a 和 b，您的任务是编写一个 Java 程序来交换这些变量，而不使用任何临时变量或第三个变量。允许使用库方法。

**示例:**

```java
Input: a = "Hello"
       b = "World"

Output:
Strings before swap: a = Hello and b = World
Strings after swap: a = World and b = Hello
```

**方法:**为了在不使用任何临时变量或第三个变量的情况下交换两个字符串变量，思路是使用字符串串联和 substring()方法来执行此操作。substring()方法有两种形式，如下所示:

*   **substring(int beginindex):**此函数将返回调用字符串的子字符串，从作为参数传递给此函数的索引开始，直到调用字符串中的最后一个字符。
*   **substring(int beginindex，** **int endindex):** 此函数将返回调用字符串的 substring，从 beginindex(包含)开始，到 endindex(不包含)结束，作为参数传递给此函数。

**算法:**

```java
1) Append second string to first string and 
   store in first string:
   a = a + b

2) call the method substring(int beginindex, int endindex)
   by passing beginindex as 0 and endindex as,
      a.length() - b.length():
   b = substring(0,a.length()-b.length());

3) call the method substring(int beginindex) by passing 
   b.length() as argument to store the value of initial 
   b string in a
   a = substring(b.length());
```

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to swap two strings without using a temporary
// variable.
import java.util.*;

class Swap
{    
    public static void main(String args[])
    {
        // Declare two strings
        String a = "Hello";
        String b = "World";

        // Print String before swapping
        System.out.println("Strings before swap: a = " + 
                                       a + " and b = "+b);

        // append 2nd string to 1st
        a = a + b;

        // store initial string a in string b
        b = a.substring(0,a.length()-b.length());

        // store initial string b in string a
        a = a.substring(b.length());

        // print String after swapping
        System.out.println("Strings after swap: a = " + 
                                     a + " and b = " + b);        
    }    
}
```

**Output**

```java
Strings before swap: a = Hello and b = World
Strings after swap: a = World and b = Hello
```

本文由 [**哈什·阿加瓦尔**](https://www.facebook.com/harsh.agarwal.16752) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。