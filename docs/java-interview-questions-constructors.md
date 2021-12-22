# Java 关于构造函数的面试问题

> 原文:[https://www . geesforgeks . org/Java-面试-问题-构造函数/](https://www.geeksforgeeks.org/java-interview-questions-constructors/)

1.  **什么是[建造师？](https://www.geeksforgeeks.org/constructors-in-java/)**
    构造函数用于初始化对象的状态。与方法一样，构造函数也包含在对象创建时执行的语句(即指令)的集合。
2.  **我们在 Java 有[复制构造器吗？](https://www.geeksforgeeks.org/copy-constructor-in-java/)**
    和 C++一样，Java 也支持复制构造函数。但是，与 C++不同的是，如果你不自己编写，Java **不会创建默认的复制构造函数**。
    要在 java 中将一个对象的值复制到另一个对象中，您可以使用:
    *   构造器
    *   将一个对象的值分配给另一个对象
    *   [克隆对象类的()方法](https://www.geeksforgeeks.org/clone-method-in-java-2/)
3.  **什么是[建造师链](https://www.geeksforgeeks.org/constructor-chaining-java-examples/)？**
    构造函数链接是一种从一个构造函数调用另一个构造函数的技术。this()用于调用同一个类构造函数，其中 as super()用于调用超类构造函数。

    ```
    // Java program to illustrate Constructor Chaining
    // within same class Using this() keyword
    class Temp
    {
        // default constructor 1
        // default constructor will call another constructor
        // using this keyword from same class
        Temp()
        {
            // calls constructor 2
            this(5);
            System.out.println("The Default constructor");
        }

        // parameterized constructor 2
        Temp(int x)
        {
            // calls constructor 3
            this(5, 15);
            System.out.println(x);
        }

        // parameterized constructor 3
        Temp(int x, int y)
        {
            System.out.println(x * y);
        }

        public static void main(String args[])
        {
            // invokes default constructor first
            new Temp();
        }
    }
    ```

4.  **能否从超类构造函数调用子类构造函数？**
    没有，在 java 中没有办法从超类构造函数中调用子类构造函数。
5.  **如果为构造函数保留一个返回类型会发生什么？**
    理想情况下，构造函数不能有返回类型。根据定义，如果一个方法有返回类型，它就不是构造函数。( [JLS8.8 申报](http://docs.oracle.com/javase/specs/#8.8))将按正常方法处理。但是编译器给出了一个警告，说这个方法有一个构造函数名。示例:

    ```
    class GfG
    {
        int GfG()
        {
            return 0;    // Warning for the return type
        }
    }
    ```

6.  **什么是无参数构造函数？**
    没有参数的构造函数称为无参数构造函数。java 中的默认构造函数总是一个无参数的构造函数。

    ```

    class GfG
    {
        public GfG()
        {
            //No-arg constructor
        }
    }
    ```

7.  **How a no – argument constructor is different from [default Constructor](https://www.geeksforgeeks.org/g-fact-50/)?**
    If a class contains no constructor declarations, then a default constructor with no formal parameters and no throws clause is implicitly declared.

    如果被声明的类是原始类对象，那么默认构造函数的主体是空的。否则，默认构造函数只是调用没有参数的超类构造函数。

8.  **什么是[私人建造商](https://www.geeksforgeeks.org/private-constructors-and-singleton-classes-in-java/)在哪里使用？**
    像任何方法一样，我们可以为构造函数提供访问说明符。如果它是私有的，那么它只能在类内部访问。
    我们使用私有构造函数的主要场景:
    *   内部构造函数链接
    *   单例类设计模式
9.  **我们什么时候需要[构造函数重载](https://www.geeksforgeeks.org/constructor-overloading-java/)？**
    有时候需要用不同的方式初始化一个对象。这可以使用构造函数重载来完成。不同的构造函数可以通过实现不同的代码行来完成不同的工作，并根据传递的参数的类型和数量进行调用。
    根据情况，在重载的构造函数中，用特定数量的参数调用一个构造函数。
10.  **Java 中有析构函数吗？**
    不，因为 Java 是一种垃圾收集语言，你无法预测一个对象何时(甚至是否)会被销毁。因此不存在析构函数的直接等价物。

[对施工人员的测验](https://www.geeksforgeeks.org/java-gq/constructors-2-gq/)

本文由齐亚娜·辛格供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论