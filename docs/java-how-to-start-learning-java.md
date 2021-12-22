# Java |如何开始学习 Java

> 原文:[https://www . geesforgeks . org/Java-如何开始学习-java/](https://www.geeksforgeeks.org/java-how-to-start-learning-java/)

Java 是最流行和使用最广泛的编程语言和平台之一。平台是一种有助于开发和运行用任何编程语言编写的程序的环境。
Java 快速、可靠、安全。从桌面到网络应用，从科学超级计算机到游戏机，从手机到互联网，Java 被应用到每一个角落。

### **关于 Java**

*   **Java 是一种简单的语言:** Java 易学，语法清晰简洁。它基于 C++(所以对懂 C++的程序员来说更容易)。Java 删除了许多令人困惑且很少使用的特性，例如显式指针、运算符重载等。Java 还负责内存管理，它还提供了一个自动垃圾收集器。这将自动收集未使用的对象。
*   **Java 是一种独立于平台的语言:**用 Java 语言编写的程序，在编译之后，被转换成一种称为**字节码**的中级语言，它是 Java 平台的一部分，与运行程序的机器无关。这使得 java 具有高度的可移植性，因为它的字节码可以通过一个名为 java 虚拟机(JVM)的解释器在任何机器上运行，因此 Java 提供了“代码的可重用性”。
*   **Java 是一种面向对象的编程语言:** OOP 通过将完整的程序划分为多个对象，使其变得更加简单。这些对象可以作为一个桥梁，让数据从一个函数流向另一个函数。我们可以根据程序的要求轻松修改数据和函数。
*   **Java 是一种健壮的语言:** Java 程序必须是可靠的，因为它们既用于消费类应用程序，也用于任务关键型应用程序，从蓝光播放器到导航系统。
*   **Java 是一种多线程语言:** Java 通过定义多个线程可以一次执行很多任务。例如，在等待来自网络连接的输入时管理图形用户界面的程序使用另一个线程来执行和等待，而不是对两个任务都使用默认的图形用户界面线程。这保持了图形用户界面的响应性。
*   **Java 程序可以创建小程序:**小程序是在 web 浏览器中运行的程序。但是小程序支持在 **Java 9** 版本中被否决，并且**在 Java 11** 版本中被删除，因为警告浏览器支持 Java 插件。
*   **Java does not require any preprocessor:** It does not require inclusion of header files for creating a Java application.

    因此，Java 是一种非常成功的语言，它正在日益普及。

    ### **让你入门的重要提示和链接**

    1.  **了解基础知识:**
        学习任何编程语言的基础知识都非常重要。这是开始学习新东西的最好方法。不要有任何焦虑，开始学习关于语言的概念。熟悉环境，慢慢你会很快习惯的。以下是一些帮助您入门的链接:
        *   [Java–概述](https://www.geeksforgeeks.org/java/#Overview)
        *   [Java–基础(文章)](https://www.geeksforgeeks.org/java/#Basics)
        *   [Java–基础(视频)](https://www.youtube.com/watch?v=lcJzw0JGfeE&list=PLqM7alHXFySENpNgw27MzGxLzNJuC_Kdj)
        *   [OOP–概念](https://www.geeksforgeeks.org/java/#OOP%20concepts)
    2.  **耐心是关键:**
        学习 Java 会因为关于这门语言的大量材料而铺天盖地，但是要有耐心，按照自己的节奏学习，不要操之过急。掌握 Java 是一个需要时间的过程。记住即使是最好的程序员也会在某个时候开始。所以没什么大不了的，尽你所能坚持下去就好。慢慢来。耐心是成功的关键。
    3.  **练习编码**
        一旦你了解了基础知识，最好的办法就是通过定期练习来复习技能。真正的知识只有当你将所学付诸实践时才会出现，正如人们所说的“实践使人完美”。所以，**代码比你读的还要多**。这会建立你的信心。记住，完美的练习会让你变得完美。
        [<u>练习编码:</u>](https://practice.geeksforgeeks.org/topics/Java/) 你可以在这里增加你的编码技能。快乐编码！
    4.  **定期阅读 Java**
        持续阅读 Java 中的各种主题，并尝试探索更多。这将有助于保持你对 Java 的兴趣。
        通过此链接探索浩瀚的 Java 世界:
        [探索 Java > >](https://www.geeksforgeeks.org/java/)
        [最近关于 Java 的文章> >](https://www.geeksforgeeks.org/category/java/)
    5.  **小组学习**
        小组学习是更好的学习方式。这样，当每个人提出他们的想法时，你就可以了解关于这个主题的新东西，并且你可以当场讨论和解决你的编码问题。了解一群愿意学习 java 的普通人。
        寻求导师的帮助，尽可能多的阅读关于 java 的书籍。市场上有很多好书可以帮助你学习 java。

    ### 设置 Java

    你可以从 [<u>这里</u>](http://www.oracle.com/technetwork/java/javase/downloads/jdk10-downloads-4416644.html) 下载 java。在这里你会发现不同版本的 java。选择并下载与您的操作系统兼容的版本。
    关于 Java 设置的详细说明，请参考本文[。](https://www.geeksforgeeks.org/setting-environment-java/)

    正确设置 Java 环境后，尝试运行这个简单的程序:

    ```
    // A Java program to print GeeksforGeeks
    public class GFG {
        public static void main(String args[])
        {
            System.out.println("GeeksforGeeks");
        }
    }
    ```

    **Output:**

    ```
    GeeksforGeeks

    ```

    如果环境设置正确，代码编写正确，您将在控制台上看到这个输出。那是你的第一个 Java 程序！