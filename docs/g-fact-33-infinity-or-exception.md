# 被 0 除时 Java 中的无穷大还是异常？

> 原文:[https://www . geesforgeks . org/g-fact-33-infinity-or-exception/](https://www.geeksforgeeks.org/g-fact-33-infinity-or-exception/)

考虑以下代码片段:

```
public class Geeksforgeeks
{
    public static void main(String[] args)
    {
        double p = 1;
        System.out.println(p/0);
    }
}
```

**输出** :

```
Infinity
```

```
public class Geeksforgeeks
{
    public static void main(String[] args)
    {
        int p = 1;
        System.out.println(p/0);
    }
}
```

**输出:**

```
Exception in thread "main" java.lang.ArithmeticException: / by zero
    at Geeksforgeeks.main(Geeksforgeeks.java:8)
```

**解释**:在第一段代码中，一个双精度值被除以 0，而在另一种情况下，一个整数值被除以 0。然而，两者的解决方案是不同的。

*   In the case of dual/floating-point division, the output is **infinity** , and the basic reason behind it is that it implements the floating-point arithmetic, which specifies a special value for the case of division by zero according to IEEE 754 standard, such as "not a number" or "infinity".
*   In the case of integer division, an arithmetic exception is thrown.

本文由**普拉哈尔·马图尔**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论