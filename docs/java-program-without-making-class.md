# Java 程序不制作类

> 原文:[https://www . geesforgeks . org/Java-程序-不制作类/](https://www.geeksforgeeks.org/java-program-without-making-class/)

不做类可以运行 Java 程序吗？

这个想法对我们来说[枚举就是 Java](https://www.geeksforgeeks.org/enum-in-java/) 。每个枚举常数总是隐式公共静态 final。由于它是静态的，我们可以通过使用枚举名称来访问它。因为它是最终的，我们不能创建子枚举。

我们可以在枚举中声明 main()方法。因此，我们可以直接从命令提示符调用枚举。

```java
// A Java program to demonstrate that we can have
// main() inside enum class.
enum Color
{
    RED, GREEN, BLUE;

    // Driver method
    public static void main(String[] args)
    {
        Color c1 = Color.RED;
        System.out.println(c1);
    }
}
```

输出:

```java
RED
```

请注意[枚举内部也使用类](https://www.geeksforgeeks.org/enum-in-java/)。这篇文章的目的是创建一个有趣的问题，用户不必显式地创建一个类。

本文由 **Raghawendra Singh** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。