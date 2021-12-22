# 用 Java 打印字符串之间的整数

> 原文:[https://www . geesforgeks . org/gfact-49-print-Java 中字符串之间的整数/](https://www.geeksforgeeks.org/gfact-49-print-integer-between-strings-in-java/)

试着算出这段代码的输出:

```
public class Test
{
    public static void main(String[] args)
    {
        System.out.println(45+5 + "=" +45+5);
    }
}
```

**输出:**

```
50=455
```

这背后的原因是——最初整数相加，我们得到的 L.H.S .为 50。但是，一旦遇到字符串，它就会被追加，我们会得到“50=”。现在' = '后的整数也被认为是一个字符串，所以被追加。

*   To make the output 50=50, we need to add a bracket around the sum statement to overload the concatenation operation.
*   This will force the sum `to occur before string concatenation, with brackets as the highest priority.`

 ````
public class Test
{
    public static void main(String[] args)
    {
        System.out.println(45+5 + "=" +(45+5));
    }
}
```

**输出:**

```
50=50
```

本文由**希曼希·古普塔**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论`