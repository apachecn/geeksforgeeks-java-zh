# Java 程序检查回文(使用库方法)

> 原文:[https://www . geesforgeks . org/Java-程序检查-回文-使用库-方法/](https://www.geeksforgeeks.org/java-program-to-check-palindrome-using-library-methods/)

给定一个字符串，编写一个 Java 函数来检查它是否是回文。如果字符串的反义词与字符串相同，则称字符串为回文。比如“abba”是回文，但“abbc”不是回文。这里的问题是用字符串反函数解决的。

示例:

```java
Input : malayalam
Output : Yes

Input : GeeksforGeeks
Output : No

```

```java
// Java program to illustrate checking of a string
// if its palindrome or not using reverse function
class Palindrome
{
  public static void checkPalindrome(String s)
  {
    // reverse the given String
    String reverse = new StringBuffer(s).reverse().toString();

    // check whether the string is palindrome or not
    if (s.equals(reverse))
      System.out.println("Yes");

    else
      System.out.println("No");
  }

  public static void main (String[] args)
               throws java.lang.Exception
  {
    checkPalindrome("malayalam");
    checkPalindrome("GeeksforGeeks");
  }
}
```

输出:

```java
Yes
No

```

**相关文章:**
[C 程序检查给定字符串是否回文](https://www.geeksforgeeks.org/c-program-check-given-string-palindrome/)

本文由 **Bhargav Sai Gajula** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。