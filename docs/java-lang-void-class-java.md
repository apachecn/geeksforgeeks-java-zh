# Java 中的 Java.lang.Void 类

> 原文:[https://www.geeksforgeeks.org/java-lang-void-class-java/](https://www.geeksforgeeks.org/java-lang-void-class-java/)

**Java.lang.Void** 类是一个占位符，如果它代表 Void 关键字，它会保存对类对象的引用。它是一个不可保存的占位符。嗯，不可实例化意味着这个类有一个私有构造函数，没有其他我们可以从外部访问的构造函数。
**lang . void 类的方法都是从 Java 中的[对象类](https://www.geeksforgeeks.org/object-class-in-java/) :** 继承而来的

*   **getClass() :** 返回参数化对象的运行时类。
*   **hashCode() :** 返回对象的哈希码值。
*   **equals() :** 检查两个对象是否相等。
*   **clone() :** 返回对象的副本。
*   **toString() :** 返回对象的字符串表示形式。
*   **notify() :** 唤醒正在等待此对象监视器的单个线程。
*   **notifyAll() :** 唤醒所有正在等待此对象监视器的线程。
*   **wait() :** 使当前线程等待，直到前一个线程调用 notify()或 notifyAll()方法。
*   **finalize() :** 当垃圾收集确定不再有对对象的引用时，由垃圾收集程序在对象上调用。

**参考:**
[Java 甲骨文文档](https://docs.oracle.com/javase/7/docs/api/java/lang/Object.html)

本文由 [**【莫希特古普塔】**](https://www.facebook.com/profile.php?id=100016327034955) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。