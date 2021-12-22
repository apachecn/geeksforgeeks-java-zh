# Java 中的最终局部变量

> 原文:[https://www.geeksforgeeks.org/final-local-variables-java/](https://www.geeksforgeeks.org/final-local-variables-java/)

**先决条件:** [最终关键字](https://www.geeksforgeeks.org/final-keyword-java/)、[变量、](https://www.geeksforgeeks.org/variables-in-java/) [变量范围](https://www.geeksforgeeks.org/variable-scope-in-java/)

Java 中的局部变量**是一个在方法体中声明的变量。那么您只能在该方法中使用该变量。该类中的其他方法甚至不知道该变量的存在。如果我们声明一个局部变量，那么我们应该在使用它之前在块中初始化它。在局部变量的情况下，JVM 不会提供任何默认值。**

当你“不小心”试图修改一个值时，一个**最终局部变量**会作为一个警告，并向编译器提供信息，从而可以更好地优化类文件。

**使用最终局部变量的可用性:**

*   最重要的是，我们可以在一个[匿名内部类](https://www.geeksforgeeks.org/anonymous-inner-class-java/)中使用局部变量作为 final，我们必须将匿名内部类的局部变量声明为 final。这与为实现匿名内部类而生成的单个访问器方法有关。非最终局部变量不能用于内部类
*   它可能允许 Java 编译器或即时编译器优化代码，知道变量值不会改变。这样可以提高程序的处理时间。

**关于局部最终变量的要点:**

1.  **Initialization of the variable is not Mandatory**: Even though local variable is final we have to perform initialization only if you want to use it i.e. if we are not using then it is not required to perform initialization even though it is final.

    ```
    // Java program to illustrate the behavior of
    // final local variable
    class Test {
        public static void main(String[] args)
        {
            final int x;
            System.out.println("GEEKS");
        }
    }
    ```

    输出:

    ```
    GEEKS

    ```

2.  **Final is the only applicable modifier for local variables** : The only applicable modifier for local variable is final. By mistake if we trying to apply any other modifier then we will get compile time error.

    ```
    // Java program to illustrate that final is
    // the only applicable modifier for local variable
    class Test {
        public static void main(String[] args)
        {
            public int x; // static int x will also not work.
            System.out.println("GEEKS");
        }
    }
    ```

    输出:

    ```
    error: illegal start of expression

    ```

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。