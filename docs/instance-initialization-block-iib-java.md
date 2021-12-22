# Java 中的实例初始化块(IIB)

> 原文:[https://www . geesforgeks . org/instance-initialization-block-iib-Java/](https://www.geeksforgeeks.org/instance-initialization-block-iib-java/)

在 Java 程序中，可以对方法、构造函数和初始化块执行操作。实例初始化块或 IIB 用于初始化实例变量。首先，调用构造函数，java 编译器在第一条语句 super()之后复制构造函数中的实例初始值设定项块。每次创建类的对象时，它们都会运行。

*   每当初始化类时，并且在调用构造函数之前，都会执行初始化块。
*   它们通常放置在大括号内的构造函数之上。
*   没有必要把它们包括在你的课堂里。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate
// Instance Initialization Block
class GfG {
    // Instance Initialization Block
    {
        System.out.println("IIB block");
    }

    // Constructor of GfG class
    GfG() { System.out.println("Constructor Called"); }
    public static void main(String[] args)
    {
        GfG a = new GfG();
    }
}
```

**Output**

```java
IIB block
Constructor Called

```

**程序中的多个实例初始化块**

我们也可以在一个类中有多个 iib。如果编译器找到多个 IIB，那么它们都是从上到下执行的，也就是说，写在顶部的 IIB 将首先被执行。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate
// execution of multiple
// Instance Initialization Blocks
// in one program
class GfG {
    // Instance Initialization Block - 1
    {
        System.out.println("IIB1 block");
    }

    // Instance Initialization Block - 2
    {
        System.out.println("IIB2 block");
    }

    // Constructor of class GfG
    GfG() { System.out.println("Constructor Called"); }

    // Instance Initialization Block - 3
    {
        System.out.println("IIB3 block");
    }

    // main function
    public static void main(String[] args)
    {
        GfG a = new GfG();
    }
}
```

**Output**

```java
IIB1 block
IIB2 block
IIB3 block
Constructor Called

```

**带有父类的实例初始化块**

父类中也可以有 iib。实例初始化块代码在调用构造函数中的 super()后立即运行。编译器在执行当前类的 IIB 之前执行父类的 IIB。

请看下面的例子。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate
// Instance Initialization Block
// with super()

// Parent Class
class B {
    B() { System.out.println("B-Constructor Called"); }

    {
        System.out.println("B-IIB block");
    }
}

// Child class
class A extends B {
    A()
    {
        super();
        System.out.println("A-Constructor Called");
    }
    {
        System.out.println("A-IIB block");
    }

    // main function
    public static void main(String[] args)
    {
        A a = new A();
    }
}
```

**Output**

```java
B-IIB block
B-Constructor Called
A-IIB block
A-Constructor Called

```

在上面的例子中，当创建类 A 的对象时，编译器试图执行类 A 的构造函数。但是它会找到 super()语句，并首先转到父类构造函数来执行。在这种情况下，执行顺序如下:

1.  超类的实例初始化块。
2.  超类的构造函数。
3.  类的实例初始化块。
4.  类的构造函数。

**重要点:**

*   每次创建新实例时，实例初始化块都会运行。
*   初始化块按照它们在程序中出现的顺序运行
*   实例初始化块在父类构造函数被调用后(即在 super()构造函数调用后)被调用

**相关文章:**
[Java 中的初始化器块](https://www.geeksforgeeks.org/g-fact-26-the-initializer-block-in-java/)
本文由 **Vishal Garg** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。