# GFact 48 | Java 中重载 main()

> 原文:[https://www . geesforgeks . org/gfact-48-重载-main-in-java/](https://www.geeksforgeeks.org/gfact-48-overloading-main-in-java/)

考虑下面的 Java 程序。

```java
// A Java program with overloaded main()
import java.io.*;

public class Test {

    // Normal main()
    public static void main(String[] args) {
        System.out.println("Hi Geek (from main)");
        Test.main("Geek");
    }

    // Overloaded main methods
    public static void main(String arg1) {
        System.out.println("Hi, " + arg1);
        Test.main("Dear Geek","My Geek");
    }
    public static void main(String arg1, String arg2) {
        System.out.println("Hi, " + arg1 + ", " + arg2);
    }
}
```

**输出:**

```java
Hi Geek (from main)
Hi, Geek
Hi, Dear Geek, My Geek
```

**要点:**
爪哇的主要方法是无地外法。除了 main()就像任何其他方法一样&可以以类似的方式重载之外，JVM 总是寻找方法签名来启动程序。

*   正常的主方法充当 JVM 开始执行程序的入口点。
*   我们可以在 Java 中重载主方法。但是当我们运行您的程序时，程序并不执行重载的 main 方法，我们只需要从实际的 main 方法中调用重载的 main 方法。

**相关文章:**
[Java 中 main()的有效变体](https://www.geeksforgeeks.org/valid-variants-main-java/)
[在 C++中重载 main](https://www.geeksforgeeks.org/can-main-overloaded-c/)
[我们可以重载或者覆盖 Java 中的静态方法吗？](https://www.geeksforgeeks.org/can-we-overload-or-override-static-methods-in-java/)

本文由 **希曼希古普塔供稿。** 如果你喜欢 GeeksforGeeks 并想投稿，你也可以写一篇文章，把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论