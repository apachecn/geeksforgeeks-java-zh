# 在 Java 中检查 URL 是否有效

> 原文:[https://www . geesforgeks . org/check-if-URL-is-valid-or-not-in-Java/](https://www.geeksforgeeks.org/check-if-url-is-valid-or-not-in-java/)

给定一个字符串形式的网址，我们需要找出给定的网址是否有效。

```
Input : str = "https://www.geeksforgeeks.org/"
Output : Yes

Input : str = "https:// www.geeksforgeeks.org/"
Output : No
Note that there is a space after https://

```

**使用 java.net.url**
我们可以使用 [java.net.url](https://www.geeksforgeeks.org/url-class-java-examples/) 类来验证一个 url。想法是从指定的字符串表示创建一个 URL 对象。如果我们在创建对象时没有得到异常，我们返回 true。否则我们返回假的。

```
// Java program to check if a URL is valid 
// using java.net.url
import java.net.URL;

class Test {

    /* Returns true if url is valid */
    public static boolean isValid(String url)
    {
        /* Try creating a valid URL */
        try {
            new URL(url).toURI();
            return true;
        }

        // If there was an Exception
        // while creating URL object
        catch (Exception e) {
            return false;
        }
    }

    /*driver function*/    
    public static void main(String[] args)
    {
        String url1 = "https://www.geeksforgeeks.org/";
        if (isValid(url1)) 
            System.out.println("Yes");
        else
            System.out.println("No");     

        String url2 = "http:// www.geeksforgeeks.org/";
        if (isValid(url2)) 
            System.out.println("Yes");
        else
            System.out.println("No");                
    }
}
```

输出:

```
Yes
No

```

本文由**普拉纳夫**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。