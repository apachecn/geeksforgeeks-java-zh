# Java 中 super()和 this()的区别

> 原文:[https://www.geeksforgeeks.org/difference-super-java/](https://www.geeksforgeeks.org/difference-super-java/)

类似文章: [super 和这个关键字](https://www.geeksforgeeks.org/super-and-this-keywords-in-java/)
super()以及这个()都是用来让**构造函数调用**的。super()用于调用 **Base** 类的构造函数(即 Parent 的类)，而 this()用于调用**当前**类的构造函数。

让我们详细看看它们:

**超级()**

1.  **super()** is use to call Base class’s(Parent class’s) constructor.

    ```java
    // Java code to illustrate usage of super()

    class Parent {
        Parent()
        {
            System.out.println("Parent class's No " + 
                                  " arg constructor");
        }
    }

    class Child extends Parent {
        Child()
        {
            super();
            System.out.println("Flow comes back from " + 
                            "Parent class no arg const");
        }
        public static void main(String[] args)
        {
            new Child();
            System.out.println("Inside Main");
        }
    }
    ```

    输出:

    ```java
    Parent class's No arg constructor
    Flow comes back from Parent class no arg const
    Inside Main

    ```

    **程序流程:**

    *   主要我们做了一个语句 **new Child()** ，所以它调用 Child 类的无参数构造函数。
    *   里面我们有 **super()** 调用父类的 no 参数，因为我们已经写了 super()和 no 参数，这就是为什么它没有调用父类的 no 参数构造函数，因为我们有一个 SOP 语句，因此它打印*父类的 No arg 构造函数*。
    *   现在，当父类的无参数常量完成时，流程返回到子类的无参数，因为我们有一个 SOP 语句，因此它打印*流程从父类的无参数常量*返回。
    *   此外，在完成子类流的无参数构造函数后，现在再次返回 main，执行剩余的语句，并在 Main 内部打印*。*
2.  *We can use super() **only inside constructor and nowhere else**, not even in static context not even inside methods and super() should be **first statement** inside constructor.

    ```java
    // Java program to illustrate usage of
    // super() as first statement

    class Parent {
        Parent()
        {
            System.out.println("Parent class's No " + 
                               "arg constructor");
        }
    } 

    class Child extends Parent {
        Child()
        {
            // Uncommenting below line causes compilation
            // error because super() should be first statement
            // System.out.println("Compile Time Error");
            super();

            System.out.println("Flow comes back from " + 
                           "Parent class no arg const");
        }

        public static void main(String[] args)
        {
            new Child();
            System.out.println("Inside main");
        }
    }
    ```

    输出:

    ```java
    Parent class's No arg constructor
    Flow comes back from Parent class no arg const
    Inside main

    ```

    **注意:** super()应该是任何构造函数里面**第一个**语句。它只能在构造器中使用**，不能在其他地方使用。super()用于仅引用**父类(超类)的构造函数**。*** 

***本()***

1.  *this() is used to call **current class’s constructor**.

    ```java
    // Java code to illustrate usage of this()

    class RR {
        RR()
        {
            this(10);
            System.out.println("Flow comes back from " + 
                               "RR class's 1 arg const");
        }

        RR(int a)
        {
            System.out.println("RR class's 1 arg const");
        }
        public static void main(String[] args)
        {
            new RR();
            System.out.println("Inside Main");
        }
    }
    ```

    输出:

    ```java
    RR class's 1 arg const
    Flow comes back from RR class's 1 arg const
    Inside Main

    ```

    **程序流程**:

    *   首先从 main 开始，然后我们做了一个声明 **new Child()** 因此它调用 Child 类的无参数构造函数，里面我们有 **this(10)** 它调用当前类(即 RR 类)的 1 参数
    *   因为我们已经写了这个(10)和 1 个参数，这就是为什么它调用 RR 类的 1 个参数构造函数。因为我们有一个标准操作程序语句，所以它打印了 *RR 类的 1 个参数常量*。
    *   现在，当 RR 类的 1 参数常量完成时，流程返回到 RR 类的 no 参数，因为我们有一个 SOP 语句，因此它打印*流程从 RR 类的 1 参数常量*返回。
    *   此外，在完成 RR 类流的无参数构造函数后，现在再次返回 main，执行剩余的语句，并在 Main 中打印*。** 
2.  *We can use this() **only inside constructor and nowhere else**, not even in static context not even inside methods and this() should be **first statement** inside constructor.

    ```java
    // Java program to illustrate usage of
    // this() as first statement

    class RR {
        RR()
        {
            // Uncommenting below line causes compilation
            // error because this() should be first statement
            // System.out.println("Compile Time Error");
            this(51);
            System.out.println("Flow comes back from RR " + 
                                     "class 1 arg const");
        }
        RR(int k)
        {
            System.out.println("RR class's 1 arg const");
        }
        public static void main(String[] args)
        {
            new RR();
            System.out.println("Inside main");
        }
    }
    ```

    输出:

    ```java
    RR class's 1 arg constructor
    Flow comes back from RR class 1 arg const
    Inside main

    ```

    **注意:**这个()应该是任何构造函数里面的**第一个**语句。它只能在构造器中使用**，不能在其他地方使用。该()仅用于引用当前类构造函数**。* 

***关于这个()和 super()的要点***

1.  *我们也可以在构造函数中只使用 super()这个()**一次**。如果我们两次使用 super()或者两次使用 this()或者 super()后跟 this()或者 this()后跟 super()，那么我们会立即得到编译时错误，即我们可以使用**或者 super()或者 this()作为构造函数内部的第一个语句，而不是两者都使用**。*
2.  *It is upto you that whether you use super() or this() or not because if we are not using this() or super() then **by default compiler will put super()** as first statement inside constructor.

    ```java
    // Java program to illustrate super() by default
    // executed by compiler if not provided explicitly

    class Parent {
        Parent()
        {
            System.out.println("Parent class's No " +
                              "argument constructor");
        }
        Parent(int a)
        {
            System.out.println("Parent class's 1 argument" + 
                                          " constructor");
        }

    }

    class Base extends Parent {
        Base()
        {
            // By default compiler put super() 
            // here and not super(int)
            System.out.println("Base class's No " + 
                            "argument constructor");
        }
        public static void main(String[] args)
        {
            new Base();
            System.out.println("Inside Main");
        }
    }
    ```

    ```java
    Output:
    Parent class's No argument constructor
    Base class's No argument constructor
    Inside Main

    ```

    **程序流程:**

    *   在 main 里面我们有**新的 Base()** 然后流程转到基类的**无参数构造器**。
    *   之后如果我们不放 super()或者 this()，那么**默认编译器放 super()** 。
    *   因此流程转到**父类的无参数构造函数** **，而不是 1 参数构造函数**。
    *   之后，它打印*父类的无参数构造函数*。
    *   之后，当 Parent()构造函数完成后，流程再次**返回到该**基类的无参数构造函数**并执行下一个 SOP 语句，即*基类的无参数构造函数*。**
    *   完成无参数构造器流程后**再次返回 main()** 并打印 main()中的剩余语句，即*main*中的语句

    但是，如果明确指定，您可以在 super 之前使用这个()。

    ```java
    // Java program to illustrate super() put by 
    // compiler always if not provided explicitly

    class Parent {
        Parent()
        {
            System.out.println("Parent class's No " + 
                               "argument constructor");
        }
        Parent(int a)
        {
            System.out.println("Parent class's one " + 
                               " argument constructor");
        }
    }

    class Base extends Parent {
        Base()
        {
            this(10);
            System.out.println("No arg const");
        }
        Base(int a)
        {
            this(10, 20);
            System.out.println("1 arg const");
        }
        Base(int k, int m)
        {
            // See here by default compiler put super();
            System.out.println("2 arg const");
        }
        public static void main(String[] args)
        {
            new Base();
            System.out.println("Inside Main");
        }
    }
    ```

    输出:

    ```java
    Parent class's No argument constructor
    2 arg const
    1 arg const
    No arg const
    Inside Main

    ```* 
3.  ***Recursive constructor call not allowed**

    ```java
    // Java program to illustrate recursive 
    // constructor call not allowed

    class RR {
        RR()
        {
            this(30);
        }
        RR(int a)
        {
            this();
        }
        public static void main(String[] args)
        {
            new RR();
        }
    }
    ```

    输出:

    ```java
    Compile time error saying recursive constructor invocation

    ```

    **程序流程:**这里，上面从 main()开始，然后流程转到**RR 类**的 No arg 构造函数。之后我们有**这个(30)** 并且流程转到**RR 的 1 个 arg 构造函数**并且因为我们有**这个()**所以流程再次转到基类的 No arg 构造函数并且因为我们有这个(30)并且流程再次转到基类的 1 个 arg 构造函数并且**它继续进行** ……就像**递归**。所以它是无效的，这就是为什么我们**得到编译时错误**说*递归构造函数调用*。所以递归构造函数调用在 java 中是不允许的。* 

*本文由 **Rajat Rawat** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。*

*如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。*