# JVM 是否创建 main 类的对象(Main()的类)？

> 原文:[https://www . geesforgeks . org/JVM-create-object-main-class-class-contains-main/](https://www.geeksforgeeks.org/jvm-create-object-main-class-class-contains-main/)

考虑以下程序。

```java
class Main {
    public static void main(String args[])
    {
        System.out.println("Hello");
    }
}
```

输出:

```java
Hello
```

JVM 创建 Main 类的对象吗？
答案是“否”。我们研究过，Java 中 main()静态的原因是为了确保 main()可以在没有任何实例的情况下被调用。为了证明这一点，我们可以看到下面的程序编译并运行良好。

```java
// Note Main is abstract
abstract class Main {
    public static void main(String args[])
    {
        System.out.println("Hello");
    }
}
```

输出:

```java
Hello
```

由于我们无法在 Java 中创建[抽象类的对象，所以保证 main()类的对象不是由 JVM 创建的。](https://www.geeksforgeeks.org/abstract-classes-in-java/)

本文由**纳伦德拉·科里**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论