# Java 中的访问和非访问修饰符

> 原文:[https://www . geesforgeks . org/access-and-non-access-修饰符-in-java/](https://www.geeksforgeeks.org/access-and-non-access-modifiers-in-java/)

Java 提供了一组丰富的修饰符。它们用于控制访问机制，也向 JVM 提供关于类功能的信息。它们分为两类:–

*   [**访问修饰符**](https://www.geeksforgeeks.org/access-modifiers-java/) **:** Java 的访问修饰符有**公共**、**私有**、**受保护**。Java 还定义了一个默认的访问级别(称为包私有)。

**它们是如何工作的？**

*   **public:** When a member of a class is modified by **public**, then that member can be accessed by any other code. 
    **private:** When a member of a class is specified as **private**, then that member can only be accessed by other members of its class. 
    Now you can understand why main( ) has always been preceded by the public modifier. It is called by code that is outside the program—that is, by the Java run-time system. When no access modifier is used, then by default the member of a class is public within its own package, but cannot be accessed outside of its package. **protected** applies only when [inheritance](https://www.geeksforgeeks.org/inheritance-in-java/) is involved. 

    **详细文章:**[Java 中的访问修饰符](https://www.geeksforgeeks.org/access-modifiers-java/)

*   **非访问修饰符:**在 java 中，我们有 7 个非访问修饰符。它们与类、方法、变量、构造函数等一起使用，向 JVM 提供关于它们行为的信息。他们是
    *   [静态](https://www.geeksforgeeks.org/static-keyword-java/)
    *   [决赛](https://www.geeksforgeeks.org/final-keyword-java/)
    *   摘要
    *   [同步](https://www.geeksforgeeks.org/synchronized-in-java/)
    *   [瞬态](https://www.geeksforgeeks.org/transient-keyword-java/)
    *   [挥发性](https://www.geeksforgeeks.org/volatile-keyword-in-java/)
    *   [原生](https://www.geeksforgeeks.org/native-keyword-java/)

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。