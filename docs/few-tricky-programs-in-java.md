# Java 中很少的狡猾程序

> 原文:[https://www.geeksforgeeks.org/few-tricky-programs-in-java/](https://www.geeksforgeeks.org/few-tricky-programs-in-java/)

1.  **Comments that execute :**

    直到现在，我们一直被教导“评论不执行”。让我们看看今天的“执行的评论”

    下面是代码片段:

    ```java
    public class Testing {
        public static void main(String[] args)
         {
             // the line below this gives an output
             // \u000d System.out.println("comment executed");
         }
    }
    ```

    输出:

    ```java
    comment executed
    ```

    原因是 Java 编译器将 unicode 字符\u000d 解析为新行，并转换为:

    ```java
    public class Testing {
        public static void main(String[] args)
        {
            // the line below this gives an output
            // \u000d
            System.out.println("comment executed");
        }
    }
    ```

2.  **Named loops :**

    ```java
    // A Java program to demonstrate working of named loops.
    public class Testing 
    {
        public static void main(String[] args)
        {
        loop1:
        for (int i = 0; i < 5; i++)
         {
            for (int j = 0; j < 5; j++) 
            {
                if (i == 3)
                    break loop1;
                System.out.println("i = " + i + " j = " + j);
            }
        }
       }
    }
    ```

    输出:

    ```java
    i = 0 j = 0
    i = 0 j = 1
    i = 0 j = 2
    i = 0 j = 3
    i = 0 j = 4
    i = 1 j = 0
    i = 1 j = 1
    i = 1 j = 2
    i = 1 j = 3
    i = 1 j = 4
    i = 2 j = 0
    i = 2 j = 1
    i = 2 j = 2
    i = 2 j = 3
    i = 2 j = 4
    ```

    您也可以使用继续跳转到命名循环的开始。

    我们还可以在带有 for 循环的嵌套 if-else 中使用 break(或 continue)，以便使用 if-else 中断几个循环，因此可以避免设置大量标志并在 if-else 中测试它们，以便在此嵌套级别中继续或不继续。

本文由 **Abhineet Nigam** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。