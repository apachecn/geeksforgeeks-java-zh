# Java 函数/构造函数重载谜题

> 原文:[https://www . geesforgeks . org/Java-function constructor-overloading-拼图/](https://www.geeksforgeeks.org/java-functionconstructor-overloading-puzzle/)

预测程序的输出

```
public class GFG {
    private GFG(Object o) {
        System.out.println("Object");
    }
    private GFG(double[] d) {
        System.out.println("double array");
    }
    public static void main(String[] args) {
        new GFG(null);
    }
}
```

**解决方案:**
传递给构造函数的参数是空对象引用，数组也是引用类型。如果我们试着运行程序，我们会得到以下信息。
程序打印**双阵**。

我们可以注意到编译器不会导致模棱两可的调用错误。Java 的重载解析过程分为两个阶段。
第一阶段选择所有可访问和适用的方法或构造函数。
第二阶段选择第一阶段选择的最具体的方法或构造器。如果一个方法或构造函数可以接受传递给另一个方法或构造函数的任何参数，那么它就没有另一个方法或构造函数那么具体。
在我们的程序中，两个构造函数都是可访问和适用的。构造函数 GFG(对象)接受传递给 GFG(double[])的任何参数，因此 GFG(对象)不太具体。(每个双数组都是一个对象，但不是每个对象都是双数组。)

本文由 **Shubham Juneja** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。