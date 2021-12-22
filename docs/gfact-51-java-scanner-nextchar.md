# Java 中的 Scanner 和 nextChar()

> 原文:[https://www . geesforgeks . org/gfact-51-Java-scanner-next char/](https://www.geeksforgeeks.org/gfact-51-java-scanner-nextchar/)

[Java 中的 Scanner 类](https://www.geeksforgeeks.org/scanner-class-in-java/)支持 nextInt()、nextLong()、nextDouble()等。但是没有 nextChar()(例子见[这个](https://www.geeksforgeeks.org/scanner-class-in-java/)

要读取一个字符，我们使用 **next()。charAt(0)** 。next()函数以字符串形式返回输入中的下一个标记/单词，charAt(0)函数返回该字符串中的第一个字符。

```
// Java program to read character using Scanner 
// class
import java.util.Scanner;
public class ScannerDemo1
{
    public static void main(String[] args)
    {
        // Declare the object and initialize with
        // predefined standard input object
        Scanner sc = new Scanner(System.in);

        // Character input
        char c = sc.next().charAt(0);

        // Print the read value
        System.out.println("c = "+c);
    }
}
```

输入:

```
g
```

输出:

```
c = g
```

本文由**比于什·古普塔**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论