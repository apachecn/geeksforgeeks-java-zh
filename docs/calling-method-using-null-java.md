# 在 Java 中使用 null 调用方法

> 原文:[https://www . geesforgeks . org/calling-method-use-null-Java/](https://www.geeksforgeeks.org/calling-method-using-null-java/)

**先决条件:**Java 中的[null](https://www.geeksforgeeks.org/interesting-facts-about-null-in-java/)、[Java 中的](https://www.geeksforgeeks.org/static-keyword-java/)Static

**你能预测以下程序的输出吗？？**
在回答之前，请注意一个事实，在给定的代码中，fun()是属于类的静态成员，不属于任何实例。

```
// Java program to illustrate calling
// static method using Null
public class GFG {
    public static void fun()
    {
        System.out.println("Welcome to GeeksforGeeks!!");
    }

    public static void main(String[] args)
    {
        ((GFG)null).fun();
    }
}
```

输出:

```
Welcome to GeeksforGeeks!!
```

**解释:**
这个程序看起来应该抛出一个 NullPointerException。但是，主方法调用常量 null 上的 greet 方法(fun)，不能调用 null 上的方法。
但是，当你运行程序时，它会打印“欢迎来到极客博客！!"。让我们看看如何:

*   理解这个谜题的关键是 GFG.fun 是一个[静态](https://www.geeksforgeeks.org/static-keyword-java/)方法。
*   虽然在静态方法调用中使用表达式作为限定符是一个**坏主意**，但这正是这个程序所做的。
*   不仅由**表达式的值引用的对象的运行时类型在确定调用哪个方法时不起作用，而且对象的标识(如果有的话)也不起作用**。
*   在这种情况下，没有对象，但这没有区别。计算静态方法调用的限定表达式，但忽略其值。不要求该值为非空。

本文由 [**舒巴姆·朱尼加**](https://auth.geeksforgeeks.org/profile.php?user=shubhamjuneja11) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。